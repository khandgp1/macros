# 25 — Remove Mindset Quote Component from Intro Tab

## Overview

Remove the dark-background "mindset quote" block that appears at the bottom of the Intro tab. This includes deleting the HTML template, its injection into the rendered output, the associated CSS styles, and the now-unused `mindset` field in the data file.

---

## Proposed Changes

### `script.js`

#### [MODIFY] script.js

- **Lines 206–210** — Delete the `mindset` template string that builds the `.mindset-quote` div.
- **Line 219** — Remove `${mindset}` from the `content.innerHTML` template inside `renderIntro`.

---

### `style.css`

#### [MODIFY] style.css

- **Lines 194–215** — Delete the `.mindset-quote` and `.mindset-quote::before` CSS rule blocks.

---

### `program.json`

#### [MODIFY] program.json

- **Line 7** — Remove the `"mindset": ""` field from the Intro day object (optional cleanup since it is no longer consumed).

---

## Checklist

- [x] Remove `mindset` template string from `script.js`
- [x] Remove `${mindset}` injection from `renderIntro` in `script.js`
- [x] Delete `.mindset-quote` and `.mindset-quote::before` CSS rules from `style.css`
- [x] Remove unused `mindset` field from `program.json`
- [ ] Verify Intro tab renders without the dark quote block
