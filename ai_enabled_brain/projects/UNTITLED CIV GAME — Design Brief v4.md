---
title: UNTITLED CIV GAME — Design Brief v4
tags: [openclaw, game-design, strategy, roguelite, deckbuilder, sci-fi, fermi-paradox]
created: 2026-03-10
---

# UNTITLED CIV GAME — Design Brief v4

## High-Level Reference

A choice-driven sci-fi strategy / god-game / deck-builder hybrid about guiding a small cluster of alien civilizations under rising existential pressure.

Inspirations include:

- Fermi Paradox for multi-civ tension, population/resource pressure, and existential sci-fi framing
- Slay the Spire for shared deck tension, hand management, and run-based structure
- Civilization for age progression and megaproject-like endgame races
- Dark Forest / Fermi paradox fiction for the core strategic tension: growth, contact, and visibility are dangerous

## 1. CORE FANTASY

You are not ruling one empire.
You are a higher-order guiding intelligence managing a small cluster of alien civilizations in a hostile galaxy.

Your role is to cultivate, steer, exploit, coordinate, and sometimes sacrifice civilizations so that at least some of them survive long enough to transcend, escape, or militarily overcome the forces closing in on them.

This is a game about:

- accelerating civilizations,
- balancing growth against exposure,
- coordinating different species with different tendencies,
- surviving multiple threat types,
- deciding who to protect, who to weaponize, and who to sacrifice.

The player fantasy is not “perfect optimization.”
It is cosmic stewardship under pressure.

## 2. CORE DESIGN PILLARS

### 2.1 Silence must be safer, but not sufficient

Staying quiet should help against some threats, especially Dark Forest-style lurkers, but pure turtling must not be a winning universal strategy.

### 2.2 Noise must be dangerous, but often necessary

Contact, coordination, expansion, military projection, and certain high-age breakthroughs should create risk, but also unlock powerful opportunities that quiet play cannot access.

### 2.3 Neglect must be allowed

The player should not be forced to service every civilization every turn.
Triage is central to the game.

### 2.4 Civs must feel distinct

Civilizations should differ through:

- starting stat profiles,
- keywords / gimmicks,
- leader choices,
- card pools,
- event tendencies,
- diplomatic instincts.

They should feel like political organisms, not just stat containers.

### 2.5 The deck must be both strategic and tactical

The deck-builder layer must support:

- long-term deck shaping,
- short-term crisis response,
- civ identity,
- painful tradeoffs in attention and energy allocation.

### 2.6 The game must stay legible

The design should be built around a maximum of 4 active civs at once.
This is a foundational constraint for fun, UI clarity, and emotional attachment.

## 3. CORE LOOP

Each turn, the player manages a shared deck and a shared energy budget across a small set of active civilizations.

### Turn loop

**Start of Turn**

- Gain Energy
- Resolve persistent status effects
- Check new proposals from civs (trade, colonization, military action, major policy shifts, etc.)
- Draw a hand from the shared God Deck

**Player Phase**

- Review civ states, threats, pending events, and proposals
- Spend Energy to play cards from the hand
- Cards usually affect their origin civ by default, though some can affect others
- Approve or deny certain civ proposals
- Use Synthesis if needed for major intervention

**Transit / Space Resolution**

- Advance fleets, colonization missions, probes, and interstellar logistics already in motion
- Some transit creates Noise and can be intercepted or disrupted

**Event Phase**

- Events resolve after player actions
- Telegraphed events may advance or trigger
- New random or systemic events may fire

**Threat Phase**

- External threat meters advance
- Dark Forest detection checks occur
- Other threat archetypes expand / consume / raid according to their logic

**End of Turn**

- Science progress updates
- Age progression checks
- Resource consumption and internal tensions resolve
- New event telegraphs may appear

This loop should create the feeling that the player is constantly deciding:

