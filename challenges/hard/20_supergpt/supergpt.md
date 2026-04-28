# SuperGPT

**Category:** Hidden Data & Access
**Difficulty:** Hard
**Points:** 500
**Files:** `extension_package.zip` (contains `manifest.json`, `app.js`, `crypto.js`, `loader.js`, `ui.html`, `gif.jpg`), `Tool.zip`, `Flag.zip`

---

## Description

> Following the events on Astraeus-9, investigators uncovered a suspicious browser extension installed on multiple compromised workstations within the station's network.
>
> Disguised as a lightweight AI assistant named "SuperGPT", the extension was widely adopted by crew members seeking quick computational assistance during operations. However, telemetry logs suggest that the tool was quietly harvesting sensitive inputs and transmitting them to an unknown external endpoint.
>
> During the containment process, analysts managed to recover:
> - The full extension package
> - A password-protected archive believed to contain exfiltrated data
>
> Your mission:
> - Analyse the extension's behaviour
> - Identify how data is collected and transmitted
> - Recover the hidden secret embedded within its operations
> - Use it to unlock the archive and retrieve the flag
>
> Flag Format: `ACFC{...}`

---

## What This Tests

- Browser extension analysis — reading JavaScript source files
- Base64 decoding across multiple files
- Key assembly — combining fragments from different sources
- AES-CBC decryption using Node.js and crypto-js
- File forensics — extracting a byte from the end of a binary file
- XOR decoding with a single-byte key
- Chaining multiple steps — output of each step feeds the next

---

## Key Concepts

**AES-CBC Decryption:**
AES in CBC (Cipher Block Chaining) mode requires both a key and an initialisation vector (IV). Both were hidden across different files — finding one without the other is insufficient. The `debug.js` tool handles the decryption but requires participants to supply both values themselves.

**XOR with single-byte key:**
XOR with a single byte is one of the simplest encodings — but only if you know the key. Hiding the key as the last byte of a GIF file requires knowing to check file bytes, not just readable strings.

**Split key recovery:**
Splitting a key across multiple files prevents any single-file analysis from recovering it. Both parts are needed — neither is useful alone.

---
