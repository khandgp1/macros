# Improve Macro Calculator Visibility

This update focuses on enhancing the visibility and contrast of the macro calculator to ensure it is easy to read. It aligns the calculator's color scheme with the application's light theme and increases contrast for key data points.

## User Review Required

> [!IMPORTANT]
> The calculator's color scheme will be shifted to high-contrast light mode to match the rest of the application. Text will be significantly darker, and the "Total" row will be more prominently highlighted.

## Proposed Changes

### Styling Improvements

#### [MODIFY] [style.css](file:///Users/khandpv1/Desktop/.AntiGrav/macros/style.css)
- Change `.macro-calc-container` background to a solid white (or light grey) with a subtle shadow for depth.
- Update text colors:
    - **Ingredient Names**: Use `--text-main` (Slate Charcoal) instead of light grey.
    - **Macro Values**: Use a high-contrast dark color.
    - **Calories**: Increase brightness/contrast.
- Refine the **Total Row**:
    - Use a stronger background tint (e.g., a more saturated version of the Sage accent).
    - Use bold, dark text for the final totals.
- Update **Input Fields**: Ensure the borders and text inside inputs are clearly visible against the light background.

### UI Structure (Minor)

#### [MODIFY] [script.js](file:///Users/khandpv1/Desktop/.AntiGrav/macros/script.js)
- Ensure the header text in the calculator uses appropriate semantic classes if needed for styling.

## Verification Plan

### Automated Tests
- N/A

### Manual Verification
- Open the "Intro" tab.
- Verify that all text (ingredients, macros, totals) is clearly legible against its background.
- Confirm the "Total" row stands out distinctly.
- Check that the calculator feels integrated with the overall "Matte Off-White" theme of the app.

## Progress Checklist
- [x] Update `.macro-calc-container` background and shadow in `style.css`
- [x] Fix text contrast for ingredient names and headers
- [x] Enhance contrast for Protein and Calorie values
- [x] Redesign Total Row for maximum prominence
- [x] Update input field styling for better visibility
- [x] Verify consistency with the application's light theme