- which civ to stabilize,
- which civ to accelerate,
- which civ to expose,
- which civ to let drift,
- which threat to respect most right now.

## 4. WIN / LOSE CONDITIONS

### Win Conditions

Difficulty may tune the required threshold, but victory is generally achieved by some combination of:

- Getting 1 / 2 / 3 civilizations to the final Age
- Completing one or more civilization-specific megaprojects
- Surviving long enough to achieve a cluster-level end state: transcendence, escape, fortified survival, dominion.

Megaprojects are intended as endgame “against the clock” commitments, similar in role to the spaceship in Civilization, though more civ-specific in flavor.

### Lose Conditions

- All active civilizations are destroyed or rendered non-viable before victory is achieved
- The cluster collapses under invasion, internal collapse, or irrecoverable strategic failure

Important:
A single civ dying is not an automatic loss.
Civ death is a setback and a structural transformation, not necessarily a run-ender.

## 5. ACTIVE CIV COUNT

### Hard cap

The player may control at most 4 active civilizations in a run at any given time.
This is a deliberate design constraint.

Why:

- preserves clarity,
- reduces spreadsheet feel,
- keeps relationship space manageable,
- maintains emotional connection,
- prevents the hand/energy system from collapsing into maintenance play.

Additional civilizations beyond that are not part of the core design and should not be assumed.

## 6. CIVILIZATION PROGRESSION

Each civilization advances through technological Ages primarily through Science progress, but progress is not guaranteed to be linear or safe.

Ages unlock:

- new cards,
- leader choices,
- new event pools,
- communication modes,
- travel options,
- megaproject access,
- new threat interactions.

| # | Age | Travel Tier | Contact / Communication |
|---|---|---|---|
| 1 | Stone Age | None | None |
| 2 | Bronze Age | None | None |
| 3 | Iron Age | None | None |
| 4 | Nautical Age | None | Radio signals possible |
| 5 | Industrial Age | None | Radio signals |
| 6 | Nuclear Age | None | Radio signals |
| 7 | Digital Age | STL probes | Radio + data transmission |
| 8 | Cyber Age | STL fleets | Radio + culture sharing |
| 9 | Solar Age | STL colonization | Radio + slow physical exchange |
| 10 | Singularity Age | Fast STL | Practical physical contact |
| 11 | FTL Age | FTL | Instant contact; loud and dangerous |
| 12 | Nano Age | FTL + stealth options | Instant |
| 13 | Godlike Age | Transcendence / portals / post-material means | Beyond conventional contact |

Machine or synthetic civs may use parallel age naming or variant presentation, but should map to the same progression skeleton unless there is a compelling reason not to.

## 7. THE FTL TRANSITION

The transition into FTL is one of the central dramatic moments of the game.

### Core principle

FTL is not just “more mobility.”
It is a major exposure threshold.

Crossing into FTL should:

- sharply increase Noise,
- accelerate certain threat responses,
- create new strategic opportunities,
- demand that the player has prepared militarily and diplomatically beforehand.

### Design intent

The player should not stumble accidentally into FTL disaster.
The transition should be clearly legible and deliberate.

### FTL design rules

- Reaching the prerequisite Age should not instantly force a civ into full FTL behavior
- FTL-capable action should likely require a specific project, activation, doctrine choice, or breakthrough card sequence
- The player should know that FTL will increase exposure
- FTL should unlock benefits that justify the risk: much faster coordination, deeper alliances, stronger military response, access to advanced megaprojects, late-game survival tools.

FTL should be dangerous, but it must not feel like a trap.
It should feel like crossing a threshold you knew was coming.

## 8. MULTIPLE THREAT ARCHETYPES

One of the biggest changes from the original brief is that the galaxy no longer contains only one threat logic.
This is essential to prevent “stay quiet forever” from becoming the dominant strategy.

### Design goal

Different threats should punish different weaknesses and therefore force the player to balance incompatible demands.

### 8.1 Lurkers / Dark Forest Predators

These are the closest to the original design.
They respond primarily to:

- Noise,
- broadcasts,
- visible transit,
- FTL activity,
- excessive technological prominence.

They punish:

- loud growth,
- poorly timed FTL,
- careless contact,
- obvious military projection.

They are best countered by:

- stealth,
- careful timing,
- selective broadcasting,
- late coordinated defense,
- deception and concealment tools.

### 8.2 Resource-Seeking Swarms

These are relentless expansionist threats that advance regardless of noise.
They respond primarily to:

- available biomass,
- infrastructure,
- weakly defended systems,
- economic abundance.

They punish:

- passive turtling without military buildup,
- over-rich but undefended systems,
- cluster stagnation,
- weak logistics.

They are best countered by:

- military readiness,
- strategic sacrifice,
- fortified worlds,
- controlled expansion,
- strong industrial output.

### 8.3 Opportunistic Raiders / Chaotic Expanders

These threats do not require high noise and are less deterministic.
They spread into:

- weak frontiers,
- under-defended transit routes,
- fragmented civilizations,
- unstable border regions.

They punish:

- neglect,
- weak periphery defense,
- internal disorder,
- disjointed cluster planning.

They are best countered by:

- flexible force projection,
- local stability,
- distributed defenses,
- rapid response.

### Threat composition per run

Not every run should feature every threat at equal strength.
Recommended structure:

- one primary threat doctrine per run,
- one secondary threat pressure,
- optional higher-difficulty wildcard behavior.

This supports:

- replayability,
- difficulty scaling,
- clearer strategic identity per run.

### Difficulty system

Threat mixture can serve as a major difficulty axis:

- easier runs: slower baseline pressure, clearer dominant threat
- harder runs: faster pressure, less predictable overlap, more punishing multi-threat environments

## 9. NOISE

Noise remains a central derived concept, but no longer the sole driver of danger.

### What Noise represents

A civilization’s visibility, detectability, and “signal” within a hostile galaxy.

### Noise sources

Noise increases from:

- scientific advancement,
- large populations,
- active broadcasts,
- certain events,
- transit,
- fleet movement,
- FTL actions,
- loud cards,
- megaproject phases,
- major warfare.

### Noise suppression

Noise can be reduced or mitigated through:

- radio silence,
- stealth tech,
- selective policy choices,
- certain leaders,
- post-FTL stealth options,
- specific cards,
- cultural / diplomatic restraint.

### Design role

Noise should matter a lot, especially versus lurker-type threats.
But Noise should not be the only strategic axis.
The player must sometimes accept Noise because the galaxy is dangerous in more than one way.

## 10. CIVILIZATION STATS

A major change from the original brief is that “mana” is no longer a separate spendable layer.
Civilizations now primarily track persistent state variables / stats.
These stats should be visible and central.

### 10.1 Science

Represents technological and intellectual development.
Effects:

- drives age progression,
- unlocks new cards and systems,
- may increase baseline Noise,
- enables new forms of travel, communication, and projects.

Risk if neglected:

- age progression stalls,
- fewer advanced options,
- weaker late-game response.

### 10.2 Population

Represents scale of civilization.
Effects:

- increases output potential,
- supports faster research and broader development,
- increases resource demand,
- increases Noise,
- raises stakes of crisis and war.

Risk if neglected:

- weak output,
- slow development,
- extinction spiral if population collapses.

Risk if too high:

- resource depletion,
- instability,
- easier targeting by some threats.

### 10.3 Resources

Represents sustainability and material base.
Effects:

- required to support population,
- required for stable development,
- low resources trigger internal crises, civil wars, collapse dynamics.

Risk if neglected:

- one of the most common routes to losing a civilization,
- unrest,
- fragmentation,
- starvation / collapse,
- military weakness.

### 10.4 Industry

Represents productive and infrastructural capacity.
Effects:

- speeds military buildup,
- supports megaproject construction,
- enables stronger recovery from crises,
- improves physical expansion and infrastructure response.

Risk if neglected:

- too slow to militarize,
- too slow to fortify,
- too slow to complete endgame commitments.

### 10.5 Ethics

Represents the civilization’s moral-social doctrine, from cooperative / humane to exploitative / dystopian.
This is not just flavor.
It should meaningfully change how the civilization behaves and what strategies it supports.

High Ethics tendencies:

- better alliances and trade,
- better long-term trust,
- stronger resilience to some corruption/panic effects,
- access to peaceful or cooperative project paths,
- improved stability in some events.

Low Ethics tendencies:

- higher industry at human cost,
- faster military buildup,
- more ruthless responses to crisis,
- stronger coercive or conquest play,
- access to harsh megaproject branches,
- some events become easier to exploit.

Risk if neglected:

- too-high dystopia can create internal brittleness, hostility, and long-term diplomatic problems
- too-high idealism may leave the civ under-militarized or slower to respond brutally when needed

Core design goal:
Ethics must be a temptation axis, not merely a punishment meter.

### 10.6 Military

Represents the civilization’s total military strength.
Military may later be expressed visually or conditionally as:

- ground capability,
- orbital capability,
- fleet capability,

but mechanically the current design should treat this as one core stat unless playtesting proves a full split is necessary.

Effects:

- defense against invaders,
- power projection,
- conquest capability,
- deterrence,
- stronger response to swarm / raider pressures.

At higher tech levels, stronger military naturally expresses more space-facing power.

Risk if neglected:

- undefended systems,
- inability to resist raids or swarms,
- vulnerability during or after FTL transition,
- inability to support allies.

## 11. REMOVED / CHANGED FROM ORIGINAL: MANA SYSTEM

The previous explicit mana system is removed as a primary mechanical layer.

### Removed elements

- per-civ mana pools as spendable resources
- Science / Industry / Strife / Art as passive mana currencies
- mana overflow as primary turn economy
- mana spending through card play as a core rule

### Why removed

- too many currencies,
- blurred the line between spendable resources and persistent state,
- increased cognitive load,
- made the economy harder to parse.

Some of the flavor previously carried by mana types should now reappear through:

- civ stats,
- civ keywords,
- leader effects,
- card tags,
- status conditions,
- event tendencies.

For example:

- previous “Strife mana” becomes unrest / volatility / militarist pressure
- previous “Art mana” becomes culture/trust/noise-reduction effects on cards or civ traits
- previous “Science mana” becomes strong Science state and science-tagged cards

## 12. GOD-LEVEL RESOURCES

The revised design now clearly distinguishes only two player-level resource layers:

### 12.1 Energy

Main per-turn resource.
Used to:

- play cards,
- execute turn actions,
- approve certain proposals,
- manipulate the deck tactically,
- trigger some cross-civ interactions.

Energy is the main tempo constraint of a turn.

### 12.2 Synthesis

Rare global intervention resource.
Used for:

- creating / awakening new civilizations,
- shaping what kind of civilization emerges,
- overriding or softening catastrophic outcomes,
- handling major race-defining events,
- forcing certain exceptional interventions.

Synthesis should remain powerful but sparse.
It should feel like:

- strategic reserve,
- moral capital,
- divine intervention,
- long-horizon choice resource.

It should not become just another generic spend meter.

## 13. THE GOD DECK

The God Deck is a shared deck drawn from each turn.
This remains one of the game’s defining features.

### Core structure

- One shared deck across the cluster
- Cards mostly originate from specific civilizations
- Draw a hand each turn
- Spend Energy to play cards
- Unplayed cards discard unless specific effects say otherwise

### Why shared deck

This creates the central cross-civ tension:
all civilizations compete for the same turn bandwidth and the same available hand.

The player is not deciding from a menu of all possible actions.
They are reacting to what the cluster’s deck currently offers.

