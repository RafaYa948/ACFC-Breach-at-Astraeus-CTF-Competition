# Astraeus 9 Sandbox

**Category:** SOC Analysis
**Difficulty:** Medium
**Points:** 300
**Files:** None
**Platform:** Docker
**Prepared by:** Ahmad Ahnaf

---

## Description

> A suspicious executable was submitted for sandbox analysis during the Astraeus-9 investigation.
>
> File: upd8.exe
> MD5: 9F3A2B8C4D1E6F7A3B9C2D5E8F1A4B7C
> Family: AstraeausStealer
>
> The sandbox captured everything — process behaviour, network traffic, dropped files, registry modifications, and extracted malware configuration.
>
> The flag is not in one place. It never is.
>
> Investigate the report thoroughly. Use CyberChef to decode what you find.
>
> Flag Format: `ACFC{...}`

---

## What This Tests

- Sandbox report analysis — reading all sections methodically
- Recognising encoded data in unexpected fields — config keys, POST bodies, DNS subdomains
- Chained decoding — understanding that Base64 output can itself be encoded in another layer
- ROT47 — a Caesar cipher variant that operates on all printable ASCII characters including symbols
- Distinguishing real flags from convincing red herrings
- CyberChef proficiency — chaining multiple operations

---
