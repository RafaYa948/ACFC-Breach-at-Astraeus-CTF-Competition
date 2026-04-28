# ACFC: Breach at Astraeus-9

> *Station Astraeus-9 has gone dark. The ACFC Cyber Defence Unit has been deployed. That unit is you.*

An internal Capture the Flag (CTF) cybersecurity competition designed and hosted by the **Axiata Cyber Fusion Center (ACFC)** as a skill assessment initiative for SOC analysts and cybersecurity staff.

---

## 📋 Overview

| Detail | Info |
|---|---|
| **Event Name** | ACFC: Breach at Astraeus-9 |
| **Format** | Jeopardy-style CTF |
| **Duration** | 72 hours (26–28 April 2026) |
| **Platform** | CTFd Plus |
| **Flag Format** | `ACFC{...}` |
| **Total Challenges** | 21 across 3 difficulty tiers |
| **Organised by** | Rafa Islam Diba & Ahnaf Masdi |

---

## Challenge Categories

### Easy — 100pts (MCQ: 50pts)

| # | Challenge | Points | Description |
|---|---|---|---|
| 1 | The First Recon | 100 | OSINT — find a hidden trace on the ACFC LinkedIn page |
| 2 | Know Your Enemy | 50 | MCQ — Red team methodology and APT simulation |
| 3 | The Encoded Dispatch | 100 | Multi-layer encoding — Base64, binary, MD5 hash lookup |
| 4 | Suspicious Email | 100 | Email header forensics — find the flag in the Return-Path field |
| 5 | Hidden in Plain Sight | 100 | Web inspection — flag hidden in the HTML page title tag |
| 6 | Station Intelligence | 50 | MCQ — ACFC HELIOS platform knowledge |
| 7 | The Last Resort | 50 | MCQ — SOC escalation procedure knowledge |
| 8 | 404 | 100 | Logic challenge — the answer is not where you expect it |

### Medium — 300pts

| # | Challenge | Points | Description |
|---|---|---|---|
| 9 | Layered Transmission | 300 | Multi-layer steganography across 5 images using steghide and exiftool |
| 10 | Terminal Override | 300 | Binary analysis — strings, XOR decoding, ELF execution |
| 11 | Night Shift | 300 | Mock Microsoft Sentinel — SOC L1 workflow, flag split across 3 incidents |
| 12 | Signal in the Noise | 300 | KQL Log Analytics workspace — find evidence buried in raw log data |
| 13 | Operation Lockdown: Memory | 300 | Memory forensics simulation — Volatility 3 command chaining |
| 14 | Ticket Trouble | 300 | Mock ServiceDesk Plus — SOC ticket workflow, flag revealed by correct procedure |
| 15 | Station Breach | 300 | SQL injection with WAF bypass and blind SQLi on a Flask/SQLite portal |
| 16 | Cracked | 300 | Hash cracking, password-protected zip, XOR decoding, string reversal |
| 17 | Astraeus 9 Sandbox | 300 | ANY.RUN-style sandbox analysis — Base64, ROT47, hex decoding across sections |
| 18 | Dead Commit | 300 | Git repository forensics — stash inspection and dangling commit recovery |

### Hard — 500pts

| # | Challenge | Points | Description |
|---|---|---|---|
| 19 | Whispering Signals | 500 | Audio steganography — hidden transmission in an intercepted audio file |
| 20 | SuperGPT | 500 | Malicious browser extension analysis — AES decryption, XOR, split key recovery |
| 21 | Echoes in the Signal | 500 | PCAP forensics — covert channel hidden in HTTP Host headers, Base64 and ROT47 |

---

## Docker Challenges

Six challenges are hosted as interactive Docker containers:

| Challenge | Docker Image | Description |
|---|---|---|
| Night Shift | `acfc-sentinel-v3` | Microsoft Sentinel replica — SOC L1 incident workflow |
| Signal in the Noise | `acfc-sentinel-kql` | KQL Log Analytics workspace |
| Operation Lockdown: Memory | `acfc-memdump` | Volatility 3 terminal simulation |
| Ticket Trouble | `acfc-sdp` | ManageEngine ServiceDesk Plus replica |
| Station Breach | `acfc-sqli` | Flask/SQLite portal with WAF |
| Astraeus 9 Sandbox | `acfc-anyrun` | ANY.RUN sandbox analysis replica |

