# UI/UX Prototypes — 2026-11-25

**Author:** Gulfam Rasheed, UI/UX Designer
**Status:** Ready for team review

## Prior style survey

Dated folders previously existing under `docs/ui-ux/`: **none** (only `prototype-guidelines.md` was present).
No visual style had been used yet, so both styles below are first use and mutually distinct:

| Prototype | Style | Board |
|---|---|---|
| `prototype-01.html` | Glassmorphism (frosted glass, dark gradient) | 3×3 |
| `prototype-02.html` | Retro pixel / arcade (chunky borders, 8-bit feel) | 4×4 variation |

Both files are self-contained single-file HTML with inline CSS and JS, no external dependencies, no images.

---

## prototype-01.html — Glassmorphism (3×3)

- **Layout choices:** Single centered frosted-glass card containing title, pill-shaped turn-status bar, the board, a Restart button, and a small X/O legend. The win/draw overlay covers only the board area so the status bar and legend stay visible.
- **Color palette:** Deep blue → violet → teal gradient background (`#1b2a6b`, `#5b2a8a`, `#0f7a8c`); translucent white glass surfaces (`rgba(255,255,255,0.14/0.24)`); X in cyan `#7df9ff`, O in pink `#ffd6f4`; focus ring yellow `#ffe066`.
- **Typography:** System sans stack (Segoe UI / system-ui). Bold uppercase small-caps subtitle, 700-weight status, 800-weight marks sized with `clamp()` for fluid scaling.
- **Interaction states:** *Normal* — translucent glass cell. *Hover* — brighter fill, lift `-3px`, drop shadow. *Focus* — 3px yellow `:focus-visible` ring with offset. *Selected/occupied* — mark colored + glow, cursor becomes default, click ignored. *Disabled* — all cells disabled after win/draw (cursor default); Restart button dims to 55% opacity when disabled. Winning line gets a pulsing highlight.
- **Accessibility:** Status uses `role="status"` + `aria-live="polite"` so turn/result changes are announced. Cells are real `<button>`s in a `role="grid"` (fully keyboard reachable, Enter/Space activates). Each cell has an `aria-label` like "Cell 2, 3, X". White text on dark saturated gradients and glowing marks exceed 4.5:1; yellow focus ring is high-contrast. Overlay focus moves to its New Game button on finish. `prefers-reduced-motion` disables animations.
- **Responsive behavior:** Card is `max-width: 460px` with 16px page padding; board uses `aspect-ratio: 1/1` cells and fluid `clamp()` type. Under 380px, padding/gaps shrink and cell radius reduces. Works down to ~320px width.
- **Question for the team:** Should the win overlay cover the whole card (more dramatic) or stay limited to the board area (keeps the status bar readable) as it is now?

---

## prototype-02.html — Retro Pixel (4×4 variation)

- **Layout choices:** "Arcade cabinet" card: dark marquee header with the title, status bar, bordered grid, Restart button, and a rules footer line. Overlay sits over the board with an arcade-style "insert coin" message. Uses a 4×4 board with **four-in-a-row** win logic as the variation.
- **Color palette:** Paper background `#f4f4e8` with a faint pixel-grid pattern; ink `#1a1c2c` for all 4px borders and hard offset shadows; accent yellow `#f7b32b`; X red `#e43b44`, O teal `#4b8f8c`; muted `#b9b7a8` for disabled.
- **Typography:** Monospace stack (Courier New) throughout, uppercase with wide letter-spacing for headings, status, buttons, and rules — reinforces the 8-bit tone. Marks are heavy (800) and fluidly sized.
- **Interaction states:** *Normal* — light panel cell with inset bevel highlights. *Hover* — accent-yellow fill, `-2px` offset shift, stepped (no-smooth) transition. *Focus* — 4px blue `:focus-visible` ring. *Active* — button presses into the surface (inset shadow). *Selected* — cell takes X/O tinted background, clicks ignored. *Disabled* — cells locked after game end; Restart dims to the muted tone. Winning four cells blink (steps timing).
- **Accessibility:** `role="status"` + `aria-live="polite"` status region; grid cells are native buttons with coordinate-style `aria-label`s (e.g., "Cell C3, O"). Ink-on-paper and ink-on-accent pairings are very high contrast (>10:1); status X/O badges use tinted backgrounds that keep text ≥ 4.5:1. Focus is visible on every control, overlay moves focus to New Game, and `prefers-reduced-motion` turns off blink/stepped effects.
- **Responsive behavior:** `max-width: 520px` card, 4-column grid with `aspect-ratio` cells and `clamp()` font sizes; at ≤380px the marquee padding, grid gaps, and bevel thickness shrink. Buttons wrap if needed. Fully usable at 320px width.
- **Question for the team:** Is the 4×4 four-in-a-row variation a welcome extra mode, or should both prototypes stay on the standard 3×3 board for a fairer style comparison?
