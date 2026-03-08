---
tags:
  - algotrading
  - "modern taa"
source: image-ocr
created: 2026-02-14
---

# Scaler Mapping: Regime Risk to Exposure

Scaler is a 2-step mapping from “regime risk” (0..1) to “exposure” (0..1):

## 1) Build `r_total` (aggregate regime risk)

- For each regime bucket `{riskonoff, inflation, rates, liquidity}`:
  - Take two input series (either macro series, or proxy-transformed ETF series)
  - Compute `z = zscore_last(series, window=z_window_days)`
  - Optionally invert sign (`invert=True` flips `z -> -z`)
  - Map to 0..1 with sigmoid: `risk = 1 / (1 + exp(-z))`
  - Bucket risk = average of the two input risks
- Aggregate buckets with weights (default equal):

`r_total = sum(bucket_risk[name] * weight[name]) / sum(weights)`

## 2) Map `r_total` to exposure scaler `s`

- `s_raw = exp(-kappa * r_total)`
- `s = clip(s_raw, s_min, 1.0)`

## Why you’re seeing a “limited” range (~0.43 to ~0.56)

- With default config (`kappa=1.5`), the mapping is:
  - if `r_total=0.39` -> `s=exp(-1.5*0.39)=0.56`
  - if `r_total=0.60` -> `s=exp(-1.5*0.60)=0.41`
  - That’s essentially the same band reported.
- Bigger limiter is usually each bucket risk staying near ~0.5 because sigmoid compresses z-scores; if underlying z-scores aren’t swinging wildly, `r_total` stays in a narrow band.

## Tuning direction

To target wider exposure ranges (e.g. high in calm regimes and low in stress), tune:
- `kappa`
- bucket weights
- transform windows
- sigmoid steepness