That keeps runs dynamic and prevents pure deterministic optimization.

## 14. CARD OWNERSHIP AND TARGETING

This section is clarified compared to the original design.

### Default rule

Most cards belong to a specific civilization and, by default, primarily affect that civilization.
This is a major change in emphasis.
It preserves civ identity and prevents the shared deck from feeling too abstract.

### Cross-civ cards

Some cards can affect multiple civs or other civs, especially:

- trade cards,
- alliance cards,
- space operations,
- late-game coordination cards,
- certain leader cards,
- crisis or relic effects.

### Possible restrictions

Cross-civ play can be gated by:

- contact established,
- alliance status,
- tech tier,
- specific leader effects,
- additional Energy cost.

This keeps civ identity intact while preserving strategic flexibility.

## 15. CARD CATEGORIES

The next major design task after this brief is to define actual card sets.
The current agreed card grammar is:

### 15.1 CIV cards

Directly affect one or more stats or states of the origin civ.
Examples:

- boost Science,
- stabilize Resources,
- increase Industry,
- reduce unrest,
- alter Ethics,
- manage population pressure.

### 15.2 MIL cards

Military-focused cards.
Examples:

- increase Military,
- mobilize defense,
- prepare invasion,
- fortify a world,
- launch a campaign,
- react to incoming threats.

### 15.3 DECK cards

Manipulate the deck or hand.
Examples:

- draw,
- scry,
- discard,
- hold,
- tutor by card type,
- cycle,
- upgrade,
- remove.

These are essential for skill expression.

### 15.4 SPACE cards

Interstellar and threat-facing operations.
Examples:

- scout external threats,
- launch probes,
- establish contact,
- plan colonization,
- move fleets,
- create listening arrays,
- reveal predator profile,
- manage transit.

### 15.5 LEADER cards

Powerful, civ-defining cards tied to leader choices.
They should:

- strongly express civ identity,
- shape deck direction,
- provide unique, high-impact abilities.

Comparable in feel to highly distinctive legendary cards.

### 15.6 TRADE cards

Cards that affect the origin civ and one or more contacted / allied civs.
Examples:

- science-sharing treaties,
- industrial exchange,
- ethical-cultural exchange,
- logistics support,
- alliance reinforcement.

### 15.7 CRISIS cards

A special category created by severe states, bad events, or desperate situations.
They represent dangerous but potentially powerful emergency tools.
Examples:

- emergency militarization,
- forced migration,
- mass surveillance,
- sacrificial mobilization,
- scorched orbit,
- panic science.

These should create dramatic recovery lines from bad states.

## 16. DECK AGENCY

A major revision from the original design is that the deck-builder layer must have real agency, not just random draw dependency.

### 16.1 Strategic deck shaping

The player must be able to shape the deck over the course of the run through:

- card removal,
- card upgrades,
- leader choices,
- age transitions,
- certain events,
- relic conversion after civ death.

### 16.2 Tactical deck manipulation

The player must also have short-term control tools during runs and during turns.
Examples:

- scrying,
- drawing,
- tutoring by class,
- discarding and cycling,
- preserving a card for next turn,
- peeking at future cards.

This is essential because the game includes:

- telegraphed threats,
- looming crises,
- timing-sensitive opportunities.

Without tactical deck agency, anticipation would feel too luck-based.

## 17. AGE LEADERS

When a civilization reaches a new Age, the player chooses a leader or doctrinal direction for that Age.

Each Age Leader should do two things:

- Provide a passive or persistent modifier for that civilization during that Age
- Add or transform cards in the deck, usually through Signature Cards or card modifications

Design purpose:
Age Leaders are one of the main ways civilizations diverge over a run.

Examples of effects:

- diplomatic leaders improve trade and alliance tools
- authoritarian leaders improve military and industry at ethical cost
- visionary leaders increase Science and risk
- covert leaders reduce Noise and improve scouting

