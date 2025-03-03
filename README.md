Below is a sample **README.md** file describing the **"Phase 1 – Final"** version of the Portfolio Manager Simulator. It provides an overview of the project's purpose, functionality, requirements, and setup instructions, serving as a convenient reference for both developers and end-users.

```md
# Portfolio Manager Simulator – Phase 1 Final

**Phase 1 – Final** is the stabilized, production-ready base version of the Portfolio Manager Simulator. It features:

1. **Robust Input Validation** for portfolio value and proposed allocations.
2. **Negative Proposed Values Allowed**, enabling scenarios where assets are sold.
3. **Auto-Expanded Rows**, so Stocks, Bonds, Cash, and their child nodes are immediately visible.
4. **Column Reordering** to a more intuitive sequence: Current → Target → Delta → Proposed → Total (for both dollars and percentages).
5. **Custom Cash Target (%)** control and a **Risk Tolerance** dropdown (Conservative, Moderate, Aggressive).

This version is our foundational "base camp," serving as a dependable starting point for future enhancements (Phases 2 and 3).

---

## Table of Contents

1. [Overview & Features](#overview--features)  
2. [Technology Stack & Dependencies](#technology-stack--dependencies)  
3. [Installation & Setup](#installation--setup)  
4. [How to Use](#how-to-use)  
5. [File Structure](#file-structure)  
6. [FAQ & Common Issues](#faq--common-issues)  
7. [License](#license)

---

## Overview & Features

- **Generate Random Portfolios**  
  The tool can create a random mix of Stocks, Bonds, and Cash, broken down into classes and positions for a realistic demo experience.

- **Reordered Columns**  
  The simulator table now displays for dollars and percents in this order:
  1. **Current**
  2. **Target**
  3. **Delta**
  4. **Proposed**
  5. **Total**

- **Auto-Expanded Rows**  
  All nodes (`Stocks`, `Bonds`, `Cash`, sub-classes, positions) start in an expanded state for immediate visibility.

- **Interactive Editing**  
  - **Proposed(\$) or Proposed(%)**: Enter negative or positive values. Negative indicates a sell or short scenario.
  - **Portfolio Value**: Click the displayed value to edit total portfolio size, auto-recalculating risk-based target allocations.

- **Dark Mode Toggle**  
  A small toggle in the top-right corner enables/disables dark mode.

- **Validation & Clamping**  
  - **Portfolio Value**: Clamped to a minimum of \$1 to avoid division by zero or negative totals.
  - **Proposed(%)**: Clamped to max 200% for demonstration, but negative values are now allowed.
  - **Proposed(\$)**: Clamped to 2× total portfolio value to avoid unrealistic extremes.

---

## Technology Stack & Dependencies

- **HTML/CSS/JavaScript**  
  Plain JavaScript (no frameworks) for data manipulation and DOM updates.

- **Chart.js**  
  For the real-time pie charts visualizing Current, Target, and Total allocations.

- **Modern Browser**  
  Requires a recent browser supporting ES6 features and the [`Intl.NumberFormat`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat) API.

There are no additional server-side requirements—this app can be served locally or via any static hosting platform.

---

## Installation & Setup

1. **Clone or Download** the repository containing this `index.html` (or similarly named file).  
2. Open the `index.html` file in your preferred web browser.  
   - If local file references to Chart.js fail, use a simple HTTP server:
     ```bash
     npx http-server .
     ```
   - Then visit [http://localhost:8080](http://localhost:8080) (or a similar port).

---

## How to Use

1. **Open the Page**  
   The simulator instantly generates a new random client scenario.

2. **Try Different Risk Tolerances**  
   - Select **Conservative**, **Moderate**, or **Aggressive** from the dropdown.
   - Adjust the **Cash Target (%)** field to override the default cash portion.

3. **Edit the Portfolio**  
   - **Portfolio Value**: Click on the displayed value (e.g., `100,000`) to enter a new total.
   - **Proposed(\$) / Proposed(%)**: Click on any Proposed cell, type a positive or negative number, and press Enter or click away.

4. **Reset or Regenerate**  
   - **Reset Trades**: Revert to the scenario’s original values.
   - **Generate New Client**: Create a fresh random set of positions.

5. **Dark Mode**  
   - Click the small gray circle at the top-right corner to toggle dark mode on/off.

---

## File Structure

- **`index.html`**  
  Main HTML file containing all markup, inlined CSS, and JS for the simulator.

- **`README.md`**  
  This file, explaining usage, features, and future directions.

- **(Optional) `assets/`**  
  If you store additional scripts, styles, or images in a subdirectory.

---

## FAQ & Common Issues

1. **Why can't I see the Proposed(%) or Proposed(\$) field upon click?**  
   Make sure you are clicking the **Proposed** column (4th dollar column or 9th percent column). The **Delta** column is not editable.

2. **Why do negative Proposed(\$) or Proposed(%) values still appear in red?**  
   Negative values are styled red by design, indicating a sell. The calculation is still correct; it’s purely a visual cue.

3. **Nothing updates after I type a Proposed value and press Enter.**  
   Check you are indeed focusing the correct cell (e.g. **Proposed** not **Delta**). Also ensure your browser supports `Event.key === 'Enter'`.

4. **The charts are overlapping or not rendering**  
   A quick browser refresh often resolves small layout issues. If on a slow connection, confirm that Chart.js loaded properly.

---

## License

The **Portfolio Manager Simulator** (Phase 1 – Final) is available under an MIT-style license by default. Adjust or replace this section with your actual license information.

--- 

### Going Forward

**Phase 1 – Final** serves as our stable baseline. Future phases will include more advanced features, such as real-time data feeds, import/export, multi-asset expansions, and so on. If you have questions or ideas, please open an issue or create a pull request!