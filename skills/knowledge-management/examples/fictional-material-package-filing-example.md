# Fictional Material Package Formal Filing Example

This is a sanitized fictional example. It contains no real customer, project, contract, quotation, personal contact, bank, or local path information.

## Source Package

| File | Fictional Role | Material Type | Handling |
|---|---|---|---|
| `<SOURCE_ARCHIVE>/example-smart-campus/project-brief.md` | Main source | Project material | Use as project context |
| `<SOURCE_ARCHIVE>/example-smart-campus/technical-architecture.md` | Supporting source | Technical material | Use for architecture and risks |
| `<SOURCE_ARCHIVE>/example-smart-campus/commercial-scope.xlsx` | Attachment source | Business material | Use only for scope boundary; no real price |

## Type Decision

| Item | Decision |
|---|---|
| Primary material type | Project material package |
| Secondary material types | Technical, business, method |
| Topic note type | Project note with technical and business boundaries |
| Resource index | Yes |
| Knowledge cards | Yes, only if reusable across scenarios |
| Card types | Method card, risk card, scenario card |
| MOC handling | Attach to existing domain MOC if available |
| Merge / duplicate check | Required before writing |

## Formal Outputs

- `Example Smart Campus-Project Note-YYYYMMDD.md`
- `Example Smart Campus-Resource Index-YYYYMMDD.md`
- `Reusable Smart Campus Acceptance Checklist-Knowledge Card-YYYYMMDD.md`
- Attach outputs to `Example Digital Delivery-MOC-YYYYMMDD.md` if it exists.

## Quality Boundary

- Do not write process notes into formal artifacts.
- Do not create cards without cross-scenario reuse value.
- Do not copy raw source content into cards.
- Use `<SOURCE_ARCHIVE>` and other placeholders only.
