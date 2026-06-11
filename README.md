# FIFA21-Cleaning-and-Transformation
Comprehensive data preprocessing, cleaning, and transformation pipeline on raw FIFA 21 player records using Python and Pandas.


# FIFA 21 Data Preprocessing & Cleaning Pipeline ⚽📊

This repository contains a structured data engineering and preprocessing workflow applied to the raw FIFA 21 dataset. The goal of this project is to take messy, unformatted structural sports data and transform it into a pristine, analysis-ready format for machine learning engines or business intelligence reporting.

## 🗂️ Dataset Overview
The project processes the **FIFA 21 Raw Dataset** consisting of **18,979 rows** and **77 initial columns** containing comprehensive metrics about football players globally, including their values, contracts, physical attributes, and in-depth skill stats.

## 🛠️ Data Preprocessing Steps Performed

The notebook executes a thorough step-by-step cleaning workflow:

1. **Redundant Feature Removal**: 
   * Dropped columns that don't add statistical significance to analytics (e.g., `photoUrl`, `playerUrl`).
   * Dropped redundant or alternative name identifiers (`Name`) favoring the full record tracking (`LongName`).

2. **Missing Value Management**:
   * Evaluated column nullability.
   * Dropped features with massive concentrations of missing entries (e.g., `Loan Date End` which missed over 94% of values).

3. **Complex Structural Column Parsing (Team & Contract)**:
   * Cleaned formatting characters (`\n`) out of text spaces.
   * Constructed custom structural lambda/mapping engines (`teamcleaner`) to parse out explicit tracking variables:
     * `Start Year` (Contract start)
     * `End Year` (Contract end)
     * `Team Name` (Parsed cleanly from contract strings)

4. **DataType Optimization**:
   * Assessed performance footprints across object strings and integer flags (e.g., converting ratings metrics like `POT` to absolute integers).

## 🚀 Built With

* **Python 3**
* **Pandas** - Comprehensive structural alignment and data cleaning
* **Jupyter Notebook** - Interactive exploratory programming and execution environment

## 📁 Repository Structure

```text
├── football.ipynb       # Main Jupyter Notebook detailing data cleaning steps
└── README.md            # Project documentation
