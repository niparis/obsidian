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

## Follow-up research tasks
1. Find literature/frameworks on AI autonomy levels and agent capability taxonomies.
2. Find governance literature on delayed-outcome decision systems.
3. Find operational patterns for human-in-the-loop at medium/high-risk decision points.
4. Collect case studies where technical observability was insufficient without outcome tracking.
5. Validate Level 3 governance patterns (control layers for iterative/self-improving agents).
