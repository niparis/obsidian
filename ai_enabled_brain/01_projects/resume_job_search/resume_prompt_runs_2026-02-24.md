# Resume Prompt Runs — Nicolas Paris (2026-02-24)

## Run Metadata
- Timestamp (UTC): 2026-02-24 15:00
- Source prompts: `/home/nicolas/obsidian/ai_enabled_brain/01_projects/resume_job_search_prompts.md`
- Source resume: `/home/nicolas/obsidian/ai_enabled_brain/01_projects/resume_job_search/Nicolas_Paris_Resume_2026-02.pdf`
- Existing review: `/home/nicolas/obsidian/ai_enabled_brain/01_projects/resume_job_search/resume_review_2026-02-24.md`
- Constraint: No fabricated employers or roles

---

## Prompt 1 — Spot the Flaws
**Prompt text:** Act as a recruiter for [your industry/role]. Review my resume below and highlight weak areas, overused buzzwords, and missing metrics. Be brutally honest.

**Output (Recruiter lens: CTO / Head of AI):**
1. Headline is broad and fragmented (`CTO - SOFTWARE PLATFORMS & GEN AI`); better with searchable keywords and clean separators.
2. Summary is strong but overly dense with claims ("trusted by Fortune 500 leaders", "hallucination-free", "elite teams") and needs sharper proof-per-line.
3. Currency and metric formatting is inconsistent: `500k USD`, `$2M`, `7m$`, `1M ARR`, `400.000 MAU`.
4. Wording and naming inconsistencies reduce polish: `Asia Development Bank` vs `Asian Development Bank`; punctuation and spacing variations.
5. Additional Experience section underutilized (10 years collapsed to one line).
6. Some bullets are duty-like; need stronger result-first structure.
7. ATS keyword density can improve for AI leadership searches (LLM, RAG, MLOps, AI governance, enterprise SaaS, data platform, stakeholder management).

---

## Prompt 2 — Rewrite for Impact
**Prompt text:** Rewrite this resume to sound more results-driven, quantifiable, and compelling for [target role]. Focus on achievements, not just duties.

**Output (sample rewritten bullets):**
- Delivered 6 production GenAI products for the **Asian Development Bank** in 2024, totaling **US$2M** contract value, including RAG search, workflow automation, and document generation under cybersecurity and AI governance controls.
- Repositioned ADI from internal data science function to external AI consultancy, building project management, solution architecture, and pre-sales capabilities to support enterprise wins.
- Built DataPipes from MVP to commercial scale, reaching **US$500k ARR in 18 months** and **US$1M+ ARR by 2024** with lean investment.
- Defined ICP and role-based GTM messaging that drove **>50% close rate** and **US$7M total contract value** in 18 months.
- Led cloud reliability and DevSecOps modernization that sustained **99.99% uptime**.

---

## Prompt 3 — ATS Boost
**Prompt text:** Update this resume to be fully optimized for Applicant Tracking Systems (ATS) for the role of [specific role/title]. Use industry-specific keywords naturally.

**Output (target role: CTO / Head of AI):**
**Inserted/strengthened ATS keywords naturally in final rewrite:**
- Generative AI, LLM, RAG, AI governance, MLOps
- Enterprise SaaS, product engineering, platform engineering
- Cloud architecture, DevSecOps, CI/CD, observability, high availability
- Data platform, data engineering, machine learning in production
- GTM strategy, pre-sales, stakeholder management, cross-functional leadership
- Regulated industries (finance, healthcare), cybersecurity compliance

---

## Prompt 4 — Craft My Hook
**Prompt text:** Write a powerful, 3-line professional summary that hooks a recruiter in under 10 seconds. Prioritize impact, clarity, and value.

**Output (3-line hook):**
CTO and AI platform leader with 19 years of experience scaling enterprise products across finance and healthcare.
Delivered 6 production GenAI solutions for the Asian Development Bank in 2024 (US$2M total contract value), including RAG and workflow automation with up to 75% workload reduction.
Built and led engineering organizations that scaled products to US$1M+ ARR while maintaining up to 99.99% uptime in regulated environments.

---

## Prompt 5 — Upgrade Experience
**Prompt text:** Rephrase the experience section to highlight impact, results, and transferable skills using action verbs and quantifiable outcomes.

