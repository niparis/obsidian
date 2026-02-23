# Draft — Agentic Maturity Roadmap (v1)

Date: 2026-02-23
Status: Draft from voice note
Owner: Nicolas

## Core thesis
Most enterprise discussions about agentic AI are too binary: "agent" vs "not agent."  
A more useful frame is a **maturity roadmap** where each level delegates different decision power to AI, and therefore requires a different governance model.

---

## Maturity model (v1)

### Level 1 — Tool-selection agency
**What the AI does:** selects tools/functions/data sources to complete a task.  
**Decision power delegated:** low (execution routing, not business decisions).  
**Example:** agent chooses whether to query DB, call search API, or run a classifier.

**Primary risk:** execution errors, wrong tool choice, incorrect retrieval.  
**Governance need:** technical observability.
- Tool call traces
- Input/output logs
- Latency/cost/error monitoring
- Basic quality checks on outputs

---

### Level 2 — Decision-and-action agency
**What the AI does:** interprets context, makes a decision, and triggers action in a target system.  
**Decision power delegated:** medium to high.

**Example:** analysis of documents leads to an automated decision pushed into an operational system.

**Sub-levels:**
- **2A (low-impact action):** limited business/financial impact
- **2B (high-impact action):** material financial, legal, customer, or operational consequences

**Primary risk:** incorrect decisions with delayed or hidden consequences.  
**Governance need:** outcome observability (not just technical traces).
- Action-to-outcome linkage
- Delayed correctness tracking (hours/days/weeks)
- Human review loops for ambiguous/high-risk cases
- Decision auditability and rollback paths

---

### Level 3 — Iterative/autonomous optimization agency
**What the AI does:** repeatedly plans and executes toward an objective over time (scheduled/heartbeat loops), potentially improving its own workflow/system around a target function.  
**Decision power delegated:** very high.

**Example pattern:** recurring cycles of research, implementation, evaluation, and adjustment toward a defined objective.

**Primary risk:** compounding errors, goal drift, unsafe self-optimization, and governance blind spots.  
**Governance need:** multi-layer control architecture.
- Explicit objective and boundary constraints
- Multi-stage verification/checkpoints
- Sandboxing and permission tiering
- Change controls for self-modifying workflows
- Continuous oversight with escalation paths

Note: Level 3 sub-levels still need design (v2).

---

## Strategic implication for enterprises
The value of this model is **governance-rightsizing**:
- avoid over-governing Level 1 use cases,
- avoid under-governing Level 2/3 use cases.

In other words: governance investment should follow delegated decision power, not the hype label "agentic AI."

---

## Structured post draft (LinkedIn/X long post style)
Agentic AI is not one thing. It has levels.

Level 1 is tool-selection agency: the AI chooses which functions and data sources to use. Useful, but limited decision power.

Level 2 is decision-and-action agency: the AI makes a judgment and pushes an action into a business system. This should be split into low-impact (2A) and high-impact (2B) actions.

Level 3 is iterative autonomy: the AI runs in recurring loops toward an objective, potentially improving its own process over time.

The governance mistake is treating these levels the same.

At Level 1, technical observability is often enough.
At Level 2, you need outcome observability and delayed correctness tracking.
At Level 3, you need layered control architecture, boundaries, verification gates, and escalation paths.

If we don’t separate these levels, enterprises will over-invest where risk is low and under-invest where risk compounds.

---

## Literature pass (Reddit / LinkedIn / X + supporting references)

### Reddit signals (community/operator perspective)
1. https://www.reddit.com/r/AI_Agents/comments/1psxz64/predictions_for_agentic_ai_in_2026/
   - Useful quote (preview): governance is hard without runtime control and explainability of why actions happened.
2. https://www.reddit.com/r/Observability/comments/1pq49fd/observing_ai_agents_logging_actions_vs/
   - Useful quote (preview): logs show *what* happened, not necessarily *why* an agent chose a path.
3. https://www.reddit.com/r/SaaS/comments/1pisfea/enterprise_ai_infrastructure_whats_actually_hard/
   - Useful quote (preview): enterprises end up needing deterministic audit trails, not just probabilistic model narratives.

### LinkedIn signals (operator/executive framing)
1. https://www.linkedin.com/posts/andrewyng_announcing-my-new-course-agentic-ai-building-activity-7381380126317404160-wW75
   - Useful quote (preview): building agentic systems requires disciplined evaluation and feedback.
2. https://www.linkedin.com/posts/allansendagi_practices-for-governing-agentic-ai-systems-activity-7155227295207559168-zRMN
   - Notes: references baseline responsibilities and safety practices in agentic AI lifecycle.
3. https://www.linkedin.com/posts/vikram-murali-40878112_agentic-ai-in-observability-building-resilient-activity-7396266501722312704-bELA
   - Notes: observability-centric framing for resilient/accountable systems.

(LinkedIn preview limits apply; many posts are partially gated.)

### X signals (faster trend pulse)
1. https://x.com/AndrewYNg/status/1981056313661559155
   - Useful quote (preview): governance pillars include lifecycle, risk, security, and observability.
