# ASTRO-DATA-PROJECT-3

## Overview
This project analyzes the light curve of the eclipsing binary star Algol using real observational data. The analysis includes data cleaning, normalization, phase folding, model fitting, and interpretation of the results. The main tools are a Jupyter notebook and a Python script for automated light curve analysis.

## Files
- **astro-data-proj-3.ipynb**: Main Jupyter notebook for step-by-step analysis, visualization, and model fitting of Algol's light curve. Includes detailed comments and explanations for each step.
- **ai_lightcurve_analysis.py**: Python script containing a function to analyze a phase-folded light curve and summarize the physical interpretation of the binary system.
- **algol.csv**: CSV file with Algol's light curve data (columns include RHJD, V, eV, etc.). Source: AAVSO data download


## How to Run the Analysis
1. Open `astro-data-proj-3.ipynb` in Jupyter or VS Code.
2. Step through the notebook cells to:
	- Load and clean the data
	- Normalize and phase-fold the light curve
	- Fit a two-Gaussian eclipse model
	- Visualize the results and residuals
	- Interpret the physical meaning of the fitted parameters
3. Optionally, use `ai_lightcurve_analysis.py` to analyze other phase-folded light curves programmatically.

## Key Steps in the Notebook
- **Data Loading & Cleaning**: Reads Algol's light curve from CSV, removes bad data, and normalizes flux.
- **Phase Folding**: Converts observation times to orbital phase using Algol's known period.
- **Model Fitting**: Fits a two-Gaussian model to the phase-folded light curve to extract eclipse depths, widths, and timing.
- **Visualization**: Plots raw and phase-folded light curves, model fits, and residuals.
- **Interpretation**: Summarizes what the light curve reveals about the Algol system (e.g., relative brightness, eclipse geometry).

## Example: Using ai_lightcurve_analysis.py
```python
import numpy as np
from ai_lightcurve_analysis import analyze_eclipsing_binary_light_curve

# Example phase and flux arrays (replace with your data)
phase = np.linspace(0, 1, 100)
flux = np.ones(100)
summary = analyze_eclipsing_binary_light_curve(phase, flux)
print(summary)
```

## Requirements
- Python 3.x
- numpy
- pandas
- matplotlib
- scipy

Install requirements with:
```bash
pip install numpy pandas matplotlib scipy
```
