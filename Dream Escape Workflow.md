---
title: Dream Escape (Badcat Games) workflow
tags: [mobile-poc, boardgame, flowchart]
related: Dream Escape (Badcat Games)
---

# Dream Escape (Badcat Games) Overview
- **Setting:** cosmic horror/dreamlands with cultists, reality warps, unsettling creatures.
- **Components:** large portal/realm board + location decks, plus narrative/story decks, lore/condition cards, event track, reward pips and runes.
- **Character sheet:** sanity, vitality, shards (lives buffer), meta-currencies (déjà vu, lucid dreams), inventory with protected/locked items.
- **Resolution:** rune toss (fortune runes + skill/item boosts). Matching symbols give successes; bad symbols trigger curses/locks. Shard depletion = lose.
- **Progression:** reward pips toggle into skill upgrades/masteries. Lore cards and key-icons unlock new threads (meta puzzle layer).

# Core Game Loop
1. **Realm + Location:** start inside a portal (realm) and sometimes a linked location.
2. **Draw Story Card:** realm or location deck depending on context.
3. **Narrative:** read text, resolve mandatory draws/effects.
4. **Reaction:** choose option (move, observe, fight, interact, etc.).
5. **Test:** build rune pool (base fortune runes + skills/items/lucid boosts), roll, count successes, apply bad symbol penalties.
6. **Consequences:** gain items/lore/rewards, take curses/hunger, lose vitality/shards, or shift location/realm.
7. **Event Track:** advance when icon appears; triggers realm-specific pressure effects.
8. **Repeat until escape or shards drop to zero.**

# Pressure Systems
- Event track escalates realm pressure, adding threats/effects.
- Curses/blocks cover slots, limiting future options.
- Inventory is fragile—fade tests and penalties can remove key artifacts.
- Forced movement resets context, requiring skill/item reassessment.

# Practical Workflow (Operating Procedure)
### A. Setup (once per session)
1. Choose character → assign stats (déjà vu, lucid dreams, sanity, vitality, shard count).
2. Equip starting artifact + items (mark protections/locks).
3. Place your marker on the initial realm portal.
4. Layout decks: realm, location, lore, conditions, threats, rune tokens, event track.

### B. Repeatable Turn Flow
1. **Encounter Phase**
   - Draw the story card tied to your realm/location.
   - If event icon appears, advance the track and resolve its realm effect.
2. **Narrative**
   - Read text; draw extra lore/locked cards as directed.
3. **Reaction Selection**
   - Pick a reaction (some auto-success, others require X successes).
4. **Test Building**
   - Base runes + skill runes + item runes + temporary boosts (lucid dream, etc.).
5. **Rune Toss**
   - Roll, count symbol matches = successes; bad icons = curses/locks.
6. **Outcome Resolution**
   - Resolve the success/failure text for the chosen option.
7. **Consequences**
   - Acquire loot/rewards, gain lore, suffer curses, lose shard, prune inventory, log scars.
8. **State Changes**
   - Discover location: place marker, draw linked card.
   - Realm shift: swap portals, reset event track (per instructions).
   - Discard to memories when cards resolve fully.
9. **Win/Loss Check**
   - Shards > 0 → continue.
   - Shards = 0 → game over.

# Flowchart (textual)
```
[Start Turn]
↓
[Draw Story Card]
→ (event icon?) → [Advance Event Track + Resolve]
↓
[Read Narrative + Mandatory Draws]
↓
[Choose Reaction]
↓
(option has test?)
├─ No → [Auto success text]
└─ Yes → [Build rune pool] → [Roll runes]
↓
(success?)
├─ Success → [Resolve success outcome]
└─ Failure → [Resolve failure/flip card]
↓
[Apply rewards/consequences]
↓
(forced movement?)
├─ Location discovery → [Reveal location + draw its card]
├─ Realm shift → [Swap portal + reset event track]
└─ None → continue
↓
(Shards remaining?)
├─ No → [Game over]
└─ Yes → [Next turn]
```

# Implementation Notes for Mobile PoC
- Emulate the rune toss: touchscreen tap on rune pool to tally symbols, highlight bad icons that add curses/locks.
- Track shards as a discrete resource (visual shards around character portrait).
- Encode key icons/lore cards as unlocks for branching narrative paths.
- Highlight pressure meters: event track tickers and curse stacks should glow/red when triggered.
- Manage inventory protections by letting players lock items (tapping an item toggles protection).
- Lucid/déjà vu tokens become reusable abilities (cost + effect). Focus on push-your-luck tension with compounding penalties.

# Decision Heuristics (Optional)
- Spend lucid dreams when you need a guaranteed rune symbol (e.g., critical skill upgrade or shard risk).
- Save déjà vu for replaying easier tests later; use shards only when forced.
- Avoid forced realm shifts unless they unlock key lore or offer safer recovery.
- Prioritize clearing curse tokens early; blocked slots throttle future options quickly.
- Balance reward pip/skill upgrades to unlock extra runes instead of raw gear.
