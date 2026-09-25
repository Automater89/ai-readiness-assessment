# Intake questionnaire

Copy this file into the working folder for the engagement and fill in answers and evidence inline.

> Tip: do not score while interviewing. Capture evidence first, score later against `rubric.md`.

---

## 1. Strategy & business case

1. What decision will this AI investment change? Who owns that decision?
2. What is the measurable target (cycle time, cost, error rate, satisfaction)? What is the current baseline?
3. Who is the executive sponsor? What have they personally committed (budget, time, air cover)?
4. What would cause us to *stop* — what are the no-go criteria?
5. How does this map to existing strategic priorities for the next 12 months?

## 2. Process maturity

1. Is there a current-state process map? When was it last updated?
2. What is the volume and cycle time of the target workflow?
3. What are the top exception types and how are they handled today?
4. Who can perform the work today, and how long does onboarding take?
5. Which steps are *judgment* vs *lookup* vs *transcription*? (AI buys the most leverage on the last two.)

## 3. Data readiness

1. What systems hold the data the AI will need?
2. Who owns each dataset? Is ownership documented?
3. What is the data classification? Is any of it regulated (PHI, PII, PCI, ITAR, export-controlled)?
4. Is the data accessible from the chosen AI surface today? (e.g., is the SharePoint library Copilot-indexed?)
5. What is the known quality posture — duplication, staleness, missing fields?

## 4. Platform & security

1. Identity posture: SSO, MFA, conditional access — coverage and exceptions?
2. DLP: what policies exist, what do they cover, what are the known gaps?
3. License entitlements: M365 Copilot, Power Platform premium connectors, Azure OpenAI access, Copilot Studio capacity?
4. Tenant configuration: are external sharing, guest access, and egress consistent with the workload's data classification?
5. What is the change-management posture for tenant-level configuration changes?

## 5. Governance & responsible AI

1. Is there a published AI use policy? Date of last review?
2. Is there a review board or equivalent approval path for AI workloads?
3. How are model and prompt changes controlled?
4. What is logged and for how long? Who can audit it?
5. What is the incident-response path for AI-specific failure modes (hallucination causing customer harm, data exfil via prompt, prompt injection)?

## 6. People & adoption

1. Who is sponsoring this outside of IT?
2. What is the communication plan?
3. What is the training plan? Who delivers it, on what cadence?
4. Who are the named champions in the target team?
5. What is the team's current change load? Are they absorbing other major changes in the same window?
6. How will adoption be measured? Is anyone measuring it today?
