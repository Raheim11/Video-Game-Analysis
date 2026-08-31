#  Understanding Video Game Trends: Genre & Review Score Analysis

## Overview

This project analyzes a dataset of **1,770 video games released between 2004 and 2010** to investigate trends in game genres and review scores.

Using Python and statistical inference, the analysis answers two primary questions:

1. **What proportion of video games are classified as Action games?**
2. **Is the average video game review score statistically different from 75?**

The project demonstrates practical applications of **data cleaning, exploratory data analysis, bootstrapping, confidence intervals, hypothesis testing, and data visualization**.

---

##  Research Questions

### Confidence Interval Analysis

> What proportion of games in the dataset are classified as Action games, and what is the 95% confidence interval for the corresponding population proportion?

### Hypothesis Testing

> Does the data provide sufficient statistical evidence that the population mean review score differs from 75?

The hypothesis test uses:

* **Null hypothesis (H₀):** μ = 75
* **Alternative hypothesis (Hₐ):** μ ≠ 75
* **Significance level:** α = 0.05

---

##  Key Findings

### Action Game Proportion

Out of **1,770 games**, approximately **60.79%** were classified as Action games.

A bootstrap procedure with **5,000 resamples** produced a 95% confidence interval of:

**58.53% – 62.94%**

This suggests that the underlying proportion of Action games is plausibly within this range for games from the analyzed period.

### Review Scores

The average review score was:

**68.43**

A bootstrap hypothesis test comparing the observed mean against the null hypothesis value of **75** produced a two-sided p-value of approximately:

**0.0000**

Because the p-value is far below the 0.05 significance level, the analysis **rejects the null hypothesis** and provides strong evidence that the population mean review score differs from 75.

The observed mean is below 75, suggesting that the difference is primarily in the lower direction.

---

##  Technologies & Tools

* **Python**
* **Pandas** — data loading, cleaning, and manipulation
* **NumPy** — numerical computations and statistical resampling
* **Matplotlib** — data visualization
* **Jupyter Notebook** — analysis and documentation
* **Bootstrap Resampling** — statistical inference

---

##  Methodology

### 1. Data Preparation

The dataset was loaded using Pandas and examined for relevant variables, including:

* Genre
* Action classification
* Review Score
* Year Released
* Sales
* Publisher
* Other game characteristics

The `Action` variable was converted into a logical indicator:

```python
is_action = 1 if Action == 1 else 0
```

Review scores were converted to numeric values and missing observations were removed before analysis.

### 2. Confidence Interval

The proportion of Action games was estimated using the sample proportion:

```text
p̂ = 0.6079
```

A bootstrap distribution was generated using **5,000 resamples with replacement**. The 2.5th and 97.5th percentiles of the bootstrap distribution were used to construct the 95% confidence interval.

### 3. Hypothesis Test

The review-score analysis tested:

```text
H₀: μ = 75
Hₐ: μ ≠ 75
```

A bootstrap null distribution was created by centering the observed review scores around the hypothesized population mean of 75.

The p-value was calculated by determining the proportion of bootstrap means at least as extreme as the observed sample mean.

### 4. Visualization

The project includes visualizations of:

* Bootstrap distribution of Action-game proportions
* Distribution of Review Scores
* Bootstrap null distribution for the mean Review Score

---

##  Results Summary

| Analysis                     |          Result |
| ---------------------------- | --------------: |
| Number of games              |           1,770 |
| Action game proportion       |          60.79% |
| 95% CI for Action proportion | 58.53% – 62.94% |
| Mean Review Score            |           68.43 |
| Hypothesized mean            |              75 |
| Bootstrap p-value            |        ≈ 0.0000 |
| Hypothesis test conclusion   |       Reject H₀ |

---

##  Business & Industry Relevance

The analysis demonstrates how statistical methods can be used to extract insights from real-world entertainment data.

Understanding genre distribution can help **game developers, publishers, and marketers** evaluate the prevalence of different game categories. Review-score analysis can also provide insight into overall product reception and establish a foundation for investigating relationships between **genre, critical reception, sales, and release year**.

---

##  Limitations

* The dataset only covers games released between **2004 and 2010**, so the findings may not generalize to modern video games.
* The analysis does not account for potential differences between gaming platforms.
* Review scores may vary systematically by publisher, genre, or release year.
* Bootstrap methods provide useful statistical inference but do not eliminate potential sampling or dataset-selection bias.

---

##  Future Analysis

Potential extensions of this project include:

* Comparing review scores across different genres
* Identifying which genres have the highest average review scores
* Analyzing the relationship between review scores and sales
* Examining how game trends changed from 2004–2010
* Comparing review scores across gaming platforms
* Building predictive models for game sales or review scores
* Investigating whether genre influences commercial success

---

##  Project Structure

```text
video-game-analysis/
│
├── Review Project.ipynb    # Main analysis notebook
├── video_games.csv         # Dataset
└── README.md               # Project documentation
```

---

##  Skills Demonstrated

**Data Analysis:**
Data cleaning • Exploratory Data Analysis • Statistical inference • Data interpretation

**Statistics:**
Confidence intervals • Bootstrap resampling • Hypothesis testing • P-values • Population estimation

**Programming:**
Python • Pandas • NumPy • Matplotlib • Jupyter Notebook

**Data Visualization:**
Histograms • Bootstrap distributions • Statistical result visualization

---

##  Project Takeaway

This project demonstrates the ability to move from a raw dataset to **statistically supported conclusions** using Python. Rather than relying solely on descriptive statistics, the analysis applies resampling and inferential methods to estimate population characteristics and evaluate statistical hypotheses.
