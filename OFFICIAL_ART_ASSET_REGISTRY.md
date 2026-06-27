# OFFICIAL_ART_ASSET_REGISTRY.md

Status: Review Draft

Purpose:

Establish the official registry for all approved artwork used throughout the project.

Only assets registered in this document are considered official visual references.

All other concepts, experiments and rejected artwork are non-authoritative.

---

## Asset Status

```text
Candidate
-> Review
-> Approved
-> Official Master Reference
-> Battlefield Adaptation
-> Sprite Production
```

---

## Official Asset Record

Each approved artwork should record:

- Asset Name
- Profession
- Promotion
- Version
- Approval Date
- Parent Reference
- Character Bible Version
- Battlefield Bible Version
- Artwork Specification Version
- Current Status

---

## Asset Naming Convention

Example:

```text
Guard_Master_V1
Guard_Master_V2
ShieldGuard_Master_V1
Knight_Master_V1
RoyalKnight_Master_V1
```

---

## Parent Chain

Every official artwork must record its parent.

Example:

```text
Guard_Master_V1
-> ShieldGuard_Master_V1
-> Vanguard_Master_V1
-> Knight_Master_V1
-> RoyalKnight_Master_V1
```

This chain must remain unbroken.

---

## Official Rule

Only artwork with Official Master Reference status may be used as:

- AI reference
- Promotion parent
- Battlefield adaptation source
- Sprite production source
- Style Reference Pack source

Candidate or rejected artwork must never enter the official chain.

---

## Archive Policy

```text
Rejected artwork
-> Archive

Approved artwork
-> Official Registry
```

Only one Official Master Reference may exist for each promotion.

---

## Registry Records

### Guard_Master_V1

| Field | Value |
|---|---|
| Asset Name | Guard_Master_V1 |
| Profession | Guard |
| Promotion | Promotion 1 |
| Version | V1 |
| Approval Date | 2026-06-26 |
| Parent Reference | None |
| Character Bible Version | Current Review Version |
| Battlefield Bible Version | Current Review Version |
| Artwork Specification Version | GUARD_MASTER_REFERENCE_ARTWORK_SPEC_V1.md |
| Production Sprint | PRODUCTION_SPRINT_01 |
| Review Result | PASS |
| Approved by User | Yes |
| Current Status | Official Master Reference |
| Official File | C:\Users\User\Documents\Codex\2026-06-24\workspace-c-users-user-documents-codex\output\production_sprint_01\Guard_Master_V1.png |

Freeze Reference:

`Guard_Master_V1` is frozen as the only approved parent reference for Shield Guard (Promotion 2).

No future Guard candidates may replace it unless the user explicitly requests a new revision cycle.

Reference Policy:

Future Guard-related artwork may use:

- Guard_Master_V1
- Character Bible
- Battlefield Bible
- Approved Artwork Specifications

Do not use:

- Candidate 01
- Candidate 02
- Historical rejected concepts
- Deprecated references

---

## Status Rule

Do not promote to Active Rule.

