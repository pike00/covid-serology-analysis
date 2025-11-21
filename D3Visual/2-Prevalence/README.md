# Prevalence (PPV-NPV) Visualization

This folder contains an interactive D3.js + Plotly visualization for exploring the relationship between prevalence, sensitivity, specificity, and predictive values (PPV/NPV) in diagnostic testing.

## Files

- `prevalence.html` - Main interactive visualization
- `prevalence_FilterType.html` - Alternative version with filter options
- `index.html` - Entry point
- `tests.csv` - Test data (if applicable)

## How to Run

### 1. Navigate to this folder

**macOS Terminal:**

```bash
cd "cse6242-team124-courseproject/D3Visual/2-Prevalence"
```

**Windows Command Prompt:**

```cmd
cd "cse6242-team124-courseproject\D3Visual\2-Prevalence"
```

### 2. Start a local HTTP server

```bash
python3 -m http.server 8000
```

On Windows, you may need:

```cmd
python -m http.server 8000
```

### 3. Open in your browser

Navigate to:

- Main visualization: http://localhost:8000/prevalence.html
- With filters: http://localhost:8000/prevalence_FilterType.html
- Index page: http://localhost:8000/index.html

## Features

The visualization includes:

- Interactive sliders for sensitivity, specificity, and prevalence
- Real-time PPV/NPV calculations and charts
- Visual representation of test performance metrics

## Troubleshooting

If visuals do not appear, verify:

- All files are in the same directory as the HTML file
- The local server is running on port 8000
- The browser URL exactly matches the filename
