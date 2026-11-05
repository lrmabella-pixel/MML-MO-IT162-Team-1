# Presentation Script — MO-IT162 Terminal Assessment
### Team A3101 (Esquivel, Fuentebella, Abella, Baluso)

*Each section below corresponds to one slide in the deck. Read naturally — this is meant as a guide, not something to memorize word-for-word.*

---

## Slide 1 — Cover

Good day, everyone. We're Team A3101, and today we're presenting our Terminal Assessment for MO-IT162, Data Analytics Fundamentals. This covers our full journey with the FinMark Corporation dataset — from data preprocessing and exploratory data analysis in Milestone 1, through to the data visualization work we completed in Milestone 2.

---

## Slide 2 — Why This Matters to FinMark

Before we get into the data, let's talk about why this analysis matters. FinMark Corporation is planning to use customer data for three future machine learning initiatives: customer segmentation, purchase behavior prediction, and sentiment analysis. But before any model can be built, the underlying data needs to be reliable. That's the purpose of this milestone — we reviewed and visualized our earlier exploratory findings across three datasets: Demographics, Transactions, and Social Media Interactions, to confirm the data is ready, or to flag where it isn't.

---

## Slide 3 — Datasets & Approach

We worked with three datasets that all connect through a shared CustomerID. Demographics gives us customer profile information like Age and Gender. Transactions gives us spending behavior — Amount, Product Category, and Transaction Date. And Social Media Interactions gives us engagement data and Sentiment.

For our tools, we used Pandas to load, clean, and merge the datasets; NumPy to calculate descriptive statistics like mean, median, and standard deviation; and Matplotlib and Seaborn to build our charts — histograms, bar charts, a scatter plot, a box plot, and a correlation heatmap.

---

## Slide 4 — Distributions: Age & Transaction Amount

Let's start with two of our key variables. For Age, most of our customers fall between 15 and 75 years old, with a mean of about 45.4 and a standard deviation of roughly 19.7. But we identified 63 anomalous records — ages of exactly -1 or 150 — which clearly fall outside any realistic range and need to be investigated.

For Transaction Amount, the median is about 496.6, with an interquartile range of around 518. Here, we found 70 transactions with an amount at or below zero, including a value of -100 that showed up repeatedly. These could represent refunds, voided purchases, or data-entry errors, and we flagged them for further investigation rather than assuming they're mistakes.

---

## Slide 5 — Sentiment Classes Are Imbalanced

Moving to our categorical data — the Sentiment count plot shows a clear imbalance. Positive, Neutral, and Negative are the dominant categories, each with 800 to 900-plus records. But Very Positive and Very Negative are dramatically underrepresented, with only 32 and 34 records respectively.

We also want to highlight the 309 records labeled "Unknown." These aren't a real sentiment — they represent missing data that was imputed during our Week 3 preprocessing. We're calling this out specifically because treating "Unknown" as if it were a genuine opinion could mislead a future sentiment classification model.

---

## Slide 6 — Age Doesn't Predict Spending

Here we looked at relationships between variables. The correlation between Age and Transaction Amount came out to just 0.021 — essentially zero. Both our scatter plot and our correlation heatmap confirmed this: there's no meaningful linear relationship between a customer's age and how much they spend.

We also compared average Transaction Amount across the five Product Categories. The range was narrow — from about 470 for Health and Beauty up to 510 for Home and Garden — meaning no single category clearly dominates in average spending.

---

## Slide 7 — A Late-2024 Decline Worth Investigating

This chart tracks average Transaction Amount over time. What stood out to us is that September and October 2024 recorded the two lowest monthly averages in the entire dataset — 405.94 and 359.05.

We want to be careful about how we interpret this. This is a real pattern worth flagging, but on its own, two low months don't prove a lasting shift in customer behavior. It could be seasonal, related to a change in transaction mix, or driven by some external business factor. We're recommending this get investigated further rather than treating it as a confirmed trend.

---

## Slide 8 — What the Charts Reveal About Data Quality

To summarize our data-quality findings: we have the 63 Age anomalies, the 70 nonpositive Transaction Amounts, and the 309 Unknown Sentiment records.

One important insight here: our box plot did not flag the 70 nonpositive transactions as statistical outliers, because the overall spread of the data was wide enough to include them. This tells us something important — statistical outlier detection alone isn't enough. We need to apply domain knowledge alongside the statistics to catch issues like these.

---

## Slide 9 — What This Means for FinMark's ML Roadmap

Tying this back to FinMark's three ML goals: since Age alone doesn't predict spending well, any future segmentation model will need to combine multiple variables, not rely on Age by itself. For sentiment classification, the class imbalance means a model could struggle to learn the rarer Very Positive and Very Negative categories unless the team applies resampling or class weighting. And across the board, these data-quality issues need to be resolved and documented before any model training begins, so we're not building predictions on top of unreliable data.

---

## Slide 10 — Recommendations & Closing

To close, here are our four recommendations: first, investigate and resolve the Age and Transaction Amount anomalies, with clear before-and-after documentation. Second, apply resampling or class weighting to address the Sentiment imbalance. Third, investigate the September-October 2024 decline against seasonal and business factors before concluding it reflects a real change in behavior. And fourth, keep a clear, documented verification trail so future milestones can trace exactly what was checked and resolved.

Overall, this visualization work confirmed and sharpened what we found in Milestone 1. With these recommendations addressed, FinMark's data will be in a strong position to support reliable machine learning development.

Thank you — we're happy to take any questions.