**Output (framework applied):**
- Bullets rewritten to start with strong action verbs: Delivered, Repositioned, Built, Defined, Led, Integrated, Scaled, Directed.
- Metrics normalized to recruiter-friendly style: **US$2M**, **US$500k**, **US$1M+ ARR**, **US$7M TCV**, **99.99% uptime**, **400k MAU**, **4.7 rating / 30,000+ reviews**.
- Scope and transferable leadership clarified: team growth, cross-functional influence, enterprise delivery, GTM impact, reliability ownership.

---

## Prompt 6 — Format Fix
**Prompt text:** Suggest a clean, modern resume format that works for both humans and ATS. No graphics, no columns. Just structured and effective.

**Output (format used in rewritten files):**
1. Name + target title + contact line
2. Professional Summary (3 lines)
3. Core Competencies (keyword-dense, single-line separators)
4. Professional Experience (reverse chronological)
   - Company | Location | Role | Dates
   - 4–6 bullet achievements per role
5. Additional Experience (concise narrative)
6. Education & Certifications

Formatting choices:
- One-column markdown, no tables, no icons
- Consistent date style and punctuation
- Consistent metric style using **US$**

---

## Prompt 7 — Tailor for the Role
**Prompt text:** Tailor this resume to fit this specific job description [paste JD]. Highlight matching experience and reword sections to match the language used.

**Output (role-targeted variants created):**
- **CTO version:** Emphasis on org leadership, platform strategy, reliability, P&L-adjacent commercial outcomes, and cross-functional GTM execution.
- **Head of AI / GenAI version:** Emphasis on production GenAI delivery, LLM/RAG deployment, governance, MLOps, and measurable AI adoption outcomes.

Files:
- `/home/nicolas/obsidian/ai_enabled_brain/01_projects/resume_job_search/Nicolas_Paris_Resume_2026-02_CTO.md`
- `/home/nicolas/obsidian/ai_enabled_brain/01_projects/resume_job_search/Nicolas_Paris_Resume_2026-02_Head_of_AI.md`

---

## Prompt 8 — Standout Cover Letter
**Prompt text:** Write a compelling cover letter based on this resume and job description. Keep it personal, enthusiastic, and under 200 words.

**Output (template, <200 words):**
Dear Hiring Manager,

I’m excited to apply for the [Role] opportunity. Over 19 years, I’ve led engineering and AI organizations across finance and healthcare, with a focus on turning complex technology into measurable business outcomes.

Most recently as CTO at ADI, I led delivery of six production GenAI solutions for the Asian Development Bank in 2024 (US$2M total contract value), including RAG search and workflow automation that reduced workload by up to 75%. Previously, I built and scaled cloud data products from MVP to US$1M+ ARR while maintaining 99.99% uptime in regulated environments.

I bring a blend of technical depth, product thinking, and commercial execution—from platform architecture and MLOps to GTM collaboration and enterprise delivery. I’m particularly motivated by roles where AI must be practical, governable, and trusted in production.

I would welcome the opportunity to discuss how my experience can help [Company] accelerate its [AI/platform/product] goals.

Sincerely,
Nicolas Paris

---

## Generated Artifacts in This Run
- `/home/nicolas/obsidian/ai_enabled_brain/01_projects/resume_job_search/resume_prompt_runs_2026-02-24.md`
- `/home/nicolas/obsidian/ai_enabled_brain/01_projects/resume_job_search/Nicolas_Paris_Resume_2026-02_rewritten.md`
- `/home/nicolas/obsidian/ai_enabled_brain/01_projects/resume_job_search/Nicolas_Paris_Resume_2026-02_CTO.md`
- `/home/nicolas/obsidian/ai_enabled_brain/01_projects/resume_job_search/Nicolas_Paris_Resume_2026-02_Head_of_AI.md`

---

## Decision Log — Preferred Tagline (2026-02-24 16:22 UTC)
- **Decision:** Use this exact tagline across all resume output variants: "CTO-level AI platform builder specialising in execution-grade transformation in complex environments."
- **Rationale:**
  - Aligns all resume variants to a single, recruiter-facing positioning statement.
  - Signals senior scope (CTO-level), AI platform depth, and execution focus in complex enterprise contexts.
  - Keeps ATS compatibility while preserving factual consistency with documented delivery outcomes.
