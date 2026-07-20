# Applied Machine Learning: Global Internet Adoption & Coursework Portfolio

 💻 [View full source code](https://github.com/khushichaturvedi-04/DSA-412)

> Built in Google Colab.

---

## Overview

A semester of applied machine learning coursework spanning supervised learning (regression, classification), unsupervised learning (clustering), and deep learning (feedforward networks, CNNs, RNNs, and transformer-based NLP), culminating in an independent capstone project analyzing two decades of global internet adoption data.

---

## Final Project: Global Internet Adoption — Clustering Trajectories & Predicting Penetration Rates

**Research question:** Can we identify distinct global internet-adoption trajectories from 2000 to 2022, and can a country's earlier penetration rates (2000–2021) predict its 2022 internet usage level?

**Dataset:** UN Internet Usage — Percentage of Individuals per Country (2000–2022), sourced from the International Telecommunication Union (ITU) via the UN's UNdata portal. Built and documented the dataset from raw source myself, including a full data dictionary, missing-value handling strategy, and wrangling plan, before any modeling began.

**Methods:** K-Means clustering (unsupervised) + Ridge regression (supervised)

**Approach:**
- Cleaned and restructured 1,552 long-format rows into a 221-country wide-format table (one row per country, one column per year), filtering out regional/development aggregates that would otherwise distort both clustering and regression
- Handled missing values via forward/backward fill along the time axis and dropped countries with insufficient data; applied `StandardScaler` fit only on the training set to prevent data leakage
- Selected K-Means cluster count (k=4) using elbow method and silhouette score analysis, prioritizing real-world interpretability (four adoption "archetypes") over the marginally higher silhouette score of k=2/3
- Diagnosed severe multicollinearity between year-columns (r > 0.95 for most pairs) via a Pearson correlation heatmap, which directly motivated using Ridge regression over ordinary least squares
- Tuned Ridge's regularization strength via 5-fold cross-validated `RidgeCV` over a log-spaced alpha grid

**Results:**
- **Clustering:** Identified four coherent global adoption archetypes (silhouette = 0.4567) — *High gradual adopters*, *Persistently low adopters* (~59 countries still below 30% penetration in 2022), *Rising mid-tier*, and *Early saturated adopters* — closely mirroring real-world development patterns
- **Regression:** Achieved Test R² = 0.9879 and Test RMSE = 2.56 percentage points predicting 2022 internet usage from 2000–2021 history, with the most recent prior year (2021) as the dominant predictor
- Discussed the ethical and methodological limits of the analysis directly in the report: self-reported national data quality varies by country, national averages mask within-country inequality, and historical trajectories aren't guaranteed to hold under structural shocks like COVID-19-driven acceleration

## Supporting Coursework

**Dataset Design & Documentation (Assignment 1)**
Authored a full data dictionary and wrangling plan for the raw UN internet usage dataset — defining variable types, valid ranges, missing-value codes, and a step-by-step cleaning strategy — before any code was written. This became the foundation dataset used throughout the rest of the course.

**Binary Classification with Logistic Regression (Assignment 2)**
Engineered time-series features (lagged value, year-over-year delta, percent change, 3-year rolling mean) from the internet usage dataset and trained a logistic regression classifier to predict whether a country-year would have "high" internet usage (≥50%), evaluating with predicted probabilities rather than just hard labels.

**Linear Regression Model Comparison (Assignment 3)**
Built and compared two linear regression pipelines predicting internet usage percentage — one numeric-only feature set and one incorporating one-hot-encoded categorical region data — using `ColumnTransformer` preprocessing pipelines, and selected the better model by Mean Squared Error.

**Unsupervised Text Clustering — Shakespeare's Plays (K-Means + TF-IDF)**
Applied Term Frequency–Inverse Document Frequency (TF-IDF) vectorization to the full text of Shakespeare's plays and used K-Means clustering to explore whether genre categories (Comedy, History, Tragedy, Romance) emerge as natural clusters from word-frequency patterns alone.

**Feedforward Neural Network — Fashion MNIST**
Built and trained a feedforward neural network image classifier on the Fashion MNIST dataset, evaluating performance with per-class precision via `classification_report` and a confusion matrix, and visually inspecting individual correct/incorrect predictions to understand the model's failure modes (e.g., confusion between visually similar clothing categories).

**CNN vs. Feedforward NN Analysis**
Worked through a guided comparison of a standard feedforward neural network against a Convolutional Neural Network (CNN) trained on the MNIST digit dataset, analyzing differences in data preprocessing, architecture (convolution/pooling layers vs. dense layers), and training behavior between the two approaches.

**Character-Level Text Generation with RNNs**
Built a character-level Recurrent Neural Network (GRU-based) in TensorFlow, trained on the full text of Arthur Conan Doyle's *The Adventures of Sherlock Holmes*, to generate new text in the author's style. Covered the full pipeline: text vectorization, tensor-based training example construction, model architecture, training-loss analysis across epochs, and autoregressive text generation with temperature-controlled sampling.

**Measuring Bias in NLP Transformer Models (BERT)**
Group lab investigating gender bias in BERT using the BEC-Pro (Bias Evaluation Corpus with Professions) dataset — measuring the log-probability association between gendered pronouns and professions in BERT's masked-language-model predictions, and interpreting the results as quantitative evidence of the model internalizing social bias from its training corpus.

## Skills Demonstrated

`Python` · `Google Colab` · `pandas` / `NumPy` · `scikit-learn` (Logistic Regression, Linear/Ridge Regression, K-Means, `ColumnTransformer` pipelines, `RidgeCV`) · `TensorFlow / Keras` (Feedforward NN, CNN, RNN/GRU) · `Hugging Face Transformers` (BERT) · `NLP` (TF-IDF, text vectorization, bias evaluation) · `Unsupervised Learning` (K-Means, elbow method, silhouette scoring) · `Supervised Learning & Regularization` (Ridge/L2, multicollinearity diagnostics) · `Data Wrangling & Feature Engineering` · `Model Evaluation` (MSE, RMSE, R², confusion matrices, classification reports) · `Data Ethics & Responsible AI`

## Result

Delivered a full independent capstone project combining unsupervised and supervised learning to answer a real-world global development question, achieving R² = 0.988 in the predictive model, alongside a semester of hands-on coursework spanning classical ML, deep learning, and NLP fairness evaluation — including authoring an original dataset from a raw UN source used throughout the course.
