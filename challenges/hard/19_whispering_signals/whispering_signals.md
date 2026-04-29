# Whispering Signals 

**Category:** Network Forensics
**Difficulty:** hard
**Points:** 500
**Files:** Top_Secret_Space_Data.pcap (docker)
**Prepared by:** Ahmed Ahnaf

---

## Description

> While monitoring outbound communications from the ASTRAEUS vessel, our network defense system detected a faint, irregular transmission — too subtle to trigger standard alerts.
>
> The signal did not originate from any registered module.
> No crew member has claimed responsibility.
> Yet... something is talking.
>
> Initial analysis suggests the data is hidden within normal network traffic — disguised as harmless communication between onboard systems.
>
> Your task is to investigate the captured network traffic and uncover the hidden message before it reaches its destination.
>
> Flag Format: `ACFC{...}`

---

## What This Tests

- PCAP analysis — filtering and reading DNS traffic in Wireshark
- Pattern recognition — identifying anomalous subdomain labels within normal-looking traffic
- DNS exfiltration awareness — understanding how data can be encoded and hidden inside DNS queries
- Data transformation — reversing strings and concatenating in the correct order
- Base64 decoding — using CyberChef to recover the final message

---

## Key Concepts

**DNS Exfiltration:**
Attackers encode data into subdomain labels of DNS queries directed at domains they control. The queries are designed to blend into normal CDN and cloud traffic. Because DNS is rarely blocked at the firewall level, it makes an effective low-noise covert channel.

**Why It's Hard to Detect:**
Each individual query appears harmless. The payload is distributed across multiple domains. Without sorting, comparing, and spotting the entropy pattern, the signal is invisible in the noise.

**Entropy and Anomaly Detection:**
The subdomain strings like `9VmchX2` and `zl2XnFG` score high on entropy — they contain mixed case, numbers, and no real dictionary words. In a real SOC environment, high-entropy subdomain labels are a detection signal worth alerting on.

---

## Notes

The `UQ` segment from `static.UQ.amazon` was the shortest and easiest to miss — which is why the hint pointed there directly.
Participants who extracted only three of the four domains and attempted to decode early would have gotten garbage output. All four needed to be identified before the transformation step would produce anything meaningful.
The reversal step is the key non-obvious transformation — Base64 decoding the raw segments directly does not work. Order and reversal both matter.

---
