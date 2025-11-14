
# 📊 E-commerce RFM Analysis

A comprehensive customer segmentation analysis using RFM (Recency, Frequency, Monetary) methodology to identify customer segments and provide actionable business insights for an e-commerce dataset.

## 🎯 Project Overview

This project performs RFM analysis on e-commerce transaction data to segment customers based on their purchasing behavior. RFM analysis is a proven marketing technique used to quantitatively rank and group customers based on the recency, frequency, and monetary total of their recent transactions.

## 🗂️ Project Structure

```text
e_commerce_rfm_analysis/
│
├── e_commerce_RFM_analysis.ipynb    # Main Jupyter notebook with complete analysis
├── e_commerce.csv                   # Dataset file
└── README.md                        # Project documentation
```

## 📁 Dataset

The dataset contains e-commerce transaction data with the following key features:

- **InvoiceNo**: Unique transaction identifier
- **StockCode**: Product identifier
- **Description**: Product description
- **Quantity**: Number of items purchased
- **InvoiceDate**: Transaction date and time
- **UnitPrice**: Price per unit
- **CustomerID**: Unique customer identifier
- **Country**: Customer's country

## 🔍 Analysis Methodology

### 1. Data Preprocessing

- Convert `InvoiceDate` to datetime format
- Remove records with `CustomerID = 0`
- Calculate `Sales` column as `Quantity × UnitPrice`
- Handle missing values and duplicates

### 2. RFM Metrics Calculation

- **Recency (R)**: Days since last purchase from snapshot date
- **Frequency (F)**: Total number of transactions per customer
- **Monetary (M)**: Total amount spent per customer

### 3. RFM Scoring

- Assign scores from 1-5 using quantile-based methods
- Recency: Lower values get higher scores (recent customers)
- Frequency & Monetary: Higher values get higher scores

### 4. Customer Segmentation

Customers are categorized into five segments:

- **Champions** (RFM Score ≥ 13): Best customers
- **Loyal Customers** (RFM Score ≥ 10): Regular customers
- **Potential Loyalists** (RFM Score ≥ 7): Promising customers
- **At Risk** (RFM Score ≥ 4): Need attention
- **Lapsed** (RFM Score < 4): Lost customers

## 📈 Key Findings

### Dataset Overview

- **Total Records**: 47,671 transactions after cleaning
- **Unique Customers**: 1,428 customers analyzed
- **Time Period**: Historical e-commerce transactions

### Customer Segments Distribution

| Segment | Count | Avg Recency | Avg Frequency | Avg Monetary |
|---------|-------|-------------|---------------|--------------|
| Champions | 20 | 23.8 days | 15.65 | $7,639.01 |
| Loyal Customers | 234 | - | - | - |
| Potential Loyalists | 579 | - | - | - |
| At Risk | 511 | - | - | - |
| Lapsed | 84 | - | - | - |

### Key Insights

- **Champions** represent the most valuable segment with highest monetary value and purchase frequency
- **Potential Loyalists** and **At Risk** segments contain the majority of customers (76% combined)
- Clear differentiation between segments enables targeted marketing strategies

## 🚀 Business Recommendations

### 1. Targeted Campaigns

- Focus on **Champions** and **Loyal Customers** with:
  - Exclusive offers and early access to new products
  - Premium customer service
  - Loyalty reward programs

### 2. Re-engagement Strategies

- Develop campaigns for **At Risk** and **Lapsed** customers:
  - Personalized discount offers
  - Win-back email campaigns
  - Special promotions to encourage repeat purchases

### 3. Growth Opportunities

- Convert **Potential Loyalists** to loyal customers:
  - Targeted product recommendations
  - Personalized shopping experiences
  - Frequency-based incentives

## 🛠️ Technologies Used

- **Python 3.x**
- **Pandas** - Data manipulation and analysis
- **NumPy** - Numerical computations
- **Matplotlib** - Data visualization
- **Seaborn** - Statistical data visualization
- **Jupyter Notebook** - Interactive development environment

## 📝 How to Run

1. Clone this repository
2. Install required dependencies:

   ```bash
   pip install pandas numpy matplotlib seaborn jupyter
   ```

3. Open the Jupyter notebook:

   ```bash
   jupyter notebook e_commerce_RFM_analysis.ipynb
   ```

4. Run all cells to reproduce the analysis

## 🔗 Additional Resources

- **Google Colab Version**: [Open in Colab](https://colab.research.google.com/drive/1C7v9wLWzGOUDXYJF2als2T_FyVKXpa-S?usp=sharing)

## 📧 Contact

For questions or suggestions regarding this analysis, please feel free to reach out.

---

*This project demonstrates the practical application of RFM analysis in customer segmentation for e-commerce businesses, providing actionable insights for data-driven marketing strategies.*
