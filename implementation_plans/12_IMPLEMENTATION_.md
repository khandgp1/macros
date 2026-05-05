# 12_IMPLEMENTATION_.md

This plan focuses on making the Macros Calculator table on the `Intro` tab wider to improve readability and visual impact.

## User Review Required

> [!IMPORTANT]
> The width of the entire Intro tab content (including the bento grid below) will be increased to accommodate the wider table. This ensures visual consistency across the page.

## Proposed Changes

### UI Styling Adjustments

#### [MODIFY] [style.css](file:///Users/khandpv1/Desktop/.AntiGrav/macros/style.css)
- Add a new utility class `.intro-wide` for the `#workout-content` container to allow a broader layout on the Intro tab.
- Update `.macro-calc-container` to utilize the full available width of its parent.
- Slightly adjust the grid column ratios in `.table-row` to better distribute the extra space.

### Application Logic

#### [MODIFY] [script.js](file:///Users/khandpv1/Desktop/.AntiGrav/macros/script.js)
- Update `renderContent` to apply the `intro-wide` class when the user is on the `Intro` tab, similar to how `snippets-wide` is handled.

## Verification Plan

### Manual Verification
- [ ] Navigate to the `Intro` tab and verify the Macros Calculator table is noticeably wider.
- [ ] Ensure the bento grid below the calculator also scales gracefully to the new width.
- [ ] Switch to the `Snippets` tab and verify it still uses its `1280px` wide layout.
- [ ] Verify that other tabs (if any) maintain the default `600px` width.

## Checklist
- [x] Add `.intro-wide` class to `style.css` with `max-width: 900px`.
- [x] Update `.macro-calc-container` in `style.css` to `max-width: 100%`.
- [x] Modify `renderContent` in `script.js` to toggle the `intro-wide` class.
- [ ] Test the layout on different screen sizes to ensure responsiveness.