Leader choice should be one of the main identity-forming decisions.

## 18. CIV IDENTITY

Civilizations are not intended to be fully bespoke one-offs.
Identity should emerge from modular combinations.

### Sources of civ identity

- base stat profile,
- civ keywords / archetypes,
- starting card set,
- event tendencies,
- leader choices,
- diplomatic instincts,
- megaproject flavor.

### Keywords / archetypes

Examples:

- Hivemind
- Parasitic
- Nomadic
- Ascetic
- Honor-bound
- Synthetic
- Biosynthetic
- Expansionist
- Scholar-caste
- Ritualist

A civ may combine 2–3 archetypal keywords rather than rely on one giant unique ruleset.
This allows many distinct-feeling civs without impossible content scope.

## 19. CIV PROPOSALS AND SEMI-AUTONOMOUS BEHAVIOR

A key clarification added during discussion:
diplomacy and some strategic behaviors should not be fully manual micromanagement.

Civilizations should generate proposals based on their condition and nature.

Examples:

- a peaceful, high-Ethics civ proposes a trade exchange
- a militarized civ proposes preparing an invasion
- an expansionist civ proposes a colonization mission
- a fearful civ proposes radio silence
- a starving civ demands emergency intervention

The player then approves, denies, or modifies the scope.
This gives civs agency and reduces click-burden.
It also helps them feel alive.

## 20. INTER-CIV RELATIONSHIPS

This system is intentionally more abstract than in the original brief.
Because the game is capped at 4 active civs, relationship space is manageable, but it should still remain simple.

### Relationship states

Recommended baseline states:

- No Contact
- Contact
- Trade
- Alliance
- Rivalry / War

Optional visible sentiment layer:

- trusting
- cautious
- resentful

### Design intent

The player should not be tracking dozens of numeric diplomatic variables.
Instead, they should understand the broad current relationship and approve or deny major proposals.

### Effects of relations

Relationships influence:

- trade access,
- alliance actions,
- military coordination,
- card targeting,
- colonization cooperation,
- internal civ reactions.

## 21. CONTACT TIERS

The separation between communication and travel remains one of the most important original ideas and is preserved.

### 21.1 Radio Contact

Available before practical physical travel.
Effects:

- establishes contact,
- increases visibility / Noise,
- allows cultural and scientific exchange,
- may unlock trade-type interactions,
- can improve or worsen trust,
- may create misinformation, fear, or ideological drift.

Radio should feel like influence without commitment.

### 21.2 Physical Contact / Ships

Unlocks later.
Effects:

- colonization,
- migration,
- conquest,
- logistics,
- military reinforcement,
- physical artifact exchange,
- deeper alliance capability.

Physical contact should feel like commitment and consequence.
The first ship arriving after long radio-only contact should be a major event.

### 21.3 FTL Contact

Instant and strategically transformative.
Effects:

- rapid alliance support,
- fast fleet movement,
- large-scale coordination,
- rapid escalation of exposure.

## 22. TRANSIT AND SPACE COMMITMENT

Transit remains multi-turn and strategically meaningful.
STL transit takes multiple turns, creates exposure while underway, may be intercepted, commits the player to decisions whose consequences land later.

This is important because it creates irreversible tension.
You launch now, but the situation may change before arrival.

Uses of transit:

- scouting,
- colonization,
- reinforcement,
- conquest,
- inter-civ support,
- logistics.

## 23. THREAT INFORMATION / PREDATOR SCOUTING

The “predator legacy” idea remains, but now requires counterplay and information tools.

### Predator legacy

Past successful civilizations can shape future invaders or hostile doctrines.
The intent is:

- your past victories influence the ecology of future runs,
- your optimized strategies leave behind the kind of predator the galaxy learns to produce.

### Important clarification

This system must create a puzzle, not arbitrary punishment.

### Information access

The player should have some combination of:

