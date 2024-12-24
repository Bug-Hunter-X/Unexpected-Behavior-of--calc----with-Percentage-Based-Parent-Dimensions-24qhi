# Unexpected `calc()` Behavior in CSS

This repository demonstrates an uncommon issue related to the CSS `calc()` function. The problem surfaces when using `calc()` to compute dimensions of an element whose parent's dimensions are also percentage-based or not yet resolved during the page rendering.

## The Problem

The `calc()` function is powerful, but it relies on the parent element's dimensions being available at the time of calculation. If the parent's size is dependent on other factors (e.g., percentage-based width, dynamic content), the calculation may result in unexpected values.

## Reproducing the Issue

See `bug.css` and a test HTML file (not included here for simplicity).  Experiment with different parent container dimensions to observe the inconsistencies.

## Solution

The solution involves ensuring that the parent element has its dimensions definitively determined before the `calc()` calculation is performed. This could involve:

1. **Setting explicit dimensions on the parent:**  Instead of relying on percentages, assign fixed width and height values to the parent container.
2. **Using `vw` or `vh` units:** For a more responsive approach, use viewport-relative units (`vw` and `vh`) in the parent's dimensions.
3. **Refactoring the CSS:**  Rework the layout to avoid the dependency on uncertain parent dimensions.

See `bugSolution.css` for an example of a corrected approach using explicit parent dimensions.