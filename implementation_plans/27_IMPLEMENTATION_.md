# Rename Tabs: INTRO to BREAKFAST and SNIPPETS to MEAT

Rename the primary navigation tabs to better reflect the application's content ("MACROS").

## User Review Required

> [!IMPORTANT]
> The internal logic in `script.js` currently relies on the strings "intro" and "snippets" (case-insensitive) to determine which rendering logic to use. These will be updated to "breakfast" and "meat" respectively.

## Proposed Changes

### Data Layer

#### [MODIFY] [program.json](file:///Users/khandpv1/Desktop/.AntiGrav/macros/program.json)
- Update "Intro" title to "Breakfast".
- Update "Snippets" title to "Meat".

---

### Logic Layer

#### [MODIFY] [script.js](file:///Users/khandpv1/Desktop/.AntiGrav/macros/script.js)
- Update `renderContent` to check for `breakfast` instead of `intro`.
- Update `renderContent` to check for `meat` instead of `snippets`.
- (Optional but recommended) Update comments that refer to "Intro" or "Snippets" to maintain codebase clarity.

---

## Verification Plan

### Automated Tests
- None available for this project.

### Manual Verification
- Open the application in the browser.
- Verify the first tab label is "BREAKFAST".
- Verify the second tab label is "MEAT".
- Click each tab to ensure the content renders correctly (the macro calculator and bento layout should appear for both, as per current implementation).
- Verify that the layout remains consistent (e.g., the wider max-width is still applied via the `intro-wide` class or its equivalent).

## Checklist

- [x] Modify `program.json` tab titles
- [x] Update `script.js` conditional logic in `renderContent`
- [x] Verify tab labels in UI
- [x] Verify tab functionality and content rendering
