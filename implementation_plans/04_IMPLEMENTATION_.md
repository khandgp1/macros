# Update Macro Calculator to Tabular Design

This update reformats the macro calculator into a clean, modern tabular layout. This will improve readability and make it easier to see individual ingredient contributions to the total macros.

## User Review Required

> [!IMPORTANT]
> The calculator will now use a grid-based table layout. Each row will represent an ingredient, and columns will display Weight (g), Protein (g), and Calories (kcal).

## Proposed Changes

### Logic & UI Structure

#### [MODIFY] [script.js](file:///Users/khandpv1/Desktop/.AntiGrav/macros/script.js)
- Update `renderMacroCalc()` to use a `table` (or a `div` grid that looks like a table).
- Include column headers: Ingredient, Grams, Protein, Calories.
- Add real-time calculation for individual rows as well as the total row.
- Ensure the input fields remain easily accessible.

### Styling

#### [MODIFY] [style.css](file:///Users/khandpv1/Desktop/.AntiGrav/macros/style.css)
- Implement a modern table aesthetic for `.macro-calc-container`.
- Use subtle background colors for headers and alternate rows.
- Ensure the table is responsive (e.g., stacking on mobile or horizontal scroll if needed).
- Refine typography and spacing for a "premium" feel.

## Verification Plan

### Automated Tests
- N/A

### Manual Verification
- Open the "Intro" tab.
- Verify the calculator has a clear tabular structure.
- Check that individual row macros update as grams are entered.
- Confirm that the totals at the bottom remain accurate.
- Test responsiveness on smaller screen widths.

## Progress Checklist
- [x] Refactor `renderMacroCalc()` for tabular structure in `script.js`
- [x] Add individual row macro display logic
- [x] Update `.macro-calc-container` styles in `style.css`
- [x] Implement responsive table behavior
- [x] Verify calculation accuracy and layout alignment
