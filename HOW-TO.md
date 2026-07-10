# SDLC Security Skills — Quick Guide

Six skills. One goal: catch security issues before they reach production.

---

## The Skills at a Glance

| When | Skill | What it does |
|------|-------|-------------|
| Planning a feature | `/sdlc-threat-model` | Finds attack vectors before you write code |
| Writing code | `/sast-advisor` | Spots vulnerabilities in your source code |
| Before committing | `/secrets-scanner` | Catches passwords and API keys in the code |
| Adding packages | `/dependency-audit` | Checks libraries for CVEs and supply chain risks |
| Opening a PR | `/secure-code-review` | Full security gate — approves or blocks the merge |
| Releasing | `/sbom-audit` | Generates a component inventory and checks integrity |

---

## How to Use Any Skill

1. Type the skill name (e.g. `/sast-advisor`)
2. Paste your code, file, or describe your feature
3. Read the report and act on it

That's it.

---

## Quick Examples

**Found a suspicious package?**
```
/dependency-audit

[paste your package-lock.json or requirements.txt]
```

**About to commit a config file?**
```
/secrets-scanner

[paste the file content]
```

**Reviewing a PR?**
```
/secure-code-review

[paste the git diff or changed files]
```

**Starting a new feature?**
```
/sdlc-threat-model

Building a login flow with email + password.
Stack: Node.js + PostgreSQL. Users: public internet.
```

---

## Recommended Order

```
Design → /sdlc-threat-model
Code   → /sast-advisor
Commit → /secrets-scanner + /dependency-audit
PR     → /secure-code-review
Ship   → /sbom-audit
```

Earlier = cheaper to fix.

---

## What the Reports Look Like

Each finding tells you:
- **What's wrong** (plain English, no jargon)
- **Where it is** (file + line number)
- **How to fix it** (ready-to-use code)
- **How urgent it is** (Critical / High / Medium / Low)

---

## The One Rule

> Run `/secrets-scanner` before every commit.
> Secrets in git history stay there forever, even after deletion.

---

*For the full technical reference, see the individual skill files in this folder.*
