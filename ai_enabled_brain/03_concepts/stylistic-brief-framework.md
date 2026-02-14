---
id: stylistic-brief-framework
type: concept
status: draft
tags: [mobile-poc, design-brief, process]
created: 2026-02-12
updated: 2026-02-12
---

# Stylistic Brief Framework for AI-Driven Builds
An AI-friendly brief must steer the impression without locking creativity. This framework sits alongside your functional and UI specs and keeps the mood–tone–anti-goal combo crystal clear for Codex.

## 1️⃣ Mood sentence (non-negotiable)
*“Calm, slightly mysterious, like a thoughtful puzzle you play at night.”* This sentence is the north star; nothing else contradicts it.

## 2️⃣ Adjective pairs
Primary tone:
- Minimal but not sterile
- Playful but not childish
- Calm but not dull
Pairs define boundaries the AI should respect.

## 3️⃣ Visual lineage (max 3 references)
- Monument Valley (clarity, spatial calm)
- Early iOS 6 skeuomorphism (material warmth without realism)
- Japanese puzzle books (white space, restraint)
References inform the vibe without copying layouts.

## 4️⃣ Rhythm, not decoration
Interaction rhythm:
- Animations slow-in, fast-out
- No flashing/strobing
- Feedback delayed ~100ms and subtle
Temporal cues beat static prettiness.

## 5️⃣ Color relationships
- One dominant neutral background for focus
- One accent color used sparingly for intent confirmation
- Motion communicates errors before color (supports low-light)

## 6️⃣ Typography personality
- Humanist, slightly rounded
- Numbers stable/readable
- No ultra-thin weights
If you name fonts (e.g., Inter), explain that it’s for neutrality, not branding.

## 7️⃣ Anti-goals
Avoid:
- Gamified visual noise (sparkles, bursts, confetti)
- Casino-like reward loops
- Mobile F2P tropes
These keep Codex from overfitting generic mobile patterns.

## 8️⃣ Emotional arc
- Main menu: calm, inviting
- Early gameplay: curious exploration
- Mid-run: focused intensity
- Failure: reflective, not punitive
This allows subtle phase shifts without chaos.

## 9️⃣ Style invariant
Nothing competes with the core action. If an element draws attention, it must justify it functionally.

## 10️⃣ Mini brief example
*“The game feels calm, cerebral, and quietly satisfying. Visuals are minimal but warm, playful but restrained. Motion is subtle and purposeful. The UI should feel like a tool, not a toy. Loud or reward-seeking visuals are out.”*

## Why this works for AI
- Adjective pairs shrink search space
- Mood anchors semantics
- Anti-goals prevent pattern sprawl
- Rhythm/emotion are easier than vague “beauty”

> Keep this note linked to your functional specs (see [[Dream Escape Workflow]]) so the narrative and the pile of prompts stay aligned.
