# AI Readiness Assessment

A structured, recruiter-facing framework for evaluating whether an enterprise team, department, or workflow is ready to adopt AI — and what to fix before it is.

> **Author:** Wes Shelton — IT Project Manager (AI enablement, process improvement, automation, Power Platform, enterprise workforce adoption).
> **Status:** Portfolio artifact. Designed to be picked up and run against a real business unit in under a week.

---

## The business problem

Most enterprise AI initiatives stall in the same place: leadership commits to "doing AI," IT is asked to deliver, and within a quarter the effort fragments into disconnected pilots that never reach production. The failure rarely comes from the model — it comes from the operating environment around it:

- Process steps are undocumented, so there is nothing concrete to automate.
- Data is fragmented across SharePoint, shared drives, and line-of-business systems with inconsistent ownership.
- Governance, risk, and change-management questions are deferred until the pilot is already running, then block rollout.
- The workforce is not prepared to change how they work, so adoption flatlines after launch.

This repository provides a **diagnostic instrument** a PM or transformation lead can use *before* a build investment — to surface the gaps, scope the remediation, and produce a defensible go / no-go recommendation.

## What this artifact proves

For a recruiter or hiring manager evaluating fit for an **IT Project Manager — AI Enablement** role, this repository demonstrates:

- The ability to translate an ambiguous executive ask ("are we ready for AI?") into a structured, repeatable assessment.
- Familiarity with the operating-model dimensions that actually drive AI adoption: process maturity, data readiness, governance, security, change management, and platform fit.
- Comfort positioning Microsoft 365 / Power Platform / Copilot as the realistic delivery surface for most mid-market and enterprise rollouts.
- A bias toward measurable outcomes, written communication, and stakeholder-ready deliverables — not just technical artifacts.

## Tech stack and delivery surface

| Layer | Choice | Why |
| --- | --- | --- |
| Assessment instrument | Markdown questionnaire + scoring rubric (`assessment/`) | Portable, version-controlled, reviewable in a PR |
| Reporting | Markdown report template, optional export to PDF/DOCX | Works inside any enterprise document-control workflow |
| Automation surface (recommended) | Microsoft Power Platform — Power Automate, Dataverse, Power BI | Aligns with where most target organizations already license and govern AI |
| AI delivery surface (recommended) | Microsoft 365 Copilot, Copilot Studio, Azure OpenAI | Same identity, DLP, and compliance perimeter the target organization already runs |
| Source control / collaboration | Git + GitHub | Treats the assessment itself as a reviewable artifact, not a one-off deck |

The assessment is platform-neutral; the *recommendations it produces* assume a Microsoft-centric enterprise because that is the realistic delivery surface for the roles this artifact is positioned against.

## AI / workflow pattern

This is a **human-in-the-loop assessment workflow**, not an autonomous agent. The pattern is deliberately conservative:

1. **Structured intake** — fixed questionnaire across six readiness dimensions (see `assessment/dimensions.md`).
2. **Evidence capture** — every score is anchored to an artifact (a process map, a data-classification record, a policy reference). Unsupported scores are flagged.
3. **Optional AI-assisted synthesis** — a Copilot / Azure OpenAI prompt set (`prompts/`) summarizes evidence into an executive narrative. The PM remains accountable for every number that lands in the final report.
4. **Recommendation** — a go / fix-then-go / no-go decision with a sequenced remediation plan.

The pattern matches how AI is actually being adopted in regulated and risk-aware enterprises: AI accelerates the analyst, but a named human signs the report.

## Business outcome (what a stakeholder gets)

Rather than claim invented metrics, this artifact targets credible, defensible outcomes:

- A signed-off readiness score across six dimensions, with evidence per score.
- A prioritized remediation backlog with owners, dependencies, and estimated effort.
- A clear recommendation on whether to invest in a build phase now, or to remediate first.
- A reusable baseline the same team can re-score against in 6–12 months to demonstrate progress.

Where this assessment has been useful in practice: replacing a *"let's just start building"* impulse with a 1–2 week diagnostic that either de-risks the build or reveals that the build was the wrong question.

## Architecture and workflow

```
        ┌──────────────────────────┐
        │ 1. Scoping conversation  │   ← stakeholder, scope, decision needed
        └─────────────┬────────────┘
                      ▼
        ┌──────────────────────────┐
        │ 2. Evidence intake       │   ← interviews, process maps, data inventory,
        │    (assessment/*.md)     │      policy refs, license posture
        └─────────────┬────────────┘
                      ▼
        ┌──────────────────────────┐
        │ 3. Scoring rubric        │   ← per-dimension 0–4 score + evidence link
        │    (assessment/rubric.md)│
        └─────────────┬────────────┘
                      ▼
        ┌──────────────────────────┐
        │ 4. AI-assisted synthesis │   ← Copilot / Azure OpenAI prompts
        │    (prompts/*.md)        │      summarize evidence; PM reviews and edits
        └─────────────┬────────────┘
                      ▼
        ┌──────────────────────────┐
        │ 5. Report + recommendation│  ← report/report-template.md
        │    go / fix-then-go / no-go│
        └──────────────────────────┘
```

The six readiness dimensions:

1. **Strategy & business case** — is there a named decision this will change?
2. **Process maturity** — is the target workflow documented well enough to automate?
3. **Data readiness** — ownership, quality, classification, accessibility.
4. **Platform & security** — identity, DLP, tenant posture, license entitlements.
5. **Governance & responsible AI** — policy, review board, risk acceptance, audit trail.
6. **People & adoption** — sponsorship, change capacity, training, success metrics.

## Setup and demo

This is a documentation-first artifact — no runtime, no secrets, no install.

```bash
# Clone
git clone https://github.com/Automater89/ai-readiness-assessment.git
cd ai-readiness-assessment

# Read the framework
$EDITOR assessment/dimensions.md   # the six readiness dimensions
$EDITOR assessment/rubric.md       # 0–4 scoring rubric with anchors
$EDITOR assessment/questionnaire.md# the intake questions, organized by dimension
$EDITOR prompts/synthesis.md       # AI-assisted executive-summary prompt
$EDITOR report/report-template.md  # the deliverable a stakeholder receives
```

**To run the assessment against a real team:**

1. Copy `assessment/questionnaire.md` into a working folder for the engagement.
2. Conduct interviews and capture evidence inline — one file per dimension is fine.
3. Apply `assessment/rubric.md` per dimension. Flag any unsupported scores.
4. (Optional) Paste anonymized evidence into the `prompts/synthesis.md` prompt in Copilot or Azure OpenAI to draft the executive narrative.
5. Fill in `report/report-template.md` and walk the sponsor through it.

## Governance and responsible AI

Because this artifact will often be used as the *first* AI conversation an organization has with itself, the framework opinionates on a few things on purpose:

- **No model output ships unreviewed.** AI synthesis is a drafting aid; the PM owns the report.
- **No customer or employee data in prompts.** The synthesis prompts assume anonymized evidence summaries, not raw transcripts.
- **Tenant-resident AI preferred.** The recommended delivery surface (Copilot, Azure OpenAI in-tenant) keeps data inside the existing compliance perimeter rather than introducing a new one.
- **Evidence is auditable.** Every score links to a document, a system-of-record, or a named interview — so the recommendation can be defended in a steering committee.
- **Bias toward reversibility.** The output is a recommendation and a backlog, not an irreversible commitment to a vendor or architecture.

These constraints exist because in regulated environments (healthcare, financial services, government-adjacent), the *governance* questions kill more pilots than the *technology* questions do.

## Recruiter-friendly positioning

If you are evaluating this repository for an IT Project Manager, AI Program Manager, or Digital Transformation Lead role, the signal here is:

- **PM discipline applied to AI.** Structured intake, evidence-based scoring, defensible recommendation, sequenced backlog.
- **Enterprise realism.** Power Platform / Copilot / Azure as the assumed delivery surface — not greenfield, not vendor-of-the-month.
- **Adoption-first thinking.** People and change management are first-class dimensions, not an afterthought.
- **Governance fluency.** Responsible AI, DLP, identity, and audit posture are treated as scope, not friction.
- **Written communication.** This README is the artifact a stakeholder would actually receive.

Wes Shelton — open to IT PM / AI Enablement roles. The contents of this repository are intentionally generic so they can be adapted to any organization's terminology and tooling.

## Suggested screenshots / demo assets

If extending this repository for an interview loop, the following would strengthen the narrative — none of which exist in this commit yet and all of which should be sourced from synthetic or sanitized engagements only:

- A filled-in `report/report-template.md` for a fictional company, with redacted evidence links.
- A Power BI screenshot of a readiness scorecard across the six dimensions.
- A Power Automate flow diagram showing how the intake questionnaire could be operationalized as a Microsoft Forms → Dataverse → report-generation flow.
- A short Loom-style walkthrough (5–7 min) narrating one dimension end-to-end.

## Repository layout

```
.
├── README.md                       ← this file
├── assessment/
│   ├── dimensions.md               ← the six readiness dimensions
│   ├── rubric.md                   ← 0–4 scoring anchors
│   └── questionnaire.md            ← intake questions per dimension
├── prompts/
│   └── synthesis.md                ← AI-assisted executive-summary prompt
├── report/
│   └── report-template.md          ← stakeholder deliverable template
└── LICENSE
```

## License

MIT. See [LICENSE](LICENSE). Use this framework on a real engagement — attribution appreciated, not required.
