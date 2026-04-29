# Operation Lockdown: Memory

**Category:** Traffic & Host Analysis
**Difficulty:** Medium
**Points:** 300
**Files:** app.py, requirements.txt, dockerfile, index.html (Docker)
**Prepared by:** Rafa Islam Diba

---

## Description

> A memory dump was captured from ASTRS-WKS-014 at 02:15:44 UTC — 71 seconds after the attacker gained access to the station.
>
> The dump has been loaded into the Volatility analysis environment.
>
> Your job is to investigate what the attacker did after gaining access. Find the evidence they left behind in memory.
>
> Not everything in memory is what it appears to be. Some paths lead nowhere. Follow the correct chain of evidence.
>
> Flag Format: `ACFC{...}`

---

## Setup

This challenge is self-hosted via Docker.

```bash
# Extract the zip
unzip memdump-sim.zip
cd memdump-sim

# Build the image
docker build -t memdump-sim .

# Run the container
docker run -p 5000:5000 memdump-sim

# Open in browser
http://localhost:5000
```

---

## What This Tests

- Memory forensics fundamentals: process tree analysis
- Identifying process masquerading, wrong parent-child relationships
- Understanding legitimate vs suspicious process behaviour
- Network connection analysis from memory
- Extracting and decoding encoded strings from process memory
- Patience: filtering signal from noise across hundreds of strings

---

## Key Concepts

**Process masquerading:**
Attackers frequently rename malware binaries to match legitimate Windows process names (`svchost.exe`, `lsass.exe`, `explorer.exe`). The parent process is the giveaway, legitimate svchost is always a child of `services.exe`.

**Reflective DLL injection:**
Loading a DLL with `InInit: False` means it bypassed the normal Windows loader. This is a common technique for in-memory malware that leaves minimal disk artifacts.

**C2 beaconing:**
Regular outbound connections to a single external IP on a non-standard port (`4443` instead of `443`) at consistent intervals is a classic C2 beacon pattern.

---

## Available Commands Reference

```
windows.info
windows.pslist
windows.pstree
windows.cmdline
windows.cmdline --pid <PID>
windows.netstat
windows.netscan
windows.malfind
windows.malfind --pid <PID>
windows.dlllist
windows.dlllist --pid <PID>
windows.filescan
windows.hashdump
windows.strings
windows.strings --pid <PID>
windows.dumpfiles --pid <PID>
windows.registry.hivelist
windows.registry.printkey
```

---

