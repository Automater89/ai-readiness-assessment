# The six readiness dimensions

Each dimension is scored 0–4 using `rubric.md`. Every score must cite at least one evidence artifact.

## 1. Strategy & business case

Does the organization know what decision an AI investment is supposed to change? Vague aspirations ("we want to do AI") score low; a named decision with a measurable target ("reduce contract-review cycle time on standard NDAs") scores high.

Look for: executive sponsor, stated business outcome, success metric, named no-go criteria.

## 2. Process maturity

Is the target workflow documented well enough that a reasonable person could automate part of it without re-interviewing every participant?

Look for: process maps, SOPs, exception-handling docs, volumes and cycle times. Undocumented tribal knowledge is a red flag.

## 3. Data readiness

Can the AI actually reach the data it needs, in a form it can use, without violating something?

Look for: data ownership, classification, quality posture, lineage, retention, accessibility from the chosen AI surface (e.g., is the SharePoint library indexed for Copilot? does Dataverse have the entities?).

## 4. Platform & security

Is the technical environment ready to host AI without opening new risk?

Look for: identity posture (SSO, MFA, conditional access), DLP coverage, tenant configuration, license entitlements (M365 Copilot, Power Platform, Azure OpenAI), network and egress controls.

## 5. Governance & responsible AI

Is there a defensible answer to "who approved this and how do we audit it?"

Look for: AI use policy, review board or equivalent, risk-acceptance process, model and prompt change-control, audit logging, incident-response path for AI-specific failure modes (hallucination, data exfil, prompt injection).

## 6. People & adoption

Is the workforce prepared to change how they work?

Look for: sponsorship beyond IT, communication plan, training plan, named champions, success metrics that measure *adoption* and not just *availability*, capacity to absorb change given everything else on the plate.
