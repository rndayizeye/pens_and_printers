# Pens & Printers: Optimizing New Product Sales Strategies 🖊️

> A data-driven evaluation of three sales methods to identify the most effective approach for a new product launch — combining exploratory analysis, statistical testing, and business KPI design.

Built with Python · DataCamp Data Analyst Certification Project · Real business dataset (15,000 observations)

---

## Business Context

Since 1984, Pens and Printers has supplied office products to large organizations. As digital tools reshape the workplace, their sales strategies must evolve. To launch a new line of office stationery, the company tested **three sales methods** over six weeks:

| Method | Description |
|---|---|
| **Email** | Automated email outreach only |
| **Call** | Direct sales call only |
| **Email + Call** | Email outreach followed by a personal call |

The business question: *Which method maximizes revenue — and is the added time cost of calls worth it?*

---

## Dataset

- **Source:** Internal sales data collected over 6 weeks post-launch
- **Size:** 15,000 observations, 8 variables
- **Variables:** `week`, `sales_method`, `customer_id`, `nb_sold`, `revenue`, `years_as_customer`, `nb_site_visits`, `state`

### Data Cleaning
- Corrected data entry errors in `sales_method` column (`'em + call'`, `'email'` → standardized)
- Replaced missing `revenue` values with zero (no sale recorded)

---

## Analysis

### Customer Distribution
- **Email:** 7,466 customers (50% of base) — most widely used method
- **Call:** 4,962 customers (33%)
- **Email + Call:** 2,572 customers (17%) — smallest segment, highest investment per customer

### Revenue Distribution
Revenue was right-skewed across all methods:
- **Email** generated the highest *total* revenue due to volume
- **Call** generated half the revenue of Email + Call, despite twice the sales volume and 3× the time per customer
- **Email + Call** yielded the highest *average* revenue per customer

### Revenue Over Time (Mean Revenue per Week)

| Week | Call | Email | Email + Call |
|------|------|-------|--------------|
| 1 | $34.51 | $81.62 | $114.09 |
| 2 | $41.98 | $92.79 | $131.88 |
| 3 | $40.19 | $85.91 | $135.76 |
| 4 | $49.35 | $100.27 | $158.17 |
| 5 | $51.26 | $100.10 | $161.13 |
| 6 | $63.06 | $120.34 | $190.66 |

All methods improved over time. Email + Call showed the steepest growth trajectory.

### Statistical Testing
- **ANOVA** tested whether revenue differed significantly across sales methods (α = 0.05)
- Result: **p < 0.0001** — significant differences confirmed
- **Effect size:** η² = 0.54 — sales method explained **54% of the variance in revenue**, a large effect
- **Pairwise comparisons** (Bonferroni correction): All three methods significantly different from each other (p < 0.0001)

### Customer Behavior
- Email + Call customers visited the website more frequently and purchased more products
- Years as a customer did **not** significantly influence outcomes across methods — loyalty alone doesn't predict sales method performance

---

## KPI Recommendation

**Recommended business metric: Average revenue per customer per sales method**

This metric enables:
- Direct, apples-to-apples comparison of method efficiency
- Longitudinal tracking as the product matures
- Resource allocation decisions (time cost of calls vs. revenue return)

---

## Recommendation

> **Continue and scale the Email + Call method.**

Despite the higher time cost per customer, Email + Call generated the highest average revenue, strongest customer engagement, and the steepest revenue growth trajectory over time. The ANOVA confirms this difference is statistically significant and large in magnitude (η² = 0.54) — not a random fluctuation.

Call-only is the least efficient method: twice the volume of Email + Call, three times the time investment per customer, half the revenue return. It should be deprioritized.

---

## Skills Demonstrated

- Data cleaning and validation (handling entry errors, missing values)
- Exploratory data analysis (distribution analysis, revenue trends)
- Statistical hypothesis testing (one-way ANOVA, Bonferroni-corrected pairwise tests, effect size)
- Business metric design and KPI recommendation
- Data storytelling and executive communication

## Tech Stack & Libraries

| Library | Purpose |
|---|---|
| `pandas` | Data loading, cleaning, manipulation |
| `numpy` | Numerical operations |
| `matplotlib` / `seaborn` | Visualization |
| `missingno` | Missing data visualization |
| `scipy.stats` | Chi-square tests, statistical analysis |
| `statsmodels` | ANOVA, pairwise comparisons, MICE imputation |

**Environment:** Python 3 · Google Colab

---

## Reproduce This Analysis

1. Open the notebook in Google Colab or Jupyter
2. Install dependencies:
```bash
pip install pandas numpy matplotlib seaborn missingno scipy statsmodels
```
3. Load `product_sales.csv` and run all cells

---

This project was completed as part of the **DataCamp Data Analyst Professional Certification** — a practical assessment requiring end-to-end analysis on a realistic business dataset, culminating in a presentation to a simulated stakeholder audience.

🎓 Certification earned: **DataCamp Certified Data Analyst** (2024)

---

## Author

**Remy Ndayizeye, MPH, MD**
Epidemiologist | Data Scientist | Virginia Department of Health
[LinkedIn](https://www.linkedin.com/in/remynd) · [DataCamp Portfolio](https://www.datacamp.com/portfolio/remyndayizeye) · [GitHub](https://github.com/rndayizeye)