2. https://x.com/Gartner_inc/status/1964336055731077243
   - Useful quote (preview): agentic adoption requires clear business value and robust governance.
3. https://x.com/csisfutures/status/2016541810235986248/photo/1
   - Useful quote (preview): definitional confusion around agentic AI weakens governance and oversight.

### Supporting long-form references (stronger conceptual anchor)
1. CSIS: https://www.csis.org/analysis/lost-definition-how-confusion-over-agentic-ai-risks-governance
   - Key contribution: argues for capability-based taxonomy to match authority, accountability, and evaluation.
2. MIT Sloan Management Review: https://sloanreview.mit.edu/projects/the-emerging-agentic-enterprise-how-leaders-must-navigate-a-new-age-of-ai/
   - Key contribution: adoption is outpacing strategy; decision rights and accountability models lag.

---

## What this literature adds to the roadmap
1. **Validates your core framing**: ambiguity in the term "agentic AI" creates governance mismatch.
2. **Supports Level 1 vs Level 2 distinction**: many sources separate logging/traceability from actual decision-quality governance.
3. **Supports delayed correctness point (Level 2)**: outcome observability is repeatedly described as harder than technical telemetry.
4. **Strengthens Level 3 argument**: as autonomy increases, governance must shift from tooling telemetry to control architecture + authority boundaries.

---

## Publication-ready angle options from this literature
1. "Agentic maturity is really a decision-rights ladder"
2. "Most teams have agent traces, not agent governance"
3. "Outcome observability is the missing layer between demo and production"
4. "The governance failure starts with fuzzy definitions"

---

## Major consultancies scan (McKinsey, Accenture, BCG, KPMG + Deloitte/PwC)

### McKinsey
- https://www.mckinsey.com/capabilities/people-and-organizational-performance/our-insights/the-agentic-organization-contours-of-the-next-paradigm-for-the-ai-era
  - Proposes an "agentic organization" model with pillars including business model, operating model, governance, workforce/culture, and technology/data.
- https://www.mckinsey.com/capabilities/quantumblack/our-insights/seizing-the-agentic-ai-advantage
  - Emphasizes autonomy levels, decision boundaries, monitoring, and audit mechanisms.

### Accenture
- https://www.accenture.com/us-en/insights/consulting/rethinking-it-operating-models
  - Frames enterprise-level governance/funding for AI-agent deployment across functions.
- https://www.accenture.com/content/dam/accenture/final/accenture-com/document-4/Accenture-The-New-Rules-of-Platform-Strategy-in-the-Age-of-Agentic-AI.pdf
  - Platform-strategy lens in the agentic era (useful for architecture + operating model framing).

### BCG
- https://www.bcg.com/publications/2025/agents-accelerate-next-wave-of-ai-value-creation
  - Highlights cross-functional governance, outcome/risk monitoring, and "freedom within a frame."
- https://www.bcg.com/publications/2025/machines-that-manage-themselves
  - Leadership/management implications for increasingly autonomous systems.

### KPMG
- https://kpmg.com/us/en/articles/2025/ai-governance-for-the-agentic-ai-era.html
  - Strong governance-centric framing and agent categorization concepts.
- https://kpmg.com/us/en/articles/2025/deploying-ai-agents.html
  - Introduces TACO framework (Taskers, Automators, Collaborators, Orchestrators), very relevant to your maturity-level idea.

### PwC
- https://www.pwc.com/us/en/tech-effect/ai-analytics/responsible-ai-agents.html
  - Responsible AI framing for autonomous enterprise workflows.
- https://www.pwc.com/us/en/tech-effect/ai-analytics/ai-observability.html
  - Focus on AI observability as governance + performance layer.

### Deloitte
- https://www.deloitte.com/us/en/what-we-do/capabilities/applied-artificial-intelligence/articles/agentic-ai-orchestration-governance.html
  - Orchestration + governance patterns as complexity grows.
- https://www.deloitte.com/us/en/insights/topics/technology-management/tech-trends/2026/agentic-ai-strategy.html
  - Notes traditional IT governance is insufficient for autonomous decision systems.

---

## What this consultancy scan confirms for your model
1. **Maturity/categorization is mainstream**: major firms already segment agent types/capabilities.
2. **Governance scales with autonomy**: consistent theme across firms (boundaries, oversight, audits, controls).
3. **Observability alone is insufficient at higher levels**: recurring shift toward outcome/risk monitoring and accountability.
4. **Your L1/L2/L3 framing is differentiated**: consultancies discuss categories broadly; your model is stronger on delegated decision rights + governance-rightsizing.

---

## Follow-up research tasks (next pass)
1. Find formal taxonomies from standards bodies/research (NIST, OECD, EU AI Act mapping where relevant).
2. Add 2-3 enterprise case studies per level (L1/L2/L3).
3. Build a one-page rubric: delegated decision rights vs required controls.
4. Gather concrete patterns for delayed-outcome evaluation windows (T+1 day, T+7 days, T+30 days).
5. Design Level 3 sub-levels (e.g., 3A bounded iteration, 3B self-modifying workflow, 3C multi-agent adaptive systems).
