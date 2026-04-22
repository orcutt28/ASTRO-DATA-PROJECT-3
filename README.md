# ASTRO-DATA-PROJECT-3

## Overview
This project analyzes the light curve of the eclipsing binary star Algol using real observational data. The analysis includes data cleaning, normalization, phase folding, model fitting, and interpretation of the results. The main tools are a Jupyter notebook and a Python script for automated light curve analysis.

## Files
- **astro-data-proj-3.ipynb**: Main Jupyter notebook for step-by-step analysis, visualization, and model fitting of Algol's light curve. Includes detailed comments and explanations for each step.
- **ai_lightcurve_analysis.py**: Python script containing a function to analyze a phase-folded light curve and summarize the physical interpretation of the binary system.
- **algol.csv**: CSV file with Algol's light curve data (columns include RHJD, V, eV, etc.). Source: AAVSO data download


## How to Run the Analysis
Run the notebook cells to:
	- Load and clean the data
	- Normalize and phase-fold the light curve
	- Fit a two-Gaussian eclipse model
	- Visualize the results and residuals
	- Interpret the physical meaning of the fitted parameters

## Key Steps in the Notebook


### 1. Import Libraries
The first code cell imports essential Python libraries:
- `numpy` for numerical operations
- `pandas` for data handling and CSV reading
- `matplotlib.pyplot` for plotting
- `scipy.optimize.curve_fit` for model fitting

**Why:** These libraries provide the core tools for data analysis, visualization, and model fitting throughout the notebook.

### 2. Data Loading, Cleaning, and Normalization
This block loads the Algol light curve data from `algol.csv` into a pandas DataFrame, extracts the relevant columns (time, magnitude, error), and applies several cleaning steps:
- Filters out invalid or unphysical data points (e.g., bad error bars, impossible magnitudes)
- Converts magnitudes to normalized flux units
- Estimates uncertainties in flux

**Why:** Cleaning and normalizing the data ensures that only reliable measurements are used and that the flux scale is consistent for model fitting.

### 3. Phase Folding and Initial Visualization
Here, the known orbital period of Algol is set, and the observation times are converted to orbital phase. Outliers are removed using robust statistics, and both the raw and phase-folded light curves are plotted.

**Why:** Phase folding aligns all eclipses on top of each other, making periodic features (like eclipses) clear and enabling model fitting. Outlier removal prevents bad data from skewing results.

### 4. Model Definition and Fitting
This section defines a two-Gaussian eclipse model (to represent the primary and secondary eclipses) and a function for initial parameter guesses. The model is then fit to the phase-folded, normalized flux data using non-linear least squares, with parameter bounds for physical realism. The best-fit parameters and their uncertainties are printed.

**Why:** Fitting a model quantifies the eclipse depths, widths, and timing, allowing physical interpretation of the binary system. Parameter bounds ensure the fit remains physically meaningful.

### 5. Secondary Eclipse Depth Check
This short block prints the fitted depth of the secondary eclipse and its uncertainty.

**Why:** The secondary eclipse is often much shallower than the primary; checking its depth helps assess the detectability and physical properties of the system.

### 6. Visualization of Model Fit and Residuals
This block plots the phase-folded light curve with the fitted model, highlights the eclipse regions, and shows the residuals (data minus model). Outliers are excluded from the plot, and the RMS of the residuals is calculated. Goodness-of-fit statistics (chi-squared, reduced chi-squared) and the covariance/correlation matrices are printed.

**Why:** Visualizing the fit and residuals helps assess model quality and identify any systematic deviations. Goodness-of-fit metrics quantify how well the model explains the data.

### 7. Further Analysis 
The notebook calls a function from `ai_lightcurve_analysis.py` to provide a summary interpretation of the fitted light curve.

**Why:** This step demonstrates how to automate the interpretation of light curve features.


## Requirements
- Python 3.x
- numpy
- pandas
- matplotlib
- scipy

