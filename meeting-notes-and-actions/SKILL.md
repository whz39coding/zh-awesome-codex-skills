---
name: meeting-notes-and-actions
description: 把会议转写或粗略笔记整理成清晰摘要，包含决策、风险和带负责人的行动项。适用于 Zoom/Meet/Teams 转写、电话记录或长会议聊天。Keywords: meeting notes, action items, summary.
metadata:
  short-description: Meeting transcript to notes and actions
---

# Meeting Notes & Actions

Process transcripts into structured notes and action items.

## Inputs to ask for
- Source: pasted transcript/text or file path; meeting title/date; attendees and their handles.
- Output style: terse bullets vs. narrative, action-item format, due date/owner tags, redaction rules if any.

## Workflow
1) Normalize text: strip timestamps/speaker labels if noisy; lightly clean filler words; keep quoted statements intact.
2) Extract essentials: agenda topics, key decisions, open questions, risks/blocked items.
3) Action items: who/what/when. Convert vague asks into concrete tasks; propose due dates if missing.
4) Produce output:
   - Header with meeting title, date, attendees.
   - Sections: `Summary`, `Decisions`, `Open Questions/Risks`, `Action Items` (checkboxes with owner + due).
5) Quality checks: ensure names are consistent; no hallucinated facts; flag ambiguities as clarifying questions.

## Optional extras
- Include timeline of major moments if timestamps exist.
- Provide short Slack/Email-ready blurb (2–3 sentences) plus the full notes.