- difficulty-based upfront information,
- threat doctrine preview,
- scouting cards,
- listening arrays,
- probes,
- late-game revelation tools.

Examples of SPACE cards that help:

- psyker listening
- deep probes
- long-range arrays
- intercepted transmissions
- recovered relic intelligence

The player must be able to adapt, not merely endure.

## 24. EVENT SYSTEM

Events fire after the player acts.
This remains important because the game should never feel fully safe or solved.

### Event types

- random local events,
- telegraphed disasters,
- ethics dilemmas,
- contact incidents,
- leader moments,
- threat encounters,
- internal crises,
- rare transformation events.

### Design role

Events:

- create chaos,
- force adaptation,
- pressure the player away from deterministic play,
- make civilizations feel alive.

## 25. TELEGRAPHED EVENTS

A major clarification from the discussion:
telegraphed events must be more than atmospheric warnings.

### How they work

A civilization may show an event incoming in N turns:

- meteor strike,
- flare,
- uprising,
- diplomatic incident,
- signal leak,
- predator scouting pass,
- etc.

### Design requirement

Each telegraphed event should have:

- a default consequence if ignored,
- known categories of mitigation,
- possible deck-based responses,
- possible stat-based responses,
- possible Synthesis override.

Examples:

- high Industry may mitigate infrastructure disaster
- strong Military may mitigate raid impact
- high Ethics may soften unrest event
- a specific card may cancel or redirect the event
- Synthesis may avert catastrophe at high cost

Telegraphing is only interesting if the player can meaningfully prepare.

## 26. ETHICS EVENTS AND TEMPTATION

This is now explicitly part of the design.

Many events should present choices like:

- gain power at ethical cost,
- preserve ethics at material cost,
- accept drift toward dystopia,
- spend Synthesis or Energy to preserve a civilization’s moral structure,
- weaponize fear,
- exploit labor,
- silence dissent,
- maintain openness.

The goal is for Ethics to be under constant pressure.
A highly ethical civilization should feel admirable but difficult to maintain under threat.

## 27. CRISIS AND DESPERATION

The original “debt / desperation” idea evolves into the Crisis card concept.
When a civ enters severe distress, it may generate Crisis cards or emergency actions.

These are:

- strong,
- dangerous,
- situational,
- often ethically costly,
- potentially run-saving.

This rewards skillful survival from bad states without making disaster desirable for its own sake.

## 28. MILITARY AND WAR

Military matters, but the game is not primarily a tactical combat simulator.

### Design direction

War should be strategic and eventful, not hyper-granular.

### Military uses

- defend against external threats,
- support colonization,
- reinforce allies,
- deter aggression,
- execute invasions,
- survive transition into late-game exposure.

### Internal wars / conquest

Some civs, especially low-Ethics or militarized ones, may push toward conquest or coercion.
These should usually emerge through:

- proposals,
- cards,
- crisis states,
- leader identity,
- relationship state.

Not every run should become a military sandbox.

## 29. MEGAPROJECTS

Megaprojects remain underdefined in final detail, but their role is now clear enough to state.

### What they are

Civilization-specific endgame commitments that act as:

- alternative or complementary win conditions,
- late-game investments,
- focal points for “against the clock” gameplay.

### Broad categories

Two broad styles are currently envisioned:

- Peaceful / transcendence / civilization-preserving
- Military / defensive / domination-oriented

### Baseline assumptions

Megaprojects likely require:

- minimum Age,
- strong Industry,
- sustained commitment,
- a relatively stable civ,
- protection from disruption.

They should vary in flavor by civilization, but need not yet be fully specified.

## 30. CIV DEATH

Civ death is not a full run-end by default.

### Effects of civ death

- loss of that civ’s productive potential,
- loss of its current trajectory,
- possible collapse of alliances or plans,
- transformation of some of its deck contribution into relic or neutralized forms,
- possible inheritance of unfinished megaproject progress by another civ,
- narrative and strategic shift in the run.

