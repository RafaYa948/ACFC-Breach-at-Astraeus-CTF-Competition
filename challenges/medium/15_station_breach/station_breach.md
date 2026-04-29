# Station Breach

**Category:** Attack Techniques
**Difficulty:** Medium
**Points:** 300
**Files:** None
**Files:** app.py, requirements.txt, dockerfile, index.html (Docker)
**Prepared by:** Rafa Islam Diba

---

## Description

> During the investigation of Astraeus-9, analysts discovered that the station's crew management portal is still accessible from the network.
>
> Intelligence suggests the portal may be vulnerable to exploitation. A successful breach could reveal classified transmission data left behind by the attacker.
>
> The portal has security measures in place. You will need to think carefully about how to get past them.
>
> Your mission:
> - Identify the vulnerability
> - Bypass the security controls
> - Access the classified data
> - Retrieve the flag
>
> Flag Format: `ACFC{...}`

---

## What This Tests

- SQL injection identification — recognising abnormal application behaviour
- WAF fingerprinting — understanding what is blocked and what is not
- WAF bypass techniques — comment injection, space removal, quote manipulation
- Blind boolean-based SQLi — extracting data without seeing output
- Database schema enumeration — querying sqlite_master
- Patience — blind SQLi requires methodical character-by-character extraction

---

## Key Concepts

**WAF Bypass — Space Removal:**
Many WAFs filter `OR 1=1` as a pattern but do not account for `OR'1'='1` with no spaces. SQL parsers accept both forms — the WAF does not.

**WAF Bypass — Comment Injection:**
SQL supports inline comments `/**/` between any tokens. `OR/**/1=1` is syntactically valid SQL but bypasses WAF rules that match `OR 1=1` with spaces.

**Blind Boolean SQLi:**
When the application returns no data but changes behaviour based on the query result, you can extract information by asking yes/no questions. A count of 7 means true. A count of 0 means false. Every piece of data in the database can eventually be extracted this way.

**sqlite_master:**
In SQLite databases, `sqlite_master` is a system table that contains the schema of the entire database — all table names, column definitions, and indices. Querying it reveals the full database structure without needing any prior knowledge.

---

## Notes

The challenge had two injection points — the login form and the search function.
The login form was used to bypass authentication via WAF bypass.
The search function was used to extract the flag via blind SQLi.

Neither injection point returned visible data — every piece of information
had to be inferred from the count returned by the search function.

Participants who tried to extract data from the login form directly
were on a dead end — the search function was the only path to the flag.
