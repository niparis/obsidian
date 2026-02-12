---
title: AI-friendly UI Brief Template
tags: [mobile-poc, design-brief, ui]
related:
  - Stylistic Brief Framework
  - Dream Escape Workflow
---

# AI-friendly UI Brief Template
This template pairs with your functional/ stylistic specs (see [[Stylistic Brief Framework]]). Describe UI as a state machine + layout contract so Codex can reason across the whole game without guessing.

## 1️⃣ UI Philosophy (Paragraph)
*Minimal, portrait-first, deterministic. UI elements simply render GameState and emit intents; they never own logic.*

## 2️⃣ Global UI State
Think in terms of observable data, not widgets.
```
UIState:
  app_phase: {boot, main_menu, in_run, paused, game_over}
  overlay: {none, settings, help, shop}
  input_enabled: boolean
  notifications: list<Notification>
```
Important: UIState + GameState → full UI. No hidden UI memory.

## 3️⃣ Screens as State Projections
Example: Main Menu (app_phase = main_menu)
- Header: title + version
- Primary actions: Start run, Continue (if saved_run_exists)
- Secondary actions: Settings, Credits
- Interaction intents:
  - Start run → Intent.StartNewRun
  - Continue → Intent.ResumeRun
  - Settings → overlay = settings

## 4️⃣ In-Run HUD Layout Grammar
- Top bar: left=current_score, center=run_timer, right=pause_button
- Bottom bar: primary_action_button
- Floating: contextual_tooltips (optional)
Constraints:
- HUD never overlaps gameplay region
- Elements must be thumb-reachable

## 5️⃣ Overlays as Modal State
Settings Overlay (overlay = settings)
- Blocks: Audio (music/sfx), Gameplay toggles, Meta controls
- Rules: pauses gameplay, never mutates GameState directly, emits intents (e.g., Intent.SetMusicVolume)

## 6️⃣ Ban UI-owned Logic
The UI must not store progression, track timers, or decide outcomes. GameState reducers/systems handle those.

## 7️⃣ Visual Tokens
```
spacing_unit: 8px
corner_radius: 12px
primary_color: #4CAF50
danger_color: #E53935
font_scale:
  title: 1.4
  body: 1.0
  caption: 0.85
```
Tokens keep things adaptable across engines.

## 8️⃣ UI → Intent → State Flow
Example: Pause button tap → emit Intent.PauseRun → GameState → paused → UIState.app_phase = paused → show pause overlay.

## TL;DR
Describe: State, Intent, Layout regions, Rules. Avoid: Pixel-perfect talk, UI-driven logic, UI-only timers. Use this alongside the stylistic brief so both brain and taste converge on the mobile PoC.
