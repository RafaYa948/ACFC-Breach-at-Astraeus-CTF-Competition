# Layered Transmission

**Category:** Hidden Data & Access
**Difficulty:** Medium
**Points:** 300
**Files:** `flag.jpg` · `flag1.jpg` · `flag2.jpg` · `maybe_this_is_the_flag.jpg` · `not_the_flag.jpg`

---

## Description

> Five satellite images were recovered from Astraeus-9's archive during the investigation. Our analysts believe one of them contains a hidden transmission, but nothing is ever as simple as it seems. Not every image holds a secret. Not every secret holds the flag. And not everything is what it appears to be.
>
> The signal was never meant to be read.
>
> Flag Format: `ACFC{....}`

---

## Files

| File | What it contains |
|---|---|
| `flag.jpg` | Steghide embedded file — `skibidi.txt` (no flag) |
| `flag1.jpg` | Exif metadata — contains both passphrases |
| `flag2.jpg` | Steghide embedded file — `l+ratio.txt` (contains encoded flag) |
| `maybe_this_is_the_flag.jpg` | Binwalk/strings — red herring message |
| `not_the_flag.jpg` | Nothing hidden — dummy image |

---

## What This Tests

- Metadata analysis with `exiftool`
- Steganography extraction with `steghide`
- Base64 decoding
- Patience — not every file contains useful data
- Reading the challenge description — *"not every image holds a secret"* is a direct hint that some images are decoys

---

## Notes

The key insight is that the passphrases for `flag.jpg` and `flag2.jpg`
are hidden in a completely different file — `flag1.jpg` — via exif metadata.
Participants who jumped straight to steghide without checking metadata
first would have been stuck guessing passphrases.

The correct investigation order is:
`exiftool` on all images first → find passphrases → then `steghide extract`.