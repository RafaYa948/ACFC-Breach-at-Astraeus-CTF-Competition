# Echoes in the Signal

**Category:** Traffic & Host Analysis
**Difficulty:** Hard
**Points:** 500
**Files:** `crew_entertainment_log.pcap`

---

## Description

> Long-range monitoring systems aboard the Astraeus have detected an unusual burst of encoded traffic hidden within civilian communication channels.
>
> At first glance, the transmissions appear harmless — routine browsing activity from a crew member during off-duty hours. Harmless distractions… entertainment… noise.
>
> But Astraeus Intelligence suspects otherwise.
>
> Buried within the stream lies a covert exchange — masked, fragmented, and intentionally obscured within legitimate traffic.
>
> One keyword keeps resurfacing in the logs: "youtube.com"
>
> This is no coincidence. The signal is believed to contain an exfiltrated payload, hidden in plain sight.
>
> Flag Format: `ACFC{...}`

---

## What This Tests

- PCAP analysis with Wireshark
- Reading HTTP Host headers carefully
- Recognising Base64 encoded strings in unexpected locations
- ROT47 decoding
- Following clues across multiple packets
- Distinguishing real data from deliberate red herrings

---
