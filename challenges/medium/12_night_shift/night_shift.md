# Night Shift

**Category:** SOC Investigation
**Difficulty:** Medium
**Points:** 300
**Files:** None
**Files:** app.py, dockerfile, requirements.txt, html templates (docker)
**Prepared by:** Rafa Islam Diba


---

## Description

> Station Astraeus-9 has been breached.
>
> You have been assigned as the on-call L1 analyst. The Sentinel queue shows 10 active incidents — not all of them matter. Some are noise. Some are connected. One tells a story.
>
> Your job is not just to find information. Your job is to work the incidents the way a real SOC analyst would.
>
> Triage. Investigate. Act.
>
> The flag is split across three parts. Each part is recovered by completing a specific analyst action in the correct incident. Collect all three parts and combine them.
>
> Flag Format: `ACFC{...}`

---

## What This Tests

- SOC L1 workflow: triage, classify, escalate
- Knowing the difference between True Positive, Benign Positive, and False Positive
- Understanding SOC escalation procedure, when the Client Info Sec Team is engaged
- Manual log and entity investigation, not every answer comes from an action panel
- Recognising encoded strings (hex and Base64) buried in legitimate-looking data

---

## Key Concepts

**Incident classification:**
- True Positive: the alert is real and the activity is genuinely malicious
- Benign Positive: the alert fired correctly but the activity is legitimate
- False Positive: the alert fired incorrectly

**Escalation rule:**
A Critical incident involving confirmed unauthorised access, lateral movement, or data exfiltration is a Major Security Incident. It must be escalated to the Client Info Sec Team, not L2, not Technology Team, not closed.

---

## Notes

The three incidents that matter are all connected, the same attacker,
the same source IP, moving through Astraeus-9 in sequence.

INC-2845 → INC-2847 (initial access) → INC-2851 (lateral movement) → INC-2863 (exfiltration)

Following this chain of events is how a real SOC analyst would investigate
an active breach, and it is the intended path through the challenge.