### Running locally

```bash
# Example — Night Shift
cd challenges/night-shift/docker
docker build -t acfc-sentinel-v3 .
docker run -p 5000:5000 acfc-sentinel-v3
```

---

## Repository Structure

```
astraeus9-ctf/
├── README.md
├── challenges/
│   ├── easy/
│   │   ├── 01-the-first-recon/
│   │   ├── 02-know-your-enemy/
│   │   ├── 03-the-encoded-dispatch/
│   │   ├── 04-suspicious-email/
│   │   ├── 05-hidden-in-plain-sight/
│   │   ├── 06-station-intelligence/
│   │   ├── 07-the-last-resort/
│   │   └── 08-404/
│   ├── medium/
│   │   ├── 09-layered-transmission/
│   │   ├── 10-terminal-override/
│   │   │   └── files/
│   │   ├── 11-night-shift/
│   │   ├── 12-signal-in-the-noise/
│   │   ├── 13-operation-lockdown-memory/
│   │   ├── 14-ticket-trouble/
│   │   ├── 15-station-breach/
│   │   ├── 16-cracked/
│   │   ├── 17-astraeus9-sandbox/
│   │   └── 18-dead-commit/
│   └── hard/
│       ├── 19-whispering-signals/
│       ├── 20-supergpt/
│       └── 21-echoes-in-the-signal/
├── infrastructure/
│   ├── ctfd-config/
│   └── docker/
├── briefings/
│   ├── day1-linux-fundamentals.docx
│   ├── day2-osint-web.docx
│   ├── day3-phishing-malware.docx
│   ├── day4-crypto-stego.docx
│   ├── day5-network-forensics.docx
│   └── day6-incident-response.docx
├── writeups/
│   └── README.md
└── assets/
```

---

## Tools Required

| Tool | Use Case |
|---|---|
| Kali Linux / WSL2 | Primary investigation environment |
| Wireshark / tshark | Network traffic analysis (Echoes in the Signal) |
| steghide | Steganography extraction (Layered Transmission) |
| exiftool | Metadata analysis (Layered Transmission) |
| strings / xxd | Binary and file analysis (Terminal Override, SuperGPT) |
| John the Ripper | Password hash cracking (Cracked) |
| python3 | Scripting, XOR/hex decoding |
| node + crypto-js | JavaScript AES decryption (SuperGPT) |
| CyberChef | Multi-layer encoding/decoding |
| git | Repository forensics (Dead Commit) |
| docker | Running self-hosted challenges locally |

---

## Pre-Event Briefing Packs

Six daily briefing packs were distributed in the week before the event:

| Day | Topic |
|---|---|
| Day 1 | Linux Fundamentals |
| Day 2 | OSINT & Web Investigation |
| Day 3 | Phishing & Malware Analysis |
| Day 4 | Cryptography & Steganography |
| Day 5 | Network & Host Forensics |
| Day 6 | Incident Response & Exploitation |

All briefing documents are available in the `/briefings` directory.

---

## Write-Ups & Solutions

Official challenge write-ups and solutions are **not publicly available** in this repository.

To request access, for learning, security research, or academic purposes:

📧 **ritzshere948@gmail.com**

Please include your name and reason for the request.

---

## Team

| Role | Name |
|---|---|
| Event Organiser & Challenge Designer | Rafa Islam Diba |
| Challenge Co-Designer & Technical Support | Ahmad Ahnaf Bin Masdi |

---

## About ACFC

The **Axiata Cyber Fusion Center (ACFC)** is the cybersecurity operations centre of Axiata Group Berhad, protecting telecom networks, digital banking systems, fintech platforms, and critical infrastructure across 12 countries in Asia Pacific.

ACFC is home to the **HELIOS** platform — a patented heuristic engine for threat detection, attribution, and operational security — Malaysia's first cybersecurity patent by a government-linked company.

[Learn more about ACFC](https://www.axiatacfc.com)

---

## Disclaimer

All challenge files, scenarios, and infrastructure in this repository are created for **educational and internal assessment purposes only**. All incidents, IP addresses, account names, and organisations referenced are entirely fictional and do not represent real events.

---

*ACFC Cyber Defence Unit · Axiata Cyber Fusion Center · 2026*
