# Astraeus-9 Sandbox

**Category:** Traffic & Host Analysis
**Difficulty:** Medium
**Points:** 300
**Files:** None
**Files:** app.py, requirements.txt, dockerfile, index.html (Docker)

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
- Recognising encoded data in unexpected places — config fields, POST bodies, DNS subdomains
- Chained decoding — knowing that Base64 output can itself be encoded
- ROT47 — a Caesar cipher variant operating on printable ASCII characters
- Distinguishing real flags from convincing red herrings
- Using CyberChef effectively for multi-step decoding

---

## Key Concepts

**ROT47:**
ROT47 is a Caesar cipher that operates on all 94 printable ASCII characters (codes 33–126), shifting each by 47 positions. Unlike ROT13 which only affects letters, ROT47 also shifts numbers and symbols. Applying it twice returns the original — it is its own inverse.

**Chained encoding:**
Attackers frequently chain multiple encoding layers — XOR then Base64, ROT47 then Base64, hex then Base64. The first decode step produces something that still looks encoded. The key insight is to keep going rather than assuming the output is wrong.

**DNS tunnelling:**
Encoding data inside DNS subdomains is a real exfiltration technique. The subdomain field can carry up to 63 characters per label — enough for meaningful data payloads. Regular DNS traffic monitoring rarely inspects subdomain content for encoded data.

**Malware configuration extraction:**
Modern sandboxes extract malware configuration from process memory during execution. RC4 keys, C2 endpoints, and target lists are all recoverable this way. The RC4 key in particular is critical — in real investigations it can be used to decrypt captured C2 traffic.

---

## Notes

The three flag fragments were hidden in three completely different sections
of the sandbox report — config, network HTTP, and network DNS.

A participant who only looked at one or two sections would find at most
one or two parts and have no way to assemble the flag.

The fake flags in downloadable files were designed to reward
impatient analysts who downloaded everything first and looked for
obvious strings — sending them down a path that looks right but leads nowhere.

The real investigation required reading every section of the sandbox report
carefully, the same way a real malware analyst would work through an ANY.RUN report.