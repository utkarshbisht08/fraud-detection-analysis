# UPI Fraud Detection Analysis

An exploratory analysis of **26,393 UPI transactions** to identify patterns and transaction characteristics associated with fraudulent activity. The dataset contains **65 columns**, with **17.2% of transactions labeled as fraud**.

The analysis focused on understanding the data, validating potential fraud indicators, and identifying patterns that could be useful for transaction risk assessment.

## What I Did

* Reviewed all **65 columns** to understand their meaning, identify redundant fields, and remove columns with no analytical value.
* Checked the dataset for **missing values and duplicate records**.
* Investigated columns such as `url_referrer` and `request_description`, which contained substantial missing values but were found to be structurally related to specific transaction types rather than missing at random.
* Analyzed **7 potential fraud indicators**, considering both fraud rate and sample size to avoid drawing conclusions from small groups.
* Cross-validated key findings using **Excel PivotTables** and **Python/pandas**.
* Created visualizations using **Matplotlib and Seaborn** to identify and communicate the strongest patterns.

## Key Findings

Several transaction characteristics showed strong associations with fraudulent activity:

Screen mirroring indicators: Transactions where an installed screen-sharing application was combined with relevant camera/screen-capture permissions showed a **100% fraud rate across 692 transactions**.
* **UPI handle verification:** Unverified UPI handles showed a **100% fraud rate**, compared with **0% for verified handles** in this dataset.
* **Authorization method:** OTP-based authorization showed a **100% fraud rate**, compared with approximately **15% for PIN-based authorization**.
* **PIN entry method:** Transactions involving a pasted PIN showed a **100% fraud rate**.
* **Transaction initiation:** Link-based transactions showed a **100% fraud rate**, compared with approximately **15% for in-app transactions**.
* **Transaction amount:** Transactions above ₹10,000 showed a fraud rate close to **100%**, compared with approximately **13% below this threshold**.

# Business Recommendation

The analysis suggests that certain transaction characteristics could be useful as **risk indicators for additional verification**, particularly:

* Unverified UPI handles
* OTP-based authorization
* Pasted PINs
* Link-based transaction initiation
* Screen-sharing or screen-mirroring indicators
* High-value transactions, particularly those above ₹10,000

These findings should be treated as **dataset-specific associations rather than standalone fraud rules**. A production fraud detection system would require validation on larger and more representative transaction data before implementing such thresholds.

# Tools Used

Python: Pandas, NumPy, Matplotlib, Seaborn
Excel: PivotTables and cross-validation
Jupyter Notebook

# Files

fraud_analysis.ipynb — Data cleaning, exploration, analysis, visualizations, and findings
fraud_dataset.csv — Dataset used for the analysis
