# banking-dashboard-powerbi
Power BI dashboard and Python EDA analysing loans, deposits, and client segments for 3,000 banking customers
# Banking Customer Analysis | Power BI & Python

## About This Project
A bank holds thousands of customer records, but the raw table doesn't show where the money is, who borrows most, or how customers use different accounts. This project explores 3,000 banking client records in Python, then presents loans, deposits, and client segments in a four-page interactive Power BI dashboard.

## Questions I Set Out to Answer
- How large are the bank's loan and deposit books, and what are they made of?
- Which customer groups (income band, nationality, length of relationship) hold the most loans and deposits?
- Do customers who hold money in one account type also hold it in others?
- Does income or age relate to how much customers save or borrow?

## Data
Banking client dataset with **3,000 records and 25 fields**, covering age, nationality, occupation, estimated income, loans, credit cards, checking, savings, and foreign currency balances, and the year the client joined. Customer name and contact columns were removed before publishing.

## Tools
| Purpose | Tool |
|---|---|
| Data exploration and correlation analysis | Python (Pandas, Matplotlib, Seaborn) |
| Dashboard and measures | Power BI (DAX, slicers, multi-page navigation) |
| Data storage |

## Approach
1. **Prepared the data:** checked structure and missing values (none found), converted the join date, and grouped clients by estimated income into **Low (up to $100K)**, **Mid ($100K to $300K)**, and **High (over $300K)**.
2. **Explored it in Python:** category counts, summary statistics, distributions of each balance, and a correlation heatmap.
3. **Built the dashboard:** four pages (Home, Loan Analysis, Deposit Analysis, Summary) with filters for gender, banking relationship, investment advisor, and time period.

## Headline Numbers
| Total Loans | Total Deposits | Savings Balances | Total Fees |
|---|---|---|---|
| $4.38bn | $3.77bn | $698.73M | $158.19M |

*Total loans = bank loans + business lending + credit card balances. Total deposits = bank deposits + checking + savings + foreign currency accounts.*

## What the Data Shows
**Where the money is**
- Business lending ($2.60bn) makes up about 59% of the loan book, larger than personal bank loans ($1.77bn).
- European clients are 44% of the customer base and hold about 44% of bank loans. Asian clients are 25% of clients and hold about 25% of loans, so loans are spread in line with customer numbers.

**How customers use accounts**
- Bank deposits move closely with checking balances (correlation 0.84) and savings balances (0.75). Customers who keep more money in one account tend to keep more in others.
- Foreign currency balances are only moderately related to other accounts (0.31 to 0.41).
- Loans, business lending, and card balances are moderately related to each other (0.35 to 0.42), so heavy borrowers often borrow in several ways.

**Income and age**
- Estimated income has only a weak-to-moderate link with balances (0.26 to 0.33), and its strongest link is with superannuation savings (0.37). Income alone does not predict how much a client holds.

## Dashboard Pages
**Home:** headline KPIs with gender and time filters.

**Loan Analysis:** loans by banking relationship, income band, nationality, and length of engagement.

**Deposit Analysis:** deposit types by nationality, income band, and engagement period.

**Summary:** all main KPIs on one page.

## Limitations
- Some Client IDs are reused by different people, so counting distinct IDs (2,940) gives fewer clients than the 3,000 records in the file.
- Correlations show that things move together, not that one causes the other.
- The data has no dates for balances, so trends over time can't be measured.

## Repository Contents
| File | Description |
|---|---|
| `Banking_Dashboard.pbix` | Power BI dashboard |
| `BankEDA.ipynb` | Python exploratory analysis |
| `Banking.csv` | Dataset |


## Acknowledgements
Learned the workflow through a guide; analysis and write-up done by me.
