# Ticket Trouble

**Category:** SOC Investigation
**Difficulty:** Medium
**Points:** 300
**Files:** None
**Files:** app.py, requirements.txt, dockerfile, index.html (Docker)
**Prepared by:** Rafa Islam Diba


---

## Description

> Something went wrong during the Astraeus-9 incident response.
>
> A critical ticket was mishandled — closed prematurely without proper investigation, and the evidence suggests it was not an accident.
>
> You have been assigned to review the response queue and pick up where the previous analyst left off.
>
> Do your job properly. Follow the correct procedure.
> The system rewards analysts who do things right.
>
> Flag Format: `ACFC{...}`

---

## What This Tests

- SOC L1 ticket workflow — Pick Up → Classify → Close
- Incident classification — identifying True Positive vs False Positive
- Reading ticket data carefully — not just the description but every field
- Recognising encoded data in metadata fields that look like system references
- Hex and Base64 decoding
- Understanding that tampering with notes leaves an audit trail

---

## Key Concepts

**Ticket workflow:**
In a real ServiceDesk environment, an L1 analyst must pick up unassigned tickets, investigate, classify, and close them with the correct resolution code. Skipping any step or using the wrong classification is a procedural failure — and in this challenge, returns an error.

**Note Edit History:**
Most ticketing systems log all edits to notes — the original content, the edited content, who changed it, and when. A deleted or modified note is not gone — it is in the audit trail. This is how insider threats and negligent analysts are caught in real SOC environments.

**Resolution codes matter:**
Closing a Critical security incident as anything other than "Security Incident Confirmed" is incorrect procedure — and in this challenge the system rejects it. Real SOCs use resolution codes to feed reporting and metrics — wrong codes distort incident data.

---

