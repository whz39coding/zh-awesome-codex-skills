---
name: support-ticket-triage
description: 将客服 tickets/emails/chats 分诊为类别、优先级和下一步行动，起草回复并生成可复现步骤。适用于 Zendesk、Intercom、Help Scout 导出或粘贴的对话串。Keywords: support ticket, triage, customer support.
metadata:
  short-description: Categorize and respond to support tickets
---

# Support Ticket Triage

Standardize how to classify and respond to incoming tickets.

## Inputs to gather
- Ticket text (include attachments/links), product area, customer plan/tier if known.
- Desired outputs: category taxonomy, priority levels, SLA hints, tone/brand voice, whether to draft a reply.

## Workflow
1) Parse context: identify issue type, product surface, severity, customer impact, reproduction hints, and blockers.
2) Categorize: assign category and subcategory; set priority (e.g., P0–P3) with short justification.
3) Draft response (if asked): concise acknowledgment, empathy, restate issue, next steps, and ask for missing info; include reproduction checklist when uncertain.
4) Internal notes: suspected root cause, logs to pull, teams to loop, and tracking IDs to create/attach.
5) Output: tabular or bullet summary with `Category`, `Priority`, `Summary`, `Proposed Fix/Next Steps`, `Reply Draft`.

## Quality checks
- Avoid promises; give ranges not exact ETAs unless provided.
- Mask PII if copying to public channels.
- If signal is weak, present 2–3 likely categories and what evidence would disambiguate.
