# Signal in the Noise

**Category:** SOC Investigation
**Difficulty:** Medium
**Points:** 300
**Files:** app.py, requirements.txt, dockerfile, index.html (Docker)
**Prepared by:** Rafa Islam Diba

---

## Description

> The breach on Astraeus-9 generated thousands of log entries across multiple data sources.
>
> Somewhere in the noise, the attacker left a trace.
>
> You have been granted access to the station's Log Analytics workspace, the same interface used by ACFC analysts to investigate incidents in Microsoft Sentinel.
>
> Your job is not to browse incidents. Your job is to query the raw logs.
>
> Find what the attacker left behind.
>
> Flag Format: `ACFC{...}`

---

## Setup

This challenge is self-hosted via Docker.

```bash
# Extract the zip
unzip sentinel-kql.zip
cd sentinel-kql

# Build the image
docker build -t sentinel-kql .

# Run the container
docker run -p 5000:5000 sentinel-kql

# Open in browser
http://localhost:5000
```

---

## What This Tests

- KQL query syntax: filtering, summarizing, sorting
- Raw log investigation, not relying on pre-built alerts
- Identifying encoded data buried in metadata fields
- Understanding Windows Event IDs, specifically 4624 (successful logon)
- Recognising Base64 encoded strings that don't decode to expected values

---

## Key Concept

In real SOC work, the SIEM incident queue only shows what the analytics rules caught. Attackers who understand detection logic can sometimes operate below the threshold of existing rules. Raw log querying, hunting, is how analysts find what the rules missed.

The flag was not in any incident. It was in a raw log field that looked identical to dozens of other encoded references, the only way to find it was to query correctly and read carefully.

