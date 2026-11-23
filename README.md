# Credit Risk Analysis in Buy Now, Pay Later (BNPL) Systems

An exploratory data study of BNPL customer data. It looks at which financial and behavioural factors are linked to customers missing payments or defaulting.

**Course:** First Steps into Data Science, MSc Applied Data Science & Artificial Intelligence, SRH University Munich

**Team:**
- Phaneendra Reddy B S
- Pratham Mandya Basavaraju
- Dwaraka Vaishnavi Mudiraj Chintala

---

## About the project

Buy Now, Pay Later services let customers split a purchase into small instalments. Approval is quick and checks are often light, so some customers miss payments or default. That's a financial risk for BNPL providers.

Our questions:
- Which customer factors are linked to loan defaults, such as credit score, income, repayment behaviour and employment type?
- How can BNPL companies spot high-risk customers early?

## Dataset

- **Source:** [Buy Now and Pay Later FinTech ML Dataset (Kaggle)](https://www.kaggle.com/datasets/shree0910/buy-now-and-pay-later-fintech-ml-dataset/data)
- **Size:** 10,345 BNPL transactions from 6 countries
- **Target variable:** `default_flag`, where 0 means paid and 1 means defaulted

| Group | Columns |
|---|---|
| Demographics | `age`, `gender`, `employment_type`, `location` |
| Financial | `monthly_income`, `credit_score`, `debt_to_income_ratio` |
| Transaction | `purchase_amount`, `product_category`, `bnpl_installments`, `transaction_date` |
| Repayment behaviour | `repayment_delay_days`, `missed_payments` |
| Customer activity | `app_usage_frequency` |
| Risk indicators | `risk_score`, `customer_segment` (Low / Medium / High Risk) |

## Repository structure

```
├── README.md
├── Project_code.ipynb                                  # Analysis notebook
├── Buy_Now_Pay_Later_BNPL_CreditRisk_Dataset.csv       # Dataset
└── PrathamMandyaBasavaraju_Presentation_PDF.pdf        # Final presentation
```

## What the notebook does

1. **Loads the data** and checks its structure, summary statistics and missing values.
2. **Cleans the data.** It drops `user_id` and encodes `gender` (Male = 1, Female = 0).
3. **Explores the data** with these charts:
   - Distribution of `risk_score`
   - Distribution of `default_flag`
   - Correlation heatmap of numeric features
   - Defaults by employment type
   - Employment type vs default status for each country

## Key findings

- Customers who defaulted mostly had **lower credit scores**. Those who repaid generally had higher ones.
- **Lower monthly income** goes with **higher risk scores**. Income and credit score are strongly positively related.
- **Students and unemployed customers** default more often than salaried and self-employed customers.
- **Gender** has little effect on repayment behaviour.
- Most customers have a risk score **between 150 and 300**, which puts them in the medium-risk range.
- **High-risk customers** make up about **83%** of the total risk score.

## Recommendations

- Watch customers with low credit scores, missed payments and repayment delays closely.
- Take extra care when approving loans for students and unemployed customers.
- Use machine learning models, such as a Random Forest classifier, to flag risky customers early.
- Offer payment reminders and flexible repayment plans to reduce missed payments.
- Use risk segments to guide lending and credit-limit decisions.

## How to run

1. Clone the repository:
   ```bash
   git clone https://github.com/Pratham-MB/bnpl-credit-risk-analysis.git
   cd bnpl-credit-risk-analysis
   ```
2. Install the required libraries:
   ```bash
   pip install pandas matplotlib seaborn jupyter
   ```
3. Open the notebook:
   ```bash
   jupyter notebook Project_code.ipynb
   ```
4. Run all cells from top to bottom. The notebook reads the CSV from the same folder.

## Tools used

Python, Jupyter Notebook, pandas, Matplotlib, Seaborn

## References

- Dataset: [Kaggle: Buy Now and Pay Later FinTech ML Dataset](https://www.kaggle.com/datasets/shree0910/buy-now-and-pay-later-fintech-ml-dataset/data)
- Experian: *Buy Now, Pay Later or Deferred Credit payment data: Decision-ready insight on the spending behaviour of BNPL customers*
