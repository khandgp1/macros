# 26 — Duplicate INTRO Tab into SNIPPET Tab

## Overview

Replace the contents of the **SNIPPET** tab so it renders identically to the **INTRO** tab. This means the Snippets tab will use the same rendering path, layout classes, data shape, and components (bento-card grid + Breakfast Macro Calculator) as the Intro tab currently does.

---

## Proposed Changes

### `program.json`

#### [MODIFY] program.json

- Replace the `Snippets` day object's `focus`, `description`, and `exercises` fields to mirror the `Intro` day object (empty strings for `focus` and `description`, empty `exercises` array).

---

### `script.js`

#### [MODIFY] script.js

- **`renderContent()`** — In the `else if (day.title.toLowerCase() === 'snippets')` branch, replace the call to `renderSnippets(day)` with `renderIntro(day)` and swap the CSS class from `snippets-wide` → `intro-wide`.
- **`renderSnippets()`** — The function becomes dead code; it can be removed entirely or left in place (plan calls for removal to keep the file clean).

---

## Checklist

- [x] Update `program.json` — set `Snippets` day `focus` and `description` to `""` and `exercises` to `[]`
- [x] Update `renderContent()` in `script.js` — route Snippets tab to `renderIntro()` with `intro-wide` class
- [x] Remove `renderSnippets()` function from `script.js` (dead code cleanup)
- [x] Verify SNIPPET tab renders the same layout as INTRO tab in the browser

