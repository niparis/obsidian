---
title: 30 SMMA Market-Condition Classification (Momentum vs Mean Reversion)
tags: [openclaw]
created: 2026-03-08
---

# 30 SMMA Market-Condition Classification (Momentum vs Mean Reversion)

_Source: extracted from Koroush AK PDF shared on 2026-03-04._

## Purpose

This is a **market regime classifier**, not a standalone entry/exit strategy.
It helps decide when to apply:

- **Momentum trading** (trade with trend)
- **Mean reversion trading** (fade moves)

using two inputs:

1. **30 SMMA direction** (Trending vs Sideways)
2. **Crossover count** (price crossing the 30 SMMA) since the last structure break

---

## Indicator Setup (TradingView)

Use **Smoothed Moving Average (SMMA)** with:

- **Length = 30**
- **Source = Close**
- **Timeframe = Chart** (not fixed TF)

> Note: default length is often 7; must be changed to 30.

---

## Crossover Counting Rules

A crossover occurs when price moves from one side of the 30 SMMA to the other.

Rules:

1. **Every cross counts, including wick-only crosses**
2. **Dwell-time rule:** if price crosses and stays on the other side for **10+ minutes**, count as a full cross
3. **Start counting after structure break** (breakout from consolidation), not inside tight consolidation
4. Use visual marks (e.g., yellow circles/highlighter) to make counting auditable

---

## Momentum Classification

Inputs:

- MA direction: Trending or Sideways
- Cross count bucket: 0–3, 4–6, 7+

Classification:

- **Ideal:** Trending MA + **0–3 crosses**
- **Average:** Trending MA + **4–6 crosses**
- **Poor:**
  - Sideways MA (any cross count), or
  - **7+ crosses** (even with trending MA)

Interpretation: momentum needs directional slope + limited back-and-forth.

---

## Mean Reversion Classification (Inverse Logic)

Classification:

- **Ideal:** Sideways MA + **7+ crosses**
- **Average:**
  - Trending MA + **7+ crosses**, or
  - Sideways MA + **4–6 crosses**
- **Poor:**
  - **0–3 crosses** (regardless of MA direction), or
  - Trending MA + **4–6 crosses**

Interpretation: mean reversion benefits from frequent oscillation around the mean.

---

## Pre-Trade Workflow (Checklist)

1. Add 30 SMMA (exact settings)
2. Identify last structure break (start of current regime)
3. Count crossovers from that point to now
4. Label MA as Trending or Sideways
5. Classify conditions for the intended strategy type
6. Trade only if environment is Ideal/Average for that style; skip if Poor

---

## Key Principle

The same chart can be:

- bad for momentum but good for mean reversion, or
- good for momentum but bad for mean reversion.

Classification is strategy-dependent.