This keeps death meaningful without making the game too brittle.

## 31. META-PROGRESSION

Meta-progression still exists between runs.

### Two broad tracks

- Card unlocks: deeper card pools for specific civ templates or archetypes
- Civ template unlocks: new species combinations, keywords, gimmicks, and project flavors

### Unlock triggers

- reaching new Ages,
- surviving specific threat types,
- completing megaprojects,
- winning with certain doctrines,
- discovering special paths.

The meta layer should deepen replayability without invalidating the core roguelite tension.

## 32. DIFFICULTY SYSTEM

Difficulty is now strongly tied to threat ecology, not just numbers.

Difficulty can tune:

- baseline pressure speed,
- primary and secondary threat combination,
- Noise sensitivity,
- scarcity,
- event harshness,
- civ stability,
- amount of information available about threats,
- forgiveness around Synthesis and intervention.

This is preferable to simple stat inflation because it changes strategic demands, not just punishment level.

## 33. UI / PRESENTATION PRINCIPLES

A major concern from the original brief remains valid:
the game must not become a spreadsheet.

### Core rule

Each civilization should be legible from one compact panel.
Each civ panel should prominently show:

- Age
- Science progress
- Population
- Resources
- Industry
- Ethics
- Military
- one or two current status warnings
- one pending proposal or event

### Main screen emphasis

The main screen should prioritize:

- current hand,
- Energy,
- Synthesis,
- active threats,
- civ panels,
- telegraphed events,
- major transit operations.

The player should feel like they are reading a living cluster under pressure, not auditing a dashboard.

## 34. WHAT HAS BEEN EXPLICITLY REMOVED OR CHANGED

This section is here to ensure the revised brief truly replaces the old one.

### Removed

- The requirement to play at least 1 card per active civ each turn
- Mana as a primary spendable civ currency system
- The assumption of up to 10 active civilizations
- Overly explicit pairwise numerical diplomatic tracking as a central mechanic
- The idea that Noise alone defines the strategic problem

### Changed

- Active civ maximum is now effectively 4
- Energy is the main per-turn action currency
- Synthesis is retained as a rare global intervention / race-seeding currency
- Civ stats are persistent state variables, not mana pools
- Most cards are now primarily civ-owned and civ-targeted by default
- Multiple threat archetypes now exist
- Ethics is now intended to be a real temptation axis
- Deck manipulation is now recognized as essential
- Diplomacy is more abstract and partially driven by civ proposals
- FTL is more clearly a deliberate, high-risk threshold rather than just another age unlock

## 35. NEXT DESIGN TASKS

With this brief updated, the next practical design steps are:

### 35.1 Lock the exact stat model

Confirm whether the final launch stat set is:

- Science
- Population
- Resources
- Industry
- Ethics
- Military

and decide whether any secondary hidden values are needed.

### 35.2 Write the exact turn sequence in mechanical detail

A one-page formal turn structure.

### 35.3 Define 3 initial threat archetypes in detail

For each: what they punish, how they advance, what reveals them, what counters them.

### 35.4 Define 3–4 starting civ templates

Including:

- keywords,
- starting stats,
- starting cards,
- diplomatic instincts,
- likely leader directions.

### 35.5 Define the first 30–50 cards

Across:

- CIV
- MIL
- DECK
- SPACE
- LEADER
- TRADE
- CRISIS

### 35.6 Define first-contact and FTL transition event structures

These are core emotional beats and should be prototyped early.

## 36. ONE-SENTENCE GAME DEFINITION

A multi-civilization sci-fi roguelite strategy game where you guide up to four alien societies through growth, contact, crisis, and cosmic threats, deciding which to accelerate, expose, coordinate, corrupt, or sacrifice in order to survive an increasingly hostile galaxy.

## Links

- [[Slay the Spire Clones - Genre Analysis]]
- [[innsmouth-cult-story]]
