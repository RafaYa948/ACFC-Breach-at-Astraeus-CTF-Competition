# ACFC: Breach at Astraeus-9

> *Station Astraeus-9 has gone dark. The ACFC Cyber Defence Unit has been deployed. That unit is you.*

An internal Capture the Flag (CTF) cybersecurity competition designed and hosted by the **Axiata Cyber Fusion Center (ACFC)** as a skill assessment initiative for SOC analysts and cybersecurity staff.

---

## Overview

| Detail | Info |
|---|---|
| **Event Name** | ACFC: Breach at Astraeus-9 |
| **Format** | Jeopardy-style CTF |
| **Duration** | 72 hours (26–28 April 2026) |
| **Platform** | CTFd Plus |
| **Flag Format** | `ACFC{...}` |
| **Total Challenges** | 15 across 5 categories |
| **Organised by** | Axiata Cyber Fusion Center — Cyber Defence Unit |

---

## Challenge Categories

### Category 1 — Open-Source & Entry Clues
| # | Challenge | Difficulty | Points | Description |
|---|---|---|---|---|
| 1 | Digital Footprint | Easy | 100 | OSINT — find a hidden trace on a professional network |
| 2 | Hidden in Plain Sight | Easy | 100 | Inspect the page source — not everything is visible |
| 3 | The Last Resort | Easy | 100 | MCQ — SOC escalation procedure knowledge |

### Category 2 — Hidden Data & Access
| # | Challenge | Difficulty | Points | Description |
|---|---|---|---|---|
| 4 | Layered Transmission | Medium | 250 | Multi-layer steganography across 5 images |
| 5 | Cracked | Medium | 200 | Hash cracking, file forensics, and XOR decoding |
| 6 | SuperGPT | Hard | 400 | Malicious browser extension analysis and reverse engineering |

### Category 3 — Traffic & Host Analysis
| # | Challenge | Difficulty | Points | Description |
|---|---|---|---|---|
| 7 | Operation Lockdown: Network | Medium | 100 | PCAP analysis with Wireshark |
| 8 | Operation Lockdown: Memory | Hard | 100 | Memory forensics with Volatility |
| 9 | Operation Lockdown: Malware | Hard | 100 | Malware analysis with VirusTotal |

### Category 4 — SOC Investigation
| # | Challenge | Difficulty | Points | Description |
|---|---|---|---|---|
| 10 | Night Shift | Hard | 300 | Mock Microsoft Sentinel — SOC L1 workflow, flag split across 3 incidents |
| 11 | Signal in the Noise | Hard | 200 | KQL Log Analytics workspace — find evidence in raw log data |

### Category 5 — Attack Techniques
| # | Challenge | Difficulty | Points | Description |
|---|---|---|---|---|
| 12 | Terminal Override | Medium | 400 | Binary analysis — strings, XOR decoding, ELF execution |
| 13 | Station Breach | Hard | 400 | SQL injection with WAF bypass and blind SQLi |
| 14 | HELIOS | Easy | 50 | MCQ — ACFC organisational knowledge |
| 15 | Know Your Enemy | Easy | 50 | MCQ — Red team methodology knowledge |

---

## 🏗️ Repository Structure

```
astraeus9-ctf/
├── README.md
├── challenges/
│   ├── 01-digital-footprint/
│   ├── 02-hidden-in-plain-sight/
│   ├── 03-layered-transmission/
│   │   └── files/
│   ├── 04-cracked/
│   │   └── files/
│   ├── 05-supergpt/
│   │   └── files/
│   ├── 06-terminal-override/
│   │   └── files/
│   ├── 07-station-breach/
│   │   └── docker/
│   ├── 08-operation-lockdown/
│   │   └── files/
│   ├── 09-night-shift/
│   │   └── docker/
│   ├── 10-signal-in-the-noise/
│   │   └── docker/
│   └── mcq/
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
    └── astraeus9-icon.svg
```

---

## Docker Challenges

Three challenges are hosted as Docker containers deployed via CTFd Plus:

| Challenge | Image | Port |
|---|---|---|
| Station Breach (SQLi) | `registry.ctfd.io/astraeusctf/acfc-sqli` | 5000 |
| Night Shift (Sentinel v3) | `registry.ctfd.io/astraeusctf/acfc-sentinel-v3` | 5000 |
| Signal in the Noise (KQL) | `registry.ctfd.io/astraeusctf/acfc-sentinel-kql` | 5000 |

### Running locally

```bash
# Station Breach
cd challenges/07-station-breach/docker
docker build -t acfc-sqli .
docker run -p 5000:5000 acfc-sqli

# Night Shift
cd challenges/09-night-shift/docker
docker build -t acfc-sentinel-v3 .
docker run -p 5000:5000 acfc-sentinel-v3

# Signal in the Noise
cd challenges/10-signal-in-the-noise/docker
docker build -t acfc-sentinel-kql .
docker run -p 5000:5000 acfc-sentinel-kql
```

---

## 🛠️ Tools Required

Participants were expected to have the following tools available:

| Tool | Use Case |
|---|---|
| Kali Linux / WSL2 | Primary investigation environment |
| Wireshark / tshark | Network traffic analysis |
| Volatility 3 | Memory forensics |
| steghide | Steganography extraction |
| exiftool | Metadata analysis |
| strings / xxd | Binary and file analysis |
| John the Ripper (snap) | Password hash cracking |
| python3 | Scripting and decoding |
| node + crypto-js | JavaScript challenge tooling |
| VirusTotal | Malware intelligence |

---

## 📚 Pre-Event Briefing Packs

Six daily briefing packs were distributed to participants in the week before the event:

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

##  Write-Ups & Solutions

Official challenge write-ups and solutions are **not publicly available** in this repository.

If you would like access to the official solutions — for learning purposes, security research, or academic use — please reach out directly:

📧 **contact@rafaislamdiba.com**

Please include your name and the reason for your request. Write-ups from event participants may also be shared upon request.

---


---

## 🏢 About ACFC

The **Axiata Cyber Fusion Center (ACFC)** is the cybersecurity operations centre of Axiata Group Berhad, protecting telecom networks, digital banking systems, fintech platforms, and critical infrastructure across 12 countries in the Asia Pacific region.

ACFC is home to the **HELIOS** platform — a patented heuristic engine for threat detection, attribution, and operational security — Malaysia's first cybersecurity patent by a government-linked company.

[Learn more about ACFC](https://www.axiatacfc.com)

---

## Disclaimer

All challenge files, scenarios, and infrastructure in this repository are created for **educational and internal assessment purposes only**. The incidents, IP addresses, account names, and organisations referenced are entirely fictional and do not represent real events.

The malware samples referenced in Operation Lockdown challenges are sourced from publicly available forensics lab repositories (CyberDefenders) and are used strictly for educational analysis.

---

*ACFC Cyber Defence Unit · Axiata Cyber Fusion Center · 2026*
