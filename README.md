# Filtering Large Dataset

# Industry Financial Analysis

## Overview

This notebook loads a large company financial dataset and filters it down to one industry and one fiscal year to compute summary statistics. The core task is finding the mean Total Assets for companies in a specific NAICS industry code during fiscal year 2018.

Author: Tanmay Tiwari

## Data

**File:** `industryAnalysis_2000_2022.csv` (not included, must be placed in the same working directory to run this notebook)

The dataset has 254,553 rows and 21 columns, covering fiscal years from 2000 to 2022. Columns include:

`gvkey, datadate, fyear, indfmt, consol, popsrc, datafmt, tic, conm, curcd, at, cogs, csho, emp, ib, oibdp, sale, costat, prcc_c, naics`

Key columns used in the analysis:
- `naics`: industry classification code
- `fyear`: fiscal year
- `at`: Total Assets
- `tic` / `conm`: company ticker and name

## What the Notebook Does

1. Imports pandas and numpy.
2. Loads the CSV into a dataframe called `industry`.
3. Displays the full dataframe to check it loaded correctly.
4. Filters the data to rows where `naics` equals 454110 and `fyear` equals 2018, keeping only the columns `tic`, `conm`, `at`, `naics`, and `fyear`.
5. Saves that filtered result to a new dataframe called `naics_454110`.
6. Displays `naics_454110` to confirm the filter worked.
7. Runs `.describe()` on `naics_454110` to get summary statistics (count, mean, std, min, max, quartiles).
8. Notes the finding in a comment.

## Key Finding

For fiscal year 2018, the mean Total Assets (`at`) across companies in this industry is approximately 5477.83. The notebook does not state the currency or unit of measurement (Compustat's `at` field is typically reported in millions, but that is not confirmed anywhere in this notebook, so you may want to verify it before citing the figure).

The sample size for this filter is 51 rows total, with only 46 having a non null value for `at`.

## How to Run

1. Open the notebook in Google Colab or Jupyter.
2. Upload `industryAnalysis_2000_2022.csv` to the same directory or to the Colab file environment.
3. Run all cells in order from top to bottom.

## Requirements

- Python 3
- pandas
- numpy
