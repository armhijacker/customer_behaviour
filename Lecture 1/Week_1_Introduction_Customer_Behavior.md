# Customer Behavior and Data Science
### Lecture Presentation

---

## Course Overview

1. **Introduction:** Customer Behavior and Data Science
2. **Data Preparation** for Customer Behavior Analysis
3. **Handling Missing Values**
4. **Anomaly / Outlier Detection**

---

# Part 1 — Introduction: Customer Behavior and Data Science

---

## What Is Customer Behavior Analysis?

**Consumer behavior analysis** = study of how people make purchase decisions about a product, service, or organization.

**Key questions it answers:**
- How do consumers choose between alternatives?
- What influences brand preference?
- Where, when, and why do they buy?
- How can marketing campaigns be improved?

**Core idea:** Psychology explains *why* people behave as they do — data science helps us measure, predict, and act on that behavior at scale.

---

## Psychology Meets Business

- **Behaviorism** — systematic study of observable behavior — originated in psychology.
- Marketers adapted these ideas to understand and improve customer relationships.
- Psychology alone is not enough: business teams must combine behavioral theory with **data science techniques**.

> Goal: turn behavioral insight into measurable, actionable decisions.

---

## Three Layers of Customer Analytics

| Layer | Question | Example |
|-------|----------|---------|
| **Descriptive** | What happened? | Weekly signups, funnel drop-offs |
| **Predictive** | What will happen? | Revenue forecast, churn probability |
| **Prescriptive** | What should we do? | Next-best offer, sales prioritization |

Every tracked action needs three components:
- **Who** — unique user ID
- **What** — action type + metadata
- **When** — timestamp

---

## Descriptive Analytics in Practice

**Trends analysis**
- Aggregate actions over time (daily / weekly / monthly)
- First step to understand direction of change

**Customer journey analysis**
- Link steps using consistent user IDs
- Map funnels and find where users drop off

**Example questions:**
- Is the pricing page blocking signups?
- Which campaigns acquire the best customers?
- How does retention compare across cohorts?

---

## Predictive Analytics

Uses historical data to forecast future outcomes (never 100% accurate, but often reliable enough).

**Statistical modeling**
- Regression, correlations between variables
- Example: predict revenue from age, gender, category, season

**Machine learning**
- Learns patterns from large datasets automatically
- Deep learning / neural networks — powerful but:
  - Need lots of data
  - Often a "black box"
  - Can inherit human bias in training data

**Promising direction:** Recurrent Neural Networks (RNN) on sequential journey data.

---

## Prescriptive Analytics & Personalization

**Prescriptive analytics** — short-term, *individual-level* recommendations:
- Next-best product or offer
- Rank users by conversion or churn likelihood
- Trigger sales / success team outreach

**Personalization signals** (even without explicit profile data):
- Search queries, clicks, categories viewed, color preferences

**Productivity use case (B2B):**
- Alert sales when a user visits pricing 3+ times
- Alert CS when login frequency drops sharply

---

## Common Customer Analysis Methods

| Method | Purpose |
|--------|---------|
| Survey analysis | Attitudes, satisfaction |
| Customer segmentation | Group similar customers |
| Journey mapping | Touchpoint experience |
| Transactional analysis | Purchase patterns |
| Factor / cluster analysis | Discover hidden segments |
| Regression analysis | Predict outcomes |
| Neural networks | Complex pattern detection |

**Analytics workflow:** Gather data → detect patterns → extract insights → support decisions → optimize experience.

---

## Factors That Shape Consumer Behavior

| Factor | Examples |
|--------|----------|
| **Psychological** | Perception, motivation, beliefs, attitude |
| **Personal** | Age, income, occupation, lifestyle |
| **Social** | Family, community, peer influence |
| **Geographical** | Climate, location, local culture |

**Benefits of studying behavior:** better campaigns, cultural fit, brand perception, lifestyle-aligned products.

---

## Sources of Customer Data

- In-store and online sales data
- Survey and customer service data
- Sales department records
- Advertising and web analytics platforms
- Marketing automation and loyalty programs
- Mobile app, wearables, and IoT data

