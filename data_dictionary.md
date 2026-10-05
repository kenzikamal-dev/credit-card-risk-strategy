# Data Dictionary

Source: UCI Machine Learning Repository, "Default of Credit Card Clients"
(Taiwan, April to September 2005). 30,000 customers, 24 columns after cleaning.

| Column | Type | Description |
|---|---|---|
| LIMIT_BAL | Numeric | Credit limit in NT dollars (individual + family supplementary credit) |
| SEX | Categorical | 1 = male, 2 = female |
| EDUCATION | Categorical | 1 = graduate school, 2 = university, 3 = high school, 4 = other (0, 5, 6 are undocumented) |
| MARRIAGE | Categorical | 1 = married, 2 = single, 3 = other (0 is undocumented) |
| AGE | Numeric | Age in years |
| PAY_1 | Ordinal | Repayment status in September 2005 (originally named PAY_0) |
| PAY_2 to PAY_6 | Ordinal | Repayment status in August (PAY_2) back to April (PAY_6) |
| BILL_AMT1 to BILL_AMT6 | Numeric | Bill statement amount, September (1) back to April (6) |
| PAY_AMT1 to PAY_AMT6 | Numeric | Amount paid in the previous month, September (1) back to April (6) |
| DEFAULT | Binary (target) | 1 = defaulted next month (October 2005), 0 = did not |

**Repayment status scale (PAY_*):** -1 = paid on time; 1 = payment delayed 1 month; 2 = delayed 2 months; ... 9 = delayed 9 months or more.
The values -2 and 0 are not defined in the original description. A common interpretation (an assumption, not official) is -2 = no credit use and 0 = revolving credit with at least the minimum payment made.

**Known data issues (addressed in notebook 02):**
- Undocumented category codes in EDUCATION and MARRIAGE
- Undefined PAY_* values (-2, 0)
- Negative BILL_AMT values (likely overpayments)
- Some identical rows once ID is removed; kept, since they may be different customers
