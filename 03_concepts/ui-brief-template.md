---
id: ui-brief-template
type: concept
status: draft
tags: [mobile-poc, design-brief, ui, process]
created: 2026-02-12
updated: 2026-02-12
---

# AI-friendly UI Brief Template
Pairs with the stylistic brief; describe UI as state + layout + intent so Codex can act without guessing screen diagrams.

## 1️⃣ UI Philosophy
*Minimal, portrait-first, deterministic.* UI elements only render GameState and emit intents.

## 2️⃣ Global UI State
```
UIState:
  app_phase: {boot, main_menu, in_run, paused, game_over}
  overlay: {none, settings, help, shop}
  input_enabled: boolean
  notifications: list<Notification>
```
UI must be derivable from UIState + GameState with no hidden memory.

## 3️⃣ Screens as state projections
### Main Menu (app_phase = main_menu)
Visible regions:
- Header: title + version
- Primary: Start run, Continue (if saved_run_exists)
- Secondary: Settings, Credits
Interaction intents:
- Start run → Intent.StartNewRun
- Continue → Intent.ResumeRun
- Settings → overlay = settings

## 4️⃣ In-Run HUD layout grammar
- Top bar: left=current_score, center=run_timer, right=pause_button
- Bottom bar: primary_action_button
- Floating: contextual_tooltips (optional)
Constraints: HUD never overlaps gameplay; tap targets thumb-reachable.

## 5️⃣ Overlays as modal state
### Settings overlay (overlay = settings)
Blocks:
- Audio: music_volume, sfx_volume
- Gameplay: tutorial_enabled
- Meta: reset_progress
Rules: pauses gameplay; emits intents, never writes GameState.

## 6️⃣ Ban UI-owned logic
UI must not store progression, track timers, or decide outcomes—systems/reducers handle those.

## 7️⃣ Visual tokens
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
Tokens keep the brief engine-agnostic.

## 8️⃣ UI → Intent → State flow
Pause button tap → Intent.PauseRun → GameState = paused → UIState.app_phase = paused → show pause overlay.

## TL;DR
Describe state, intent, layout, rules. Avoid pixel talk, neutral naming, or UI-driven logic. This pairs cleanly with our Dream Escape project work.
