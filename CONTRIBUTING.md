# Contributing Guide

This guide defines how the team collaborates on the Tic-Tac-Toe Software Engineering Suite.

## Before starting work

1. Pull the latest `main` branch.
2. Create or select a GitHub issue with a clear owner and acceptance criteria.
3. Move the issue into the current sprint or team task list.
4. Create a branch from `main` using one of these formats:
   - `feature/<short-description>`
   - `fix/<short-description>`
   - `docs/<short-description>`
   - `test/<short-description>`

Example:

```bash
git switch main
git pull origin main
git switch -c feature/basic-game-board
```

Do not commit feature work directly to `main`.

## Making changes

- Keep each branch focused on one issue or deliverable.
- Put requirements in `docs/requirements/`, designs in `docs/ui-ux/`, meeting records in `docs/meetings/`, and test documentation in `docs/testing/`.
- Add application code only to the implementation folders agreed by the team.
- Add or update tests when behavior changes.
- Use clear commit messages written as commands, such as `Add basic game board` or `Document frontend test cases`.
- Never commit passwords, tokens, local environment files, generated caches, or editor settings.

## Pull requests

1. Update your branch with the latest `main`.
2. Run the relevant tests and perform a manual check.
3. Push the branch and open a pull request using the repository template.
4. Link the related issue and include screenshots for visual changes.
5. Request at least one teammate review.
6. Resolve review comments before merging.
7. Prefer squash merging so each completed task has a clear entry on `main`.

The pull request author must not approve their own work. The QA Engineer should review behavior-changing work when practical, and the Frontend Lead should review architecture-level changes.

## Versioning

The project uses Semantic Versioning: `MAJOR.MINOR.PATCH`.

- `MAJOR`: incompatible or fundamental product changes.
- `MINOR`: backward-compatible features, such as a new game mode.
- `PATCH`: backward-compatible fixes and small improvements.

During initial development, versions remain in the `0.x.y` range. The first usable development baseline will be `0.1.0`; the first stable release will be `1.0.0`.

For every release:

1. Move completed entries from `Unreleased` in `CHANGELOG.md` into a dated version section.
2. Commit the release notes.
3. Create an annotated Git tag, for example `v0.1.0`.
4. Push the commit and tag after approval.

## Agile workflow

The team follows a lightweight iterative workflow:

- Work is recorded as small issues with an owner, acceptance criteria, and status.
- The team chooses a short sprint goal and only commits work that can reasonably be completed in that sprint.
- Members share blockers early instead of waiting until the end of the sprint.
- Each work session ends with updated issue status and documentation where needed.
- At sprint review, the team demonstrates completed work against its acceptance criteria.
- At retrospective, the team records what worked, what did not, and one improvement for the next sprint.

Suggested issue states are `Backlog`, `Ready`, `In progress`, `In review`, and `Done`. Work is only `Done` when its acceptance criteria pass, documentation is updated, and the change is merged.

## Definition of done

A task is complete when:

- Its stated acceptance criteria are satisfied.
- Relevant tests pass.
- No known critical defect remains.
- Documentation and `CHANGELOG.md` are updated when applicable.
- A teammate has reviewed the pull request.
- The change has been merged into `main`.
