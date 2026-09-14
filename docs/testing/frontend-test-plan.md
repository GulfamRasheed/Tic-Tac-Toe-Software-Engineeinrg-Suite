# Initial Frontend Test Plan

**Owner:** Gulfam Hashmi, QA Engineer

**Status:** Initial baseline; assigned for review and expansion at the September 12, 2026 kickoff meeting

## Objective

Verify that the first frontend implementation is usable and follows the basic Tic-Tac-Toe rules before it is merged into `main`.

## Test rules

- Test from a clean application start and record the tested commit or pull request.
- Record the browser, device or viewport, operating system, and result.
- Use `Pass`, `Fail`, or `Blocked` for every case; do not leave results ambiguous.
- For failures, create a reproducible bug report with expected behavior, actual behavior, steps, and evidence.
- Retest fixed defects and run relevant previous cases to detect regressions.
- Critical game-rule failures block release. Visual polish issues may be prioritized by the team unless they prevent use or accessibility.

## Baseline manual test cases

| ID | Scenario | Expected result |
| --- | --- | --- |
| FE-001 | Open the application | An empty 3-by-3 board appears and `X` is the current player. |
| FE-002 | Select an empty cell | The cell shows the current player's mark and the turn changes. |
| FE-003 | Select an occupied cell | The board and current turn remain unchanged. |
| FE-004 | Complete a winning row | The correct player is declared the winner and further moves are blocked. |
| FE-005 | Complete a winning column | The correct player is declared the winner and further moves are blocked. |
| FE-006 | Complete a winning diagonal | The correct player is declared the winner and further moves are blocked. |
| FE-007 | Fill all cells without a winner | The game displays a draw and further moves are blocked. |
| FE-008 | Use the restart control during or after a game | The board clears, the result resets, and `X` becomes the current player. |
| FE-009 | Navigate controls using a keyboard | Interactive controls can be reached and activated with a visible focus indicator. |
| FE-010 | View the game at mobile and desktop widths | The board and controls remain visible, readable, and usable without unintended overlap. |

## Automation priorities

Automate pure game-rule checks first: valid moves, turn alternation, occupied-cell rejection, all win combinations, draw detection, and reset behavior. UI-level automation can follow after the initial frontend structure is stable.