> More data sources = richer behavioral picture — but also more cleaning and integration work.

---

# Part 2 — Data Preparation for Customer Behavior Analysis

---

## Where Data Prep Fits in a Project

Typical data science workflow:

1. Problem identification
2. **Exploratory Data Analysis (EDA)**
3. **Data cleaning**
4. **Feature engineering**
5. Modeling
6. Project delivery

> *"EDA is an attitude — a willingness to look for things we believe are not there, as well as those we believe to be there."* — John Tukey

---

## Exploratory Data Analysis (EDA)

**Goal:** Build intuition about the dataset before modeling.

**Step 1 — Dataset overview**
- Summary statistics for all variables
- Check missing values (NAs)
- Review data types

**Step 2 — Each variable individually**
- Histograms / box plots for numeric data
- Bar charts for categorical data
- Outlier detection

**Step 3 — Variable interactions**
- Scatterplot matrices
- Correlation heatmaps
- Cross-tabulations

---

## Data Cleaning Checklist

1. **Remove useless data** — irrelevant columns, test records
2. **Handle missing values** — drop, impute, or flag (Part 3)
3. **Handle outliers** — investigate, cap, or remove (Part 4)
4. **Remove duplicates** — same transaction recorded twice

**Always ask:** *Does this row represent a real customer action?*

---

## Feature Engineering

Create new variables to unlock patterns:

| Technique | Example |
|-----------|---------|
| Datetime features | Hour, weekday, month from timestamp |
| Type conversion | Continuous → categorical bins |
| Dummy variables | One-hot encode country, product category |
| Derived metrics | TotalPrice = Quantity × UnitPrice |
| Domain logic | Days since last purchase, order frequency |

Good features often matter more than model choice.

---

## EDA Example — Key Takeaways

Using e-commerce transaction data:

- **CustomerID missing?** Drop those rows — can't analyze behavior without identity.
- **Negative quantities?** Data error — remove or investigate.
- **Extreme prices?** Often non-product codes (postage, discounts) — filter out.
- **Time patterns:** Purchases peak at certain hours; seasonality visible by month.
- **Geography:** Highly imbalanced (e.g., 90%+ from one country).

Save cleaned data before moving to modeling.

---

# Part 3 — Handling Missing Values

---

## Why Missing Values Matter

Most ML models **cannot accept NaN** — they will throw errors.

**Common causes of missing data:**
- Equipment or system errors
- Respondent unavailable or forgot to answer
- Accidental deletion
- Data not collected for certain records

**Bad default:** Fill everything with 0 → often hurts model accuracy significantly.

**Better approach:** Understand *why* data is missing, then choose the right strategy.

---

## Strategy 1 — Delete

| Approach | When to use | Risk |
|----------|-------------|------|
| **Drop column** | >50% missing, column not critical | Lose potentially useful signal |
| **Drop row** | Few rows affected, key fields missing | Reduce sample size |

Example: Drop rows where `CustomerID` is null — you cannot track behavior without it.

---

## Strategy 2 — Simple Imputation

Fill missing values with a substitute:

| Variable type | Fill with |
|---------------|-----------|
| Numeric | Mean or median |
| Categorical | Mode (most frequent) |
| Any | Sentinel value (0, -999) to mark "unknown" |
| Categorical | New category: `"Missing"` |

```python
df['Age'].fillna(df['Age'].mean(), inplace=True)
```

Use `sklearn.impute.SimpleImputer` for pipeline-friendly imputation.

---

## Strategy 3 — Advanced Imputation

**Missing indicator column**
- Add binary flag: `Age_is_missing = True/False`
- Model learns that "missing" itself carries information

**K-Nearest Neighbors (KNN) imputation**
- Find similar records and impute from neighbors
- Better when variables are correlated (e.g., age ↔ fare ↔ class)

**Regression imputation**
- Train model on complete rows to predict missing values
- Example: predict `Age` from `Sex`, `Pclass`, `Fare`

> Rule of thumb: start simple → validate → upgrade if accuracy gains justify complexity.

