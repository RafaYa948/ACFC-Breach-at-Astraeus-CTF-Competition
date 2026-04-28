# The Last Resort

**Category:** Open-Source & Entry Clues
**Difficulty:** Easy
**Points:** 50
**Files:** None

---

## Description

> Understanding how your SOC operates is just as important as the technical skills you bring to it.
>
> Based on ACFC's SOC Operation model, when does escalation to the Client's Info Sec Team occur?
>
> * Immediately after the SIEM platform correlates and generates an alert, triggering the escalation workflow automatically
> * Once the SOC team has completed post incident analysis and the Report & Dashboard has been produced and distributed
> * Only when the Incident Responder determines that the event constitutes a Major Security Incident requiring elevated response
> * After the Client's Technology Team has attempted remediation and formally requested additional support from the Info Sec Team

---

## What This Tests

- Knowledge of the ACFC SOC escalation model
- Understanding the difference between automated alerting and deliberate analyst-driven escalation
- Knowing when the Client Info Sec Team is involved vs the Client Technology Team

---

## Key Concept

In a real SOC workflow, escalation paths are clearly defined:

- **L1 Analyst** handles triage, classification, and initial investigation
- **L2 Analyst** handles deeper investigation and containment
- **Client Technology Team** handles remediation of affected systems
- **Client Info Sec Team** is engaged when the incident is confirmed as a **Major Security Incident** — an active breach, confirmed lateral movement, or data exfiltration

The decision to escalate to the Client Info Sec Team is always made by the Incident Responder based on severity — it is never automatic and never delayed until after remediation.

---

## Notes

The answer is grounded in the ACFC SOC Operation model diagram shared
during the pre-event briefing. Day 6 briefing covered the escalation
procedure in detail, participants who read the materials had a
significant advantage on this question.