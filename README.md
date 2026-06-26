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
| Power BI | Dashboard, KPI calculations and customer segmentation |

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

- Standardised and stripped whitespace across all text columns
- Retained missing CustomerIDs (filled with 0) as guest transactions
- Converted InvoiceDate to datetime and created a YearMonth column
- Removed duplicate rows
- Derived `Revenue` column (`Quantity` × `UnitPrice`)
- Filtered out non-product stock codes (POST, DOT, BANK CHARGES etc.) in Power BI
- Separated cancellation invoices from genuine purchases
- Classified customers as repeat vs. one-time buyers using Power BI DAX measures

---

## Dashboard Preview

Online Retail Sales & Customer Value Analytics Dashboard<img width="1422" height="799" alt="Dashboard" src="https://github.com/user-attachments/assets/ea6ff96c-4796-4f41-8bf4-fc2fbd000312" />

Online Retail Sales & Customer Value Analytics Dashboard (dashboard/Dashboard.png)
---

## Reports
[View Full Insight Report](https://drive.google.com/file/d/1nnNDjVHmTSMBS2glUFaNW1-498tnHrH6/view?usp=drive_link)

---

## AOV Methodology Note

Average Order Value was calculated as:

$$\text{AOV} = \frac{\text{Net Product Revenue}}{\text{Number of Distinct Purchase Invoices}}$$

**Net product revenue** was used (not gross) because:
- Gross revenue includes the value of returned/cancelled orders the business never retained
- Operational line items (postage, fees, etc.) are excluded as they don't reflect product purchasing behavior

**Cancellation invoices were excluded from the order count** because they are reversals of existing orders, not independent purchase events. Counting them would inflate the denominator and artificially deflate AOV.

---

## Author

**Odusanya Oluwatobi**  
Aspiring Data Analyst  
[LinkedIn Profile URL](https://www.linkedin.com/in/oluwatobi-odusanya-6b339834a/) | [GitHub Profile URL](https://github.com/Oluwatobi-Analyst)

---

## Acknowledgements

Dataset sourced from Kaggle as part of an internship programme with 
**AnalystLab Africa**.
Original dataset: Vijay UV (2019). *Online Retail* [Dataset]. Kaggle.
https://www.kaggle.com/datasets/vijayuv/onlineretail/data
