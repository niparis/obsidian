---
title: Godot Best Practices
tags: [godot, gdscript, game-dev, best-practices, architecture]
created: 2026-03-10
---

# Godot Best Practices

## Core GDScript patterns and autoloads

This note captures practical architecture patterns used repeatedly across Godot projects.

### 1) Global Script (Singleton)

Use a Global autoload as a central access point for shared state and managers.

**Setup**
- Add via `Project Settings -> Autoload` so it loads at game startup.

**Common uses**
- Data managers for persistent startup-loaded content (e.g., card catalogs).
- Centralized RNG (`RandomNumberGenerator`) for consistent global seeding behavior.
- Main scene reference: assign root scene to `Global.main` in `_ready()` for easy top-level access from any node.

### 2) Signal Bus

Use a dedicated Signal Bus autoload to expose global signals.

**Why**
- Decouples distant systems (e.g., UI and game state) without hard references.

**Caveat**
- Signal execution order is not guaranteed by Godot.
- If strict sequencing is required, prefer direct method calls.

### 3) Utility Script + Enums

Use a Util script for stateless helpers, constants, and shared mappings.

**Best practices**
- Use enums broadly (resource types, states, modes) to keep UI and logic aligned.
- Keep math helpers and static functions in Util when no owned state is needed.

### 4) Reference Scene Autoload (instead of raw script)

Use an autoloaded scene (node + script) for visually configurable references.

**Benefits**
- Configure colors, textures, and packed scenes via exported variables in Inspector.
- Avoid hardcoding values (hex colors, path strings) where possible.
- Map enums to visual assets through helper methods to enforce consistency.

### 5) Scene Changer

Use a global scene-transition manager for clean state changes.

**Typical structure**
- `CanvasLayer` + `ColorRect` + `AnimationPlayer` for fade transitions.

**Workflow**
- Use enum-based `match` to resolve next-scene paths.
- Use `call_deferred` for safe scene switching.

### 6) Audio Manager

Use a global audio limiter to prevent stacked SFX distortion.

**Pattern**
- Track active instances per sound key.
- Enforce max concurrent instances for each effect.
- Block additional plays until one instance finishes.

**Result**
- Cleaner, more professional audio mix under burst events.

### 7) Hexagon Utility (project-specific)

For hex-grid projects, isolate coordinate math in a dedicated utility module.

**Responsibilities**
- Hex coordinates
- Neighbor lookup
- Distance calculations

**Practical note**
- Cell size often needs manual tuning to match actual textures.

## Quick implementation checklist

- Add autoloads: `Global`, `SignalBus`, `Util`, `SceneChanger`, `AudioManager`
- Standardize enums before feature growth
- Keep sequencing-critical logic out of unordered signal chains
- Centralize scene transitions and audio constraints early
- Use reference scenes when designers/art iteration is frequent

## Links

- [[Slay the Fermi — Design Brief v4]]
