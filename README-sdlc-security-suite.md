# SDLC Security Skills Suite

A suite of 6 skills covering the complete secure software development lifecycle (Secure SDLC), with a focus on supply chain attacks.

## SDLC Stage → Skill Map

```
DESIGN        →  /sdlc-threat-model      Threat modeling before writing code
CODE          →  /sast-advisor           Static analysis (OWASP Top 10, CWE)
CODE          →  /secrets-scanner        Hardcoded credential detection
DEPENDENCIES  →  /dependency-audit       CVEs, typosquatting, supply chain
PR / REVIEW   →  /secure-code-review     PR gate: logic + ASVS + IaC
BUILD/RELEASE →  /sbom-audit             SBOM, integrity, compliance
```

## Recommended Flow

```
1. [DESIGN]   /sdlc-threat-model   → identify threats before writing code
2. [CODE]     /sast-advisor        → analyze code as you develop
3. [CODE]     /secrets-scanner     → scan for credentials before committing
4. [DEPS]     /dependency-audit    → verify added or updated dependencies
5. [PR]       /secure-code-review  → final review before merge
6. [RELEASE]  /sbom-audit          → generate and validate SBOM before distribution
```

## Framework Coverage

| Framework / Standard | Skills covering it |
|---------------------|-------------------|
| OWASP Top 10 2021 | sast-advisor, secure-code-review |
| OWASP ASVS 4.0 | secure-code-review |
| OWASP Dependency Check | dependency-audit |
| STRIDE | sdlc-threat-model |
| SLSA (Supply Chain Levels) | sbom-audit |
| SPDX / CycloneDX | sbom-audit |
| NTIA SBOM Minimum Elements | sbom-audit |
| EO 14028 (US Cyber EO) | sbom-audit |
| NIS2 Art. 21 | sbom-audit |
| GDPR / LGPD (PII) | secrets-scanner, sdlc-threat-model |
| CWE Top 25 | sast-advisor, secure-code-review |

## Supply Chain Attack Coverage

| Attack Vector | Skill(s) |
|--------------|---------|
| Package typosquatting | dependency-audit |
| Dependency confusion | dependency-audit, sbom-audit |
| Compromised maintainer | dependency-audit, sbom-audit |
| Backdoored package (XZ-style) | dependency-audit, sbom-audit |
| CI/CD pipeline compromise | sdlc-threat-model, secure-code-review |
| Tampered artifact (MITM) | sbom-audit |
| Credentials in code/history | secrets-scanner |
| CVEs in transitive dependencies | dependency-audit, sbom-audit |
| Malicious postinstall script | dependency-audit |
| Compromised container base image | sbom-audit |
