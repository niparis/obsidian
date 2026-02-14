---
id: dream-escape-workflow
type: project
status: active
tags: [mobile-poc, boardgame, flowchart, process]
created: 2026-02-12
updated: 2026-02-12
---

# Dream Escape (Badcat Games) Overview
- **Setting:** cosmic horror/dreamlands with cultists, reality warps, unsettling creatures.
- **Components:** large portal/realm board + location decks, plus narrative/story decks, lore/condition cards, event track, reward pips, and runes.
- **Character sheet:** sanity, vitality, shards (lives buffer), meta-currencies (déjà vu, lucid dreams), inventory with protected/locked items.
- **Resolution:** rune toss (fortune runes + skill/item boosts). Matching symbols yield successes; bad symbols trigger curses/locks. Shard depletion = lose.
- **Progression:** reward pips toggle into skill upgrades/masteries. Lore cards and key-icons unlock new story threads (meta puzzle layer).

## Core Game Loop
1. **Realm + Location** – begin inside a portal (realm) and optionally a linked location.
2. **Draw Story Card** – pull from the realm or location deck depending on context.
3. **Narrative** – read text, resolve mandatory draws/effects, update lore.
4. **Reaction** – choose an action (move, observe, trade, fight, etc.).
5. **Test** – build rune pool (fortune + skills/items/lucid boosts), toss runes, tally successes, apply bad symbol penalties.
6. **Consequences** – gain items/lore/rewards, incur curses/hunger, lose vitality/shards, or shift location/realm.
7. **Event Track** – advance when the event icon appears; triggers realm pressure effects.
8. **Repeat** – continue until you escape or shards drop to zero.

## Pressure Systems
- Event track escalates realm pressure with threats/effects.
- Curses/locks cover ability slots, narrowing your options.
- Inventory fragility: fade tests or penalties can remove artifacts.
- Forced movement resets the context, demanding new key skills.

## Practical Workflow (Operating Procedure)
### A. Setup (per session)
1. Choose character → assign déjà vu, lucid, sanity, vitality, and shard count.
2. Equip starting artifact/items; mark any protected or locked slots.
3. Place the marker on the initial realm portal.
4. Layout decks: realm, location, lore, condition, threat, event track, rune tokens.

### B. Turn Flow
1. **Encounter Phase** – draw current story card; if event icon showing, advance event track/resolution.
2. **Narrative** – digest text; execute mandatory draws (lore/locked story) immediately.
3. **Reaction Selection** – pick a bottom option (some auto-success, some require tests).
4. **Test Building** – collect base runes + relevant skill/item/boost runes.
5. **Rune Toss** – count symbol matches; bad icons become curses/locks.
6. **Outcome Resolution** – follow success or failure text for that option.
7. **Consequences** – gain rewards, take curses, lose shards, remove items, log notes.
8. **State Changes** – if prompted, discover location (flip card and move marker) or shift realm (swap portal/reset event track).
9. **Win/Loss** – if shards remain, next turn; if zero, game over.

## Flowchart (text form)
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
(option requires test?)
├─ No → [Auto success resolution]
└─ Yes → [Build rune pool] → [Roll runes]
↓
(success?)
├─ Success → [Resolve success text]
└─ Failure → [Resolve failure/failure side]
↓
[Apply Consequences (loot/curses/shards)]
↓
(forced movement?)
├─ Location discovery → [Reveal location + draw linked card]
├─ Realm shift → [Swap portal + reset event track]
└─ None → continue
↓
(Shards remaining?)
├─ No → [Game over]
└─ Yes → [Next turn]
```

## Implementation Notes for Mobile PoC
- The rune toss becomes a tappable pool; highlight bad icons that add curses/locks.
- Shards visually surround the character portrait; depletion triggers game over alerts.
- Key icons/lore cards unlock branching narrative paths.
- Event track and curse stacks glow red when pressure builds.
- Inventory protections toggle (tap to lock/unlock) so items don’t fade unintentionally.
- Lucid/déjà vu tokens are reusable abilities; spending them should feel like a pulse of control.

## Decision Heuristics
- Reserve lucid dreams for critical succeed needs (shard save, unlock mastery).
- Keep déjà vu for rerunning easy tests vs. risk exposures.
- Avoid forced realm shifts unless they unlock lore or safer recovery nodes.
- Remove curses quickly; blocked slots neuter options.
- Balance reward pips toward skill upgrades for new rune boosts.
