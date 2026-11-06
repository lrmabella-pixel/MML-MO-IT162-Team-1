# Terminal Assessment — MO-IT162 Math for Machine Learning: Linear Algebra
### Team 1 (Esquivel, Fuentebella, Abella, Baluso)


## Contents

- **`Milestone1_EDA.ipynb`** — Exploratory data analysis of the three preprocessed datasets (Demographics, Transactions, Social Media Interactions): structure, descriptive statistics, anomaly checks, and findings.
- **`Milestone2_Visualizations.ipynb`** — Visualization work built on the Milestone 1 findings: distributions, categorical breakdowns, relationships between variables, trends over time, and a summary dashboard.
- **`datasets/`** — The three cleaned datasets used by both notebooks (`demographics_clean.csv`, `social_clean.csv`, `transactions_clean.csv`).
- **`visualizations/`** — Exported chart images from Milestone 2, including the summary dashboard.
- **`presentation/`** — The exported slide deck PDF for the Terminal Assessment presentation.

## Key findings

- 63 anomalous Age records (values of -1 or 150) and 70 nonpositive Transaction Amounts were identified and resolved; masking and median-imputing the Age anomalies brought the mean from 45.4 to 44.7 (SD from 19.7 to 14.4).
- Sentiment classes are imbalanced: Positive, Neutral, and Negative dominate, while Very Positive (32) and Very Negative (34) are underrepresented; 309 "Unknown" records reflect imputed missing data, not a genuine sentiment.
- Age shows essentially no correlation with Transaction Amount (0.021), so future segmentation models will need to combine multiple variables rather than rely on Age alone.
- September–October 2024 recorded the two lowest monthly average Transaction Amounts in the dataset, flagged for further investigation rather than treated as a confirmed trend.

See `presentation/` for the full slide deck, and the notebooks for complete analysis and methodology.
