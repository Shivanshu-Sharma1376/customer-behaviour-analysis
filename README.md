# Customer Shopping Behavior Analysis

End-to-end data analytics project on 3,900 retail transactions, using **Python**, **MySQL** and **Power BI** to uncover spending patterns, customer segments, product preferences and subscription behavior, and to turn them into business recommendations.


---

## Overview

The goal is to answer practical business questions such as:

- Who spends the most, and which customer groups drive revenue?
- Do subscribers spend more than non-subscribers?
- Which products depend most on discounts?
- How loyal is the customer base, and how can loyalty be increased?

## Dataset

| Item | Detail |
|---|---|
| Rows | 3,900 purchases |
| Columns | 18 |
| Demographics | Age, Gender, Location, Subscription Status |
| Purchase details | Item, Category, Purchase Amount (USD), Season, Size, Color |
| Behavior | Discount Applied, Promo Code Used, Previous Purchases, Frequency of Purchases, Review Rating, Shipping Type, Payment Method |
| Data quality | 37 missing values in `Review Rating` |

## Tools

- **Python** (pandas, Jupyter Notebook): data loading, EDA, cleaning, feature engineering
- **MySQL**: business analysis with SQL
- **Power BI**: interactive dashboard

## Steps

### 1. Exploratory Data Analysis and Cleaning (Python)
- Loaded the data with pandas and inspected it with `df.info()` and `df.describe()`
- Filled the 37 missing `Review Rating` values using the **median rating of each product category**
- Renamed columns to snake_case
- Created **`age_group`** (binned ages) and **`purchase_frequency_days`** features
- Found `discount_applied` and `promo_code_used` to be redundant and dropped `promo_code_used`
- Loaded the cleaned DataFrame into MySQL for SQL analysis

### 2. Business Analysis (SQL)
Ten business questions were answered with MySQL:

1. Revenue by gender
2. High-spending customers who used discounts
3. Top 5 products by average rating
4. Standard vs. Express shipping spend
5. Subscribers vs. non-subscribers
6. Most discount-dependent products
7. Customer segmentation (New, Returning, Loyal)
8. Top 3 products per category
9. Repeat buyers and subscriptions
10. Revenue by age group

### 3. Dashboard (Power BI)
An interactive dashboard with filters for subscription status, gender, category and shipping type. It shows KPIs (customers, average purchase amount, average rating), subscription split, and revenue and sales by category and age group.

## Results

| Metric | Finding |
|---|---|
| Average purchase amount | **$59.76** |
| Average review rating | **3.75 / 5** |
| Revenue by gender | Male **$157,890** vs. Female **$75,191** |
| Subscribers | **27%** of customers (1,053 of 3,900) |
| Subscriber vs. non-subscriber spend | $59.49 vs. $59.87 average, so subscribing doesn't lead to higher spend yet |
| Shipping | Express averages **$60.48** vs. Standard **$58.46** |
| Top revenue age group | Young Adults (**$62,143**), closely followed by Middle-aged ($59,197) |
| Customer segments | Loyal: 3,116, Returning: 701, New: 83 |
| Most discount-dependent items | Hat (50.0%), Sneakers (49.7%), Coat (49.1%) |
| Highest-rated items | Gloves (3.86), Sandals (3.84), Boots (3.82) |
| Top category by revenue and sales | Clothing |

## Business Recommendations

- **Boost subscriptions:** Subscribers are only 27% of customers and don't spend more, so add exclusive benefits that give people a reason to subscribe.
- **Loyalty programs:** Reward repeat buyers to keep and grow the Loyal segment.
- **Review discount policy:** Several products have discount rates near 50%, so balance sales boosts with margin control.
- **Product positioning:** Feature top-rated and best-selling products in campaigns.
- **Targeted marketing:** Focus on high-revenue age groups and express-shipping users.

## Project Files

| File | What it is |
|---|---|
| `customer_shopping_behavior.csv` | Dataset |
| `customer shopping behaviour.ipynb` | Python notebook (EDA, cleaning, feature engineering) |
| `customers.sql` | MySQL queries for the 10 business questions |
| `customer behaviour dashboard.pbix` | Power BI dashboard file (open with Power BI Desktop) |
| `dashboard.png` | Dashboard screenshot |

## How to Run

1. Clone the repo
   ```bash
   git clone https://github.com/Shivanshu-Sharma1376/customer-behaviour-analysis.git
   cd customer-behaviour-analysis
   ```
2. Install the Python libraries
   ```bash
   pip install pandas numpy sqlalchemy pymysql jupyter
   ```
3. Open `customer shopping behaviour.ipynb` in Jupyter and run it to clean the data and load it into MySQL (update the connection details with your own credentials).
4. Run `customers.sql` in MySQL (version 8.0 or later is needed for window functions).
5. Open `customer behaviour dashboard.pbix` in Power BI Desktop to explore the dashboard.

## Author

**Shivanshu Sharma**
GitHub: [Shivanshu-Sharma1376](https://github.com/Shivanshu-Sharma1376)
