# Credit Card Fraud Analytics
**Python · Pandas · PostgreSQL · SQL · Exploratory Data Analysis**

## Project overview
This work-in-progress portfolio project explores patterns in a historical credit-card transaction dataset and considers the business implications of simple fraud-screening rules. The current notebooks focus on data understanding, data quality, descriptive analytics, and SQL validation. **No trained fraud-prediction model is presented here yet.**

## Business questions
- How prevalent is fraud in the dataset?
- How does observed fraud prevalence vary by transaction method and transaction amount?
- What data-quality issues require attention before modeling?
- What trade-offs arise when flagging transactions above a fixed amount threshold?

## Findings to date
| Metric | Observed result |
|---|---:|
| Total transactions | 24,386,900 |
| Fraud-labeled transactions | 29,757 |
| Overall fraud rate | ~0.122% |
| Online transaction fraud rate | ~0.676% |
| Chip transaction fraud rate | ~0.0769% |
| Swipe transaction fraud rate | ~0.0427% |
| Legitimate transactions above $100 | 2,659,851 |
| False-positive rate for flagging amounts above $100 | ~10.92% |

These are descriptive results for this dataset. The $100 rule's recall, precision, and business cost have **not** yet been fully evaluated.

## Repository contents
- `notebooks/01_Business_Data_Understanding.ipynb` — Pandas-based inspection, missingness, transaction amount, payment method, time, and merchant-category exploration.
- `notebooks/02_SQL_Business_Data_Understanding.ipynb` — PostgreSQL retrieval, SQL aggregations, transaction-method comparisons, and preliminary threshold analysis.
- `requirements.txt` — Python packages used by the notebooks.

## Reproducing the analysis
1. Obtain the **IBM credit-card transactions** dataset from its authorized original source. The raw transaction data is not distributed in this repository.
2. Install Python packages: `pip install -r requirements.txt`.
3. For notebook 1, place the CSV file at the path referenced in the notebook or update that path.
4. For notebook 2, load the dataset into your own PostgreSQL database and adapt the database/table/column names to the notebook's SQL. Connection parameters may be set with `PGHOST`, `PGPORT`, `PGUSER`, `PGPASSWORD`, and `PGDATABASE`. Never commit secrets.

**Note:** The notebooks were cleaned of saved execution outputs for publication. They have not been re-executed in this package because the underlying data and local database are not included.

## Limitations and next steps
- Class imbalance makes accuracy alone an inadequate evaluation metric.
- Transaction method is associated with observed fraud rates; these comparisons do not establish causation.
- Complete the $100 threshold confusion matrix, recall, precision, and cost analysis.
- Add validated model evaluation and a business-facing dashboard in subsequent milestones.
- Document dataset provenance and license before sharing any raw data.

## Author
Dwight Dunn — Mathematics and Data Science
