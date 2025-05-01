# Soda Taste Test: A Factorial Experiment Design with Blocking

## Overview
This project investigates how the **method of pouring** and **method of consumption** affect the enjoyment of Coca-Cola. Using a **3×2 factorial design with participant blocking**, the study evaluates taste ratings across six conditions in a controlled experimental setting.

## Methodology

This study followed a controlled factorial experiment using a **3×2 within-subjects design** with blocking to account for individual differences in taste perception.

### Participants
- **6 university students**, aged 18–21
- Each participant tasted all 6 conditions (fully crossed design)
- Participants rinsed with water between tastings to reset palate

### Experimental Factors
- **Pouring Method (3 levels)**:
  - *Down the side*
  - *Center*
  - *From the can*
- **Consumption Method (2 levels)**:
  - *Straw*
  - *No straw*

### Blocking
Participants were treated as blocks to control for individual taste preferences. Each participant provided one rating for every condition, reducing variability unrelated to the treatment effects.

### Procedure
- Enjoyment was rated on a **1–10 scale** after each tasting
- All trials occurred in a single session per participant

### Analysis
- A linear model with interaction and blocking was fitted
- Partial F-tests were conducted to evaluate main and interaction effects
- Model assumptions (normality, independence, homoscedasticity) were tested and met
- A custom R script was used for post-hoc power simulation


## Results

The linear model analysis revealed several key insights into how pouring and consumption methods affect soda enjoyment:

### Main Findings
- **Drinking without a straw** significantly increased enjoyment.  
  - *p* = 0.027  
  - Estimated increase of **+1.33 points** on a 10-point enjoyment scale
- **Pouring method**, when considered along with its interaction with consumption, also showed statistical significance.  
  - *p* = 0.0126  
  - Suggests that how the soda is poured affects perception, especially when combined with the way it is consumed

### Non-significant Results
- The **pure interaction** between pouring and consumption methods was **not** significant  
  - *p* = 0.773  
  - Indicates that their joint effect does not differ substantially from their individual contributions

### Model Performance & Power
- **Overall model p-value**: 2.62 × 10⁻⁶
- **Post-hoc power analysis**:  
  - Achieved statistical power = **0.932** with 6 participants  
  - Exceeds the standard 0.8 threshold, confirming robustness of the results

### Assumption Checks
- Residual plots and the Shapiro-Wilk test confirmed:
  - **Normality of residuals**
  - **Independence** (no structure in data)
  - **Homoscedasticity** (equal variance)

# View the Full Report
- 🔗 [HTML Report (Github Pages)](https://aidanpmitchell.github.io/Soda_Factorial/)
- 🔗 [PDF Report](Report/Soda_Factorial.pdf)

## Project Structure

```
Soda_Factorial/
├── Data/                         # Raw dataset used in the analysis
│   └── Soda_Data.csv
│
├── Images/                       # Photos and supporting visuals
│   └── [experiment photos, optional figures]
│
├── Report/                       # Analysis scripts and report source files
│   ├── Soda_Factorial.Rmd        # Full R Markdown analysis file
│
├── Soda_Factorial.pdf            # PDF version of the report
│── power_factorial_32.R          # R script for power analysis simulation
├── index.html                    # Rendered HTML version for GitHub Pages
├── .gitignore                    # Files to be ignored by Git
└── README.md                     # Project overview and documentation
```

## Dependencies

This project was developed using R. To run the analysis and render the report, make sure the following packages are installed:

### Required R Packages

```r
install.packages(c(
  "tidyverse",     # For data manipulation and visualization
  "knitr",         # For dynamic report generation
  "rmarkdown",     # To knit .Rmd to HTML/PDF
  "kableExtra",    # For enhanced tables in the report
  "ggplot2",       # For plotting
  "dplyr",         # For data wrangling
  "tidyr",         # For data formatting
  "broom"          # For tidying model outputs
))
```

## How to Run
1. Clone the repository:
```
git clone https://github.com/aidanpmitchell/Soda_Factorial.git
cd Soda_Factorial
```
2. Open **Soda_Factorial.Rmd** in RStudio
3. Install required dependencies
4. Run the analysis by knitting the R Markdown file to a pdf