# Skyrun Customer Retention Analysis

Cohort analysis and RFM segmentation of Skyrun's e-commerce transactions (1 Dec 2024 – 9 Dec 2025), completed as part of the Amdari Data Science Internship.

## Project aim

The project brief stated that Skyrun does a good job of acquiring new customers, but retention has suffered over the past 18 months. The aim of this project was to assess customer retention by acquisition cohort, segment customers by value, and make recommendations for improving retention.

## Files

| File | Description |
|---|---|
| `skyrun_retention_analysis.ipynb` | Jupyter notebook with all the code and outputs |
| `Skyrun_Customer_Analysis_Report.docx` | Final report with findings and recommendations |
| `Skyrun_dataset.zip` | The dataset (unzip before running the notebook) |
| `Retention_heatmap.png` | Cohort retention heatmap |
| `rfm_profile.png` | Customer segment profile chart |

## Method

1. **Data cleaning:** removed cancelled orders (invoice numbers starting with "C") and rows without a customer ID, and read the invoice date as a date.
2. **Cohort retention:** grouped customers by the month of their first order and tracked the percentage who ordered again in each following month. December 2024 (customers who were already ordering before the data starts) and December 2025 (only 9 days of data) were excluded.
3. **RFM segmentation:** measured recency, frequency and monetary value for each customer, log-transformed frequency and monetary, standardised all three, and grouped customers with K-Means. The elbow method showed 4 clusters was the best choice.

## Key findings

- On average, only 20% of new customers place a second order in their second month (15–24% across the 2025 cohorts).
- Customer retention is consistently low rather than diminishing over time.
- Champions (668 customers, 15.4%) make up 54.7% of revenue. Together with Loyal Repeaters, about half of all customers account for 88.9% of revenue.
- 1,190 New One-Time Buyers ordered recently but typically have only 1 order, so they are the group that would benefit the most from conversion.

| Segment | Customers | Share of revenue |
|---|---|---|
| Champions | 668 | 54.7% |
| Loyal Repeaters | 1,566 | 34.2% |
| New One-Time Buyers | 1,190 | 5.8% |
| Lost One-Time Buyers | 915 | 5.2% |

## Recommendations

1. Introduce a second-order programme for New One-Time Buyers and all new customers.
2. Introduce a loyalty programme to encourage Loyal Repeaters to order more like Champions.
3. Keep Champions ordering through account management and loyalty perks.
4. Send low-cost win-back offers to Lost One-Time Buyers before the autumn.
5. Make sure a customer ID is captured on every order.

## How to run

1. Unzip `Skyrun_dataset.zip` into the same folder as the notebook. The file should be called `Skyrun dataset.csv`.
2. Install the libraries: `pip install pandas numpy matplotlib seaborn scikit-learn yellowbrick`
3. Open `skyrun_retention_analysis.ipynb` and click **Restart** then **Run All**.

## Tools

Python, pandas, NumPy, Matplotlib, seaborn, scikit-learn, Yellowbrick
