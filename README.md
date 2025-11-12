

https://colab.research.google.com/drive/1C7v9wLWzGOUDXYJF2als2T_FyVKXpa-S?usp=sharing



## Summary:

### Data Analysis Key Findings

*   **Data Preparation**: The initial dataset was processed by converting `InvoiceDate` to datetime objects and removing records with `CustomerID = 0`. The `Sales` column was calculated as `Quantity * UnitPrice`. The cleaned DataFrame contained 47,671 entries.
*   **RFM Metric Calculation**:
    *   **Recency**: Calculated as the number of days since the last purchase from a `snapshot_date` (one day after the latest `InvoiceDate` in the dataset). For example, `CustomerID 12346.0` had a Recency of 142 days.
    *   **Frequency**: Calculated as the count of unique invoices per customer. For instance, `CustomerID 12346.0` had a Frequency of 2.
    *   **Monetary**: Calculated as the sum of total sales for each customer. For example, `CustomerID 12346.0` had a Monetary value of \$0.00, while `CustomerID 12347.0` had \$475.39.
    *   These metrics were computed for 1,428 unique customers and combined into a single `rfm_df`.
*   **RFM Scoring**: Recency, Frequency, and Monetary metrics were assigned scores from 1 to 5 using quantile-based methods. For Recency, lower values received higher scores (e.g., `pd.qcut` with `labels=[5, 4, 3, 2, 1]`). For Frequency and Monetary, higher values received higher scores, utilizing percentile ranks to handle identical values accurately.
*   **RFM Segment Creation**: A `RFM_Segment_String` was created by concatenating the individual R, F, and M scores (e.g., '555'). A composite `RFM_Score` was calculated by summing the R, F, and M scores, ranging from 3 to 15.
*   **Customer Segmentation**: Customers were categorized into five distinct segments based on their `RFM_Score`:
    *   **Champions**: `RFM_Score` \>= 13 (20 customers)
    *   **Loyal Customers**: `RFM_Score` \>= 10 (234 customers)
    *   **Potential Loyalist**: `RFM_Score` \>= 7 (579 customers)
    *   **At Risk**: `RFM_Score` \>= 4 (511 customers)
    *   **Lapsed**: `RFM_Score` < 4 (84 customers)
*   **Segment Analysis**:
    *   'Champions' emerged as the most valuable segment, exhibiting the lowest average Recency (23.8 days), highest average Frequency (15.65 transactions), and highest average Monetary value (\$7639.01).
    *   'Potential Loyalist' and 'At Risk' segments represent the largest portions of the customer base with 579 and 511 customers, respectively.
    *   Visualizations confirmed these distributions, with 'Champions' clearly showing the highest average monetary contribution per customer.

### Insights or Next Steps

*   **Targeted Campaigns**: Leverage the 'Champions' and 'Loyal Customers' segments for exclusive offers and loyalty programs to maintain their engagement and maximize lifetime value, given their high frequency and monetary contributions.
*   **Re-engagement Strategies**: Develop specific re-engagement campaigns for 'At Risk' and 'Lapsed' customers, focusing on incentives to encourage repeat purchases and prevent further churn, as these segments collectively represent a significant portion of the customer base.
