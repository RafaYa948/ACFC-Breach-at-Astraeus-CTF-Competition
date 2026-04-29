# Hidden in Plain Sight

**Category:** Open-Source & Entry Clues
**Difficulty:** Easy
**Points:** 100
**Files:** None
**Prepared by:** Ahmed Ahnaf
---

## Description

> This window was used for Astraeus-9 mission updates and it shows unusual behavior. Analysts suspect hidden data may exist within this window structure. Inspect the page elements to uncover concealed information.

---

## What This Tests

- Basic web inspection skills, using browser developer tools
- Understanding that web pages contain more data than what is visually rendered
- Reading challenge descriptions carefully, the hint is explicit

---

## Key Concept

The `<title>` tag defines the text shown in the browser tab. It is part of the page's HTML structure but is never displayed in the page body. Attackers and developers frequently leave sensitive information in HTML tags that are invisible to casual users: comments, title tags, meta tags, and hidden input fields are all common places to look during a web investigation.

---

## Notes

No tools beyond a browser are required.
Right-click → View Page Source is the fastest path.
The flag is visible immediately once you open the page source.
