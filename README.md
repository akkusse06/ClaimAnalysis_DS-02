
---

# 🩺 Healthcare Claims & Accounts Receivable (AR) Analytics

An end-to-end data processing and analytics project designed to inspect, clean, and analyze medical insurance claims. This project targets optimizations in the **Healthcare Revenue Cycle Management (RCM)** loop by evaluating billing discrepancies, tracking claim statuses, and profiling internal financial risk metrics (AR status).

---

## 📌 Project Overview

Managing insurance claims efficiently is critical for healthcare providers. This project processes transactional raw claim data to diagnose patterns behind operational issues like structural payment friction and high claim denial rates.

By utilizing statistical data validation and structural preprocessing, the repository lays down the baseline architecture needed to mitigate financial leakages before dynamic forecasting operations.

---

## ⚙️ Key Technical Implementations

* **Structured Data Profiling:** Statistical indexing of operational revenue columns (`Billed Amount`, `Allowed Amount`, `Paid Amount`).


* **Data Type Integrity Enforcement:** Transformation and standard formatting of structural tracking variables (e.g., date-time objects).


* **Completeness & Deduplication Audit:** Empirical proofing for missing fields or multi-entry redundancies.


* **Clinical Code Optimization:** Granular tracking of frequency distribution patterns within ICD-10 standard codes (`Diagnosis Code`).


* **Core Exploratory Visualization (EDA):** Feature-driven plotting evaluating multi-variable pricing disparities and multi-class categorical structures.

---

## 📊 Data Anatomy & Dimensional Profiling

The model processes an initial shape of **1,000 records across 15 distinct diagnostic columns**:

| Structural Field | Functional Data Type | Business Analytical Purpose |
| --- | --- | --- |
| **Claim ID / Patient ID** | Identification Key (`object` / `int64`) | Unique system identification tracks. |
| **Billed Amount** | Continuous Currency Numeric (`int64`)| Gross financial amount charged by the provider. |
| **Allowed Amount** | Continuous Currency Numeric (`int64`)| Contractually agreed-upon ceiling cap by insurers. |
| **Paid Amount** | Continuous Currency Numeric (`int64`)| Realized revenue disbursed to the provider. |
| **Procedure / Diagnosis Code** | Clinical Classifications (`int64` / `object`)| CPT and ICD-10 medical classifications. |
| **Insurance Type** | Multi-class Categorical (`object`)| Payer group cohorts (Medicare, Commercial, etc.).|
| **Claim Status / AR Status** | Operational Categorical (`object`)| Transactional billing state & financial aging flag. |

---

## 🛠️ Analytical Insights (Data Preview)

### **1. Financial Distribution Statistics**

```python
# Baseline numerical overview extracted from claim registers
       Billed Amount  Allowed Amount  Paid Amount
count     1000.00000     1000.000000  1000.000000
mean       297.19100      223.112000   200.754000
std        116.36365       90.784731    83.353688
min        100.00000       64.000000    53.000000
max        500.00000      442.000000   423.000000

```

* **Loss Identification:** The difference between the average `Billed Amount` ($\approx 297.19$) and the actual `Paid Amount` ($\approx 200.75$) indicates systematic hair-cuts and dynamic adjustments within contract cycles.

### **2. Clinical ICD-10 Categorization Density**

The analysis indicates high concentration bands among distinct clinical vectors (e.g., `A05.4`, `A06.0`, `A16.1`) which serve as foundational pivot points for multi-variable profiling against denial reason logs.

---

## ### 🧩 How to Run the Pipeline

1. Place your target healthcare dataset inside the root working path as `claim_data.csv`.


2. Initialize your notebook environment and execute the processing notebook sequentially:

```python
import pandas as pd
# Read and run baseline ingestion schema
df = pd.read_csv('claim_data.csv')[cite: 1]

```

---

## ### 📈 Future Extension Roadmap

* **Multicollinearity Diagnostic Tracing:** Apply Variance Inflation Factor (`VIF`) engines to eliminate inter-feature dependency distortions.


* **Machine Learning Denial Prediction:** Implement predictive binary classification tasks targeting high-risk flags (`Claim Status == Denied`) before batch transmission.



---

*Developed as a baseline foundation module for advanced operational healthcare finance reporting.*