---

# Part 4 — Anomaly / Outlier Detection

---

## What Is an Anomaly?

An **anomaly (outlier)** = a data point that deviates significantly from normal behavior.

Also called: peculiarity, exception, surprise.

**Why it matters in customer analytics:**
- Fraud detection (unusual transactions)
- Data quality issues (negative quantities, typos)
- VIP / high-value customer identification
- System errors in tracking pipelines

---

## Three Types of Anomalies

| Type | Description | Example |
|------|-------------|---------|
| **Point** | Single value far from the rest | $50,000 purchase in a $20 avg basket |
| **Contextual** | Unusual in a specific context | Ice cream spend normal in summer, odd in winter |
| **Collective** | Group of points anomalous together | Unusual burst of 50 orders in 1 minute |

---

## Supervised vs Unsupervised Detection

| Setting | Training data | Difficulty |
|---------|---------------|------------|
| **Supervised** | Labeled "normal" / "anomaly" | Ideal — but labels are rare |
| **Unsupervised** | No labels | Hardest — model must find anomalies itself |

**Supervised algorithms:** SVM, k-NN, decision trees, Bayesian networks

**Unsupervised algorithms:** k-means, LOF, DBSCAN, one-class SVM, autoencoders

---

## Statistical Methods (Quick & Interpretable)

**Z-Score**
- Flag values beyond ±3 standard deviations from the mean
- Works well for roughly normal distributions

**IQR (Interquartile Range)**
- Outlier if value < Q1 − 1.5×IQR or > Q3 + 1.5×IQR
- Robust to skewed data — use box plots to visualize

**Percentile-based**
- Remove top/bottom 1–5% of values
- Simple but can discard valid extreme customers (whales)

---

## ML-Based Anomaly Detection Algorithms

| Algorithm | Idea | Best for |
|-----------|------|----------|
| **k-NN** | Distance to k nearest neighbors | Fraud, text anomalies |
| **LOF** | Local density vs neighbors | Density-based outliers |
| **k-means** | Points far from cluster centroids | Numeric, segmented data |
| **SVM (one-class)** | Learn boundary of "normal" region | High-dimensional data |
| **DBSCAN** | Points not assigned to any cluster | Spatial / 2D feature space |
| **Neural networks** | Autoencoders, RNN on time series | Sequential / complex patterns |

---

## Practical Workflow for Outliers

1. **Visualize first** — histograms, box plots, scatter plots
2. **Investigate** — is it an error, fraud, or a real VIP?
3. **Decide:**
   - **Remove** — clear data error (negative quantity)
   - **Cap (winsorize)** — limit extreme values
   - **Keep & flag** — valid but rare (whale customer)
   - **Transform** — log scale to reduce skew
4. **Document** — record what was removed and why

> Never delete outliers blindly — understand the business context first.

---

## Summary

| Topic | Key takeaway |
|-------|--------------|
| **Customer behavior** | Psychology + data science → understand, predict, and influence purchases |
| **Analytics layers** | Descriptive → Predictive → Prescriptive |
| **Data preparation** | EDA → clean → engineer features → then model |
| **Missing values** | Delete, impute, or flag — match strategy to the missingness pattern |
| **Outliers** | Detect, investigate, then remove / cap / keep based on context |

**Next steps:** Apply these techniques to real customer datasets in the lab sessions.

---

## Further Reading

- [Customer Analytics For Dummies](https://www.amazon.com/Customer-Analytics-Dummies-Jeff-Sauro/dp/1118937597) — Jeff Sauro
- [Data Science for Business](https://www.amazon.com/Data-Science-Business-Data-Analytic-Thinking-ebook/dp/B00E6EQ3X4) — Provost & Fawcett
- [Doing Data Science](https://www.oreilly.com/library/view/doing-data-science/9781449363871/) — O'Neil & Schutt
- [R for Marketing Research and Analytics](https://www.springer.com/gp/book/9783030143152) — Gattiker
- Course repo: [customer_behaviour](https://github.com/armhijacker/customer_behaviour)
