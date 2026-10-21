[README.md](https://github.com/user-attachments/files/33787359/README.md)
# 📊 Global Sales Analysis | Python + pandas

*Course project from the Python module of my data analytics training.*

**[Notebook](global_sales_analysis.ipynb)**

## 🔍 Project Overview

Cleaning, merging and exploring a multi-table sales dataset: 1,330 orders across 12 product categories and 45 countries in Europe and Asia, 2010 – July 2017. The goal was to practise a full pandas workflow, from raw CSV files to business-oriented findings, and to check which patterns in the data are real.

## 🗄 Data

- `events.csv` – orders: dates, country code, product, sales channel, units, unit price and cost
- `products.csv` – product categories
- `countries.csv` – country names and regions

## ⚙️ What I Did

1. **Data cleaning:** standardised column names, converted dates and numeric types, normalised text fields, removed 2 orders with missing quantity, checked for impossible values (non-positive prices, negative costs, ship date before order date).
2. **Merging:** joined the three tables into one analytical dataset and validated row counts after each merge.
3. **Metrics:** revenue, cost, profit, margin and shipping time per order.
4. **EDA:** categories, countries and regions, online vs. offline, shipping time, monthly and weekday dynamics.

## 📈 Key Findings

- **Total revenue ~$1.70B, profit ~$501M, margin 29.5%.** 82 orders (~$103M, 6% of revenue) have no country code and are excluded from geographic analysis.
- **Revenue leaders are the most expensive categories, not the most demanded ones.** Office Supplies ($402M), Household ($294M) and Cosmetics ($233M) lead in revenue, but units sold are similar across all 12 categories (440K–618K units). Each category has a single fixed unit price for the whole period, so the revenue ranking mirrors the price ranking.
- **Margins differ widely by category:** from 13.6% (Meat) to 67.2% (Clothes). Clothes sells as many units as other categories; its small revenue share comes from a low unit price ($109).
- **Online and offline are balanced:** 49% vs. 51% of revenue, with almost the same margin (29.9% vs. 29.1%).
- **Shipping time does not affect profit** (r = 0.06).
- **Differences in shipping time between countries are within random variation.** Country averages range from 18 to 33 days, but each country has only 13–40 orders and individual shipping times vary from 0 to 50 days. Shuffling shipping times randomly across countries produces a similar gap (median ~12 days, 95th percentile ~16 days; ANOVA p = 0.44). The same applies to Europe vs. Asia (25 vs. 26 days, p = 0.44).
- **No meaningful weekday pattern** in the number of orders (χ², p = 0.32).

## 💡 What the Data Itself Shows

The dataset looks synthetic: fixed prices per category, units per order spread evenly from 2 to ~10,000, and shipping times spread evenly from 0 to 50 days. Recognising this matters more than the individual numbers: many apparent "insights" (country logistics gaps, weekday peaks) disappear once you check them against what random variation alone would produce.

## 🔁 Revision Note

The commentary inside the notebook was written during the course. When I reviewed the project later, several of those interpretations did not hold up: the country shipping-time gap and weekday peaks are consistent with chance, and Clothes' lower revenue is driven by price rather than sales volume. The findings above reflect the revised analysis.

## 🛠 Stack

`Python` · `pandas` · `NumPy` · `matplotlib` · `seaborn` · `Google Colab`
