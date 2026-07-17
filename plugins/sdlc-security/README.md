# Plugin: sdlc-security

Security skills for Claude Code covering the full secure software development lifecycle, with a focus on supply chain attacks.

## Installation

### 1. Add the marketplace

```bash
/install marketplace ciandt-copilot/Skills_Sec
```

### 2. Install the plugin

```bash
/install plugin sdlc-security
```

## Skills

| Skill | Stage | What it does |
| --- | --- | --- |
| `/sdlc-threat-model` | Design | Threat modeling before writing code (STRIDE) |
| `/sast-advisor` | Code | Static analysis — OWASP Top 10, CWE Top 25 |
| `/secrets-scanner` | Pre-commit | Detects hardcoded credentials and API keys |
| `/dependency-audit` | Dependencies | CVEs, typosquatting, supply chain risks |
| `/secure-code-review` | PR Gate | Full security review with formal merge verdict |
| `/sbom-audit` | Release | SBOM generation, integrity check, compliance |

## Usage

After installing, invoke any skill by name in a Claude Code session:

```text
/sdlc-threat-model
/sast-advisor
/secrets-scanner
/dependency-audit
/secure-code-review
/sbom-audit
```

## Recommended flow

```text
Design  →  /sdlc-threat-model
Code    →  /sast-advisor  +  /secrets-scanner
Deps    →  /dependency-audit
PR      →  /secure-code-review
Release →  /sbom-audit
```

Earlier = cheaper to fix.

## Coverage

**Standards & Frameworks:** OWASP Top 10 2021, OWASP ASVS 4.0, CWE Top 25, STRIDE, SPDX 2.3 / CycloneDX 1.5, SLSA, EO 14028, NIS2 Art. 21, NTIA Minimum Elements.

**Supply chain vectors:** typosquatting, dependency confusion, compromised maintainer (XZ-style), backdoored packages, CI/CD compromise, tampered build artifacts, transitive CVEs, malicious postinstall scripts.
