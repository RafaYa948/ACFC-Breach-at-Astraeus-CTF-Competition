# Terminal Override

**Category:** Attack Techniques
**Difficulty:** Medium
**Points:** 300
**Files:** `astraeus_terminal` (ELF binary)

---

## Description

> A backup terminal aboard Astraeus-9 is still live. It is protected by an emergency access code. The terminal binary has been recovered from the station's systems. Analyse it. Find the code. Get in.
>
> Not all secrets need to be encrypted to be hidden.

---

## What This Tests

- Basic binary analysis — identifying file type with `file`
- Using `strings` to extract readable data from compiled binaries
- Recognising XOR encoding and decoding with a simple key
- Understanding that compiled binaries often leak sensitive data that developers intended to hide

