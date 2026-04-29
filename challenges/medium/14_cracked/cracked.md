# Cracked

**Category:** Hidden Data & Access
**Difficulty:** Medium
**Points:** 300
**Files:** `ir_toolkit.py` · `ir_package_0x13.zip` · `ASTRS-2025-IR-0047.txt`
**Prepared by:** Rafa Islam Diba


---

## Description

> A recovery toolkit was found on one of Astraeus-9's compromised nodes during the investigation.
>
> Our analysts managed to retrieve two artifacts before the workstation was fully isolated. The toolkit appears to contain an encoded artifact, and somewhere inside the investigation package, a critical transmission was left behind.
>
> Your job is to find it.
>
> Flag Format: `ACFC{....}`

---

## What This Tests

- Running and reading Python script output
- Hex to ASCII decoding
- MD5 hash identification and cracking with John the Ripper
- Password-protected zip extraction
- Using `strings` to find hidden data in files
- Base64 decoding
- XOR decoding with a key hidden in a filename
- String reversal
- Chaining multiple encoding layers — no single tool solves this

---

## Key Concepts

**MD5 cracking:**
MD5 is a one-way hash function — it cannot be mathematically reversed. However common passwords have been pre-computed and stored in rainbow tables. John the Ripper uses a wordlist to hash each word and compare against the target hash.

**XOR key in the filename:**
The zip file was named `ir_package_0x13.zip` — the `0x13` is not random. Analysts who noticed this had a direct path to the XOR key. This is a real-world technique — attackers sometimes embed key material in filenames, comments, or metadata.

**String reversal:**
An additional obfuscation layer on top of XOR. The flag was reversed before encoding — so decoding gives a reversed string that must be flipped to get the real flag.

---
