# Repository Structure and Ownership

## Purpose

This repository separates decisions and project records from application code and automated tests. Each artifact should have one clear home and owner.

| Path | Purpose | Primary owner |
| --- | --- | --- |
| `docs/requirements/` | Scope, functional requirements, acceptance criteria, and constraints | Frontend Lead with team input |
| `docs/architecture/` | Architecture decisions, structure, and technical guidance | Solution Architect |
| `docs/ui-ux/` | Wireframes, prototypes, assets, and design rationale | UI/UX Designer |
| `docs/meetings/` | Agendas, minutes, decisions, and action items | Meeting facilitator |
| `docs/testing/` | Test strategy, manual cases, QA rules, and results | QA Engineer |
| `docs/reports/` | Sprint, progress, and final reports | Team |
| `tests/` | Automated test code and fixtures | Developers and QA Engineer |
| `.github/` | Collaboration templates and GitHub configuration | Frontend Lead |

The frontend implementation directories are intentionally not prescribed yet. The Frontend Developer should propose a conventional structure that matches the chosen technology, explain it in the pull request, and keep generated dependencies out of Git.

## Documentation rules

- Use Markdown for text documentation.
- Use `YYYY-MM-DD-short-title.md` for dated meeting and report files.
- Link prototypes or exported images from a short Markdown index in `docs/ui-ux/`.
- Record architecture decisions before or alongside major structural changes.
- Never store secrets, credentials, or private personal information in the repository.
