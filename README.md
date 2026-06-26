# Online Retail Analytics

**Revenue, returns and AOV analysis on the Online Retail dataset — Python for cleaning & EDA, Power BI for visualization**

---

## Project Overview

This is an end-to-end data analytics project analyzing a real-world transactional dataset from a UK-based online retailer. The goal was to uncover key business insights around revenue performance, customer behavior, product trends, and return/cancellation impact; answering questions a business stakeholder or logistics team would actually care about.

The project covers the full analytics workflow: raw data ingestion, cleaning, exploratory data analysis (EDA) in Python, and an interactive business intelligence dashboard built in Power BI.

---

## Dataset

- **Source:** [Online Retail Dataset](https://www.kaggle.com/datasets/vijayuv/onlineretail)
- **Period covered:** December 2010 – December 2011
- **Records:** 541,909 transactions
- **Business context:** UK-based non-store online retailer selling gift-ware. Many customers are wholesalers.

> The raw dataset is not included in this repository due to file size. You can download it directly from the link above.

---

## Tools & Technologies

| Tool | Purpose |
|---|---|
| Python (pandas, numpy) | Data cleaning, transformation, EDA |
| Jupyter Notebook | Exploratory analysis and documentation |
| Power BI | Interactive dashboard and visualizations |

---

## Business Questions Answered

| # | Question | Purpose |
|---|---|---|
| 1 | What is the total gross revenue, net product revenue, and revenue lost to returns? | Establishes overall business scale and revenue leakage |
| 2 | How does revenue change month over month? | Identifies growth trends and seasonality |
| 3 | Which countries generate the highest total revenue? | Identifies geographic drivers of business |
| 4 | Who are the top 10 highest revenue-generating customers? | Identifies key accounts (critical in wholesale retail) |
| 5 | What is the split between repeat vs. one-time buyers? | Measures customer loyalty and retention |
| 6 | Which products generate the highest revenue? | Identifies best-performing products |
| 7 | What is the proportion and financial impact of returns/cancellations? | Quantifies revenue leakage and data quality |
| 8 | What is the average value of a single customer order, and how does it vary by country (AOV)? | Helps logistics prioritize shipping optimization |

---

## Key Findings

- **Gross Sales Revenue:** £10.25M
- **Total Returns Revenue:** £475.90K
- **Net Revenue:** £9.77M
- **Revenue Returns Rate:** 4.64%
- **Average Order Value (AOV):** £494.17
- **Peak month:** November 2011 (£1.50M) — consistent with holiday season demand
- **Top revenue country (ex-UK):** Netherlands at £285.45K
- **Highest AOV by country:** Netherlands at £3.05K, suggesting high-value wholesale customers
- **Customer loyalty:** 65.59% of customers are repeat buyers (2.85K), 34.41% are one-time buyers (1.49K)
- **Top product:** Regency CakeStand 3 Tier, generating £174.16K in revenue

---

## Data Cleaning Highlights

The raw dataset required significant cleaning before analysis:

- Removed operational/non-product stock codes (POST, DOT, C2, M, BANK CHARGES, CRUK, AMAZONFEE, etc.)
- Separated cancellation invoices (InvoiceNo starting with "C") from genuine purchases
- Handled missing CustomerID values
- Removed rows with negative or zero unit prices
- Derived a `Revenue` column as `Quantity × UnitPrice`
- Classified customers as repeat vs. one-time buyers based on invoice frequency

---

## Dashboard Preview

![Online Retail Sales & Customer Value Analytics Dashboard]<img width="1422" height="799" alt="Dashboard" src="https://github.com/user-attachments/assets/ea6ff96c-4796-4f41-8bf4-fc2fbd000312" />


---

## AOV Methodology Note

Average Order Value was calculated as:

$$\text{AOV} = \frac{\text{Net Product Revenue}}{\text{Number of Distinct Purchase Invoices}}$$

**Net product revenue** was used (not gross) because:
- Gross revenue includes the value of returned/cancelled orders the business never retained
- Operational line items (postage, fees, etc.) are excluded as they don't reflect product purchasing behavior

**Cancellation invoices were excluded from the order count** because they are reversals of existing orders, not independent purchase events. Counting them would inflate the denominator and artificially deflate AOV.

---

## Repository Structure

```
online-retail-analytics/
│
├── data/
│   └── README.md               # Dataset source and download instructions
│
├── notebooks/
│   └── online_retail_eda.ipynb # Python cleaning and EDA notebook
│
├── dashboard/
│   └── dashboard_screenshot.png # Power BI dashboard export
│
└── README.md
```

---

## How to Run

1. Download the dataset from the [UCI repository](https://archive.ics.uci.edu/dataset/352/online+retail) and place the `.xlsx` file in the `/data` folder
2. Open `notebooks/online_retail_eda.ipynb` in Jupyter Notebook or JupyterLab
3. Run all cells sequentially
4. The Power BI dashboard (`.pbix`) can be opened in [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free)

---

## Author

**[Your Name]**  
Aspiring Data Analyst  
[LinkedIn Profile URL](https://www.linkedin.com/in/oluwatobi-odusanya-6b339834a/) | [GitHub Profile URL](https://github.com/Oluwatobi-Analyst)

---

## Acknowledgements

Dataset: Chen, D. (2015). Online Retail [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5BW33
