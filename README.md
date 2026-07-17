# SDLC Security Skills Suite

> Security skills for Claude Code covering the full secure software development lifecycle, with a focus on supply chain attacks.

---

## What is this?

A suite of 6 skills that turn Claude Code into a security expert available at every step of software development. Each skill targets a specific phase of the SDLC — from design to release — so security issues are caught early, where they are cheapest to fix.

---

## Skills

| Skill | Stage | What it does |
|-------|-------|-------------|
| `/sdlc-threat-model` | Design | Threat modeling before writing code (STRIDE) |
| `/sast-advisor` | Code | Static analysis — OWASP Top 10, CWE Top 25 |
| `/secrets-scanner` | Pre-commit | Detects hardcoded credentials and API keys |
| `/dependency-audit` | Dependencies | CVEs, typosquatting, supply chain risks |
| `/secure-code-review` | PR Gate | Full security review with formal merge verdict |
| `/sbom-audit` | Release | SBOM generation, integrity check, compliance |

---

## How to Use

```
1. Type the skill name in Claude Code (e.g. /sast-advisor)
2. Paste your code, file content, or describe your feature
3. Read the report and act on the findings
```

**Recommended flow:**

```
Design  →  /sdlc-threat-model
Code    →  /sast-advisor  +  /secrets-scanner
Deps    →  /dependency-audit
PR      →  /secure-code-review
Release →  /sbom-audit
```

---

## Coverage

**Standards & Frameworks**
- OWASP Top 10 2021
- OWASP ASVS 4.0
- CWE Top 25
- STRIDE Threat Modeling
- SPDX 2.3 / CycloneDX 1.5 (SBOM)
- SLSA (Supply Chain Levels for Software Artifacts)
- EO 14028 · NIS2 Art. 21 · NTIA Minimum Elements

**Supply Chain Attack Vectors Covered**
- Package typosquatting
- Dependency confusion
- Compromised maintainer (XZ-style attacks)
- Backdoored packages
- CI/CD pipeline compromise
- Tampered build artifacts
- CVEs in transitive dependencies
- Malicious postinstall scripts

---

## File Structure

```
.claude-plugin/
└── marketplace.json
plugins/
└── sdlc-security/
    ├── .claude-plugin/plugin.json
    ├── README.md
    └── skills/
        ├── sdlc-threat-model/SKILL.md
        ├── sast-advisor/SKILL.md
        ├── secrets-scanner/SKILL.md
        ├── dependency-audit/SKILL.md
        ├── secure-code-review/SKILL.md
        └── sbom-audit/SKILL.md
```

---

## Getting Started

Install as a Claude Code marketplace — no cloning, no copying:

```bash
/install marketplace ciandt-copilot/Skills_Sec
/install plugin sdlc-security
```

Then run any skill with `/skill-name` in any project.

See [`plugins/sdlc-security/README.md`](plugins/sdlc-security/README.md) for the full plugin reference.
