# AI-assisted synthesis prompt

Use this prompt with Microsoft 365 Copilot, Copilot Studio, or Azure OpenAI **after** the evidence has been captured and scored.

## Guardrails before you run it

- Paste only **anonymized** evidence summaries — no employee names, no customer identifiers, no raw transcripts.
- Use a tenant-resident model (M365 Copilot or Azure OpenAI in your tenant). Do not paste evidence into a consumer chat surface.
- The output is a **draft**. The PM owns every sentence that lands in the final report.

## Prompt

```
You are assisting an IT Project Manager preparing an AI Readiness
Assessment report for an executive sponsor.

I will give you, for each of six readiness dimensions, a score (0–4)
and a short bulleted evidence summary. Your job is to produce a
concise executive narrative.

For each dimension, write 2–3 sentences that:
- State the score and what it means in plain language.
- Reference the strongest piece of evidence.
- Name the single most important gap, if any.

Then write an overall summary (4–6 sentences) that:
- States the aggregate readiness in plain language.
- Names the 2–3 highest-impact remediation items.
- Gives a clear recommendation: go, fix-then-go, or no-go.

Rules:
- Do not invent metrics. If a number is not in the evidence, do not
  produce one.
- Do not soften governance findings. If governance is below 2, say so.
- Write for a non-technical executive. No jargon, no model names,
  no vendor names unless they appear in the evidence.

Evidence follows below.
---
[paste anonymized dimension-by-dimension evidence here]
```

## After the model responds

1. Read every sentence. Strike anything not supported by evidence.
2. Replace any softened governance language with the original finding.
3. Paste the edited narrative into `report/report-template.md`.
4. Save the prompt input, the raw model output, and your edits to the engagement folder for audit.
