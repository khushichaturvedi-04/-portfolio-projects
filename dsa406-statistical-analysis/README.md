# Exploratory Data Analysis & Statistical Modeling in R

> Built in RStudio on Posit Cloud.

💻 [View full source code](https://github.com/khushichaturvedi-04/DSA-406)

---

## Overview

A series of statistical analysis and modeling projects completed in R, progressing from foundational exploratory data analysis (EDA) through correlation analysis, data distribution/normality diagnostics, and linear regression modeling — applied to two very different real-world datasets: a large-scale computer vision annotation dataset and an NHL season performance dataset.

---

## Project 1 & 2: YouTube Bounding Boxes (YT-BB) Dataset Analysis

**Research question:** What are the most commonly annotated object classes in the YT-BB dataset, and how do bounding box dimensions vary across classes?

A two-part progressive analysis of a 100,000-observation, 10-variable computer vision annotation dataset (YouTube-BoundingBoxes), moving from foundational EDA into statistical modeling.

**Part 1 — Foundational EDA:**
- Loaded and cleaned the dataset (`read_csv()`, `clean_names()`, `complete.cases()`), identifying variable types and handling missing values
- Performed data wrangling with `mutate()`/`across()` to convert types and engineer new bounding-box dimension variables
- Computed descriptive statistics (`summary()`, `skim()`) to characterize central tendency and spread
- Built five visualizations (bar chart of top object classes, histogram of bounding box areas, boxplot of width by class, scatterplot of width vs. height, and a presence/absence chart), each with a written interpretation
- **Finding:** Bounding box area distribution is right-skewed, class annotations are imbalanced, and different object classes show distinct spatial "shape signatures" in their bounding box dimensions

**Part 2 — Advanced EDA, correlation & regression:**
- **Hypothesis:** Bounding box width and height are positively correlated, such that bounding box area can be reasonably predicted from a linear combination of width and height
- Applied grouped descriptive statistics (`describeBy()`) across object classes, `skimr::skim()` and `summarytools::dfSummary()` for distribution diagnostics, and log transformation to address right-skew and improve normality
- Built a Pearson correlation matrix and heatmap across numeric variables, with significance testing via `corr.test()`
- Fit and validated a linear regression model predicting `bb_area` from `bb_width` and `bb_height`, checking model assumptions (linearity, normality, multicollinearity, homoscedasticity)
- **Finding:** Hypothesis confirmed — width and height are moderately-to-strongly positively correlated, and the regression model achieved a high R², with the log-transformed version showing improved residual normality. Noted class imbalance (dominated by the "person" class) as a limitation, with per-class modeling flagged as future work

## Assignment 3: NHL 2022–2023 Season Analysis

**Research question:** What factors are most strongly associated with team wins in the NHL 2022–2023 regular season?

Analyzed a 32-team, 18-variable season statistics dataset to identify the strongest statistical predictors of regulation wins (`W`).

- Conducted EDA and built a Pearson correlation matrix/heatmap across key performance variables
- Fit a linear regression model (`W ~ GF + GA`) and validated it against the standard linear model assumptions: linearity, normality of residuals, multicollinearity (VIF), and homoscedasticity
- **Findings:**
  - Goal Differential (`DIFF`) is the single strongest predictor of wins (r = 0.969)
  - The model `W ~ GF + GA` explains 94% of the variance in wins (R² = 0.94), with both Goals For (+0.153/goal) and Goals Against (−0.164/goal) highly significant (p < 0.001)
  - Goals Against has a slightly larger coefficient magnitude than Goals For, suggesting defensive performance is marginally more predictive of winning than offense
  - Shootout statistics showed near-zero correlation with wins, consistent with shootout outcomes being largely random

## Skills Demonstrated

`R` · `RStudio / Posit Cloud` · `tidyverse` (`dplyr`, `readr`, `janitor`) · `Exploratory Data Analysis` · `Data Wrangling & Cleaning` · `Descriptive Statistics` · `Data Visualization` (`ggplot2`) · `Correlation Analysis` · `Linear Regression Modeling` · `Regression Diagnostics` (linearity, normality, multicollinearity/VIF, homoscedasticity) · `Statistical Hypothesis Testing` · `R Markdown / Quarto Reporting`

## Result

Completed three progressively deeper statistical analysis reports in R — from foundational EDA through hypothesis-driven correlation and regression modeling — applied to both a large-scale computer vision dataset and a real-world sports analytics dataset, with all models validated against standard linear regression assumptions.
