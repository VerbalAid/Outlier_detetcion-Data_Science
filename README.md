# Data Science Projects: Outlier & Identity Analysis

This README provides a concise overview of two data science projects focused on **anomaly detection** and **forensic identity analysis**.

---

## 1. SpamBase Outlier Detection

### Objective  
The goal of this project was to perform **unsupervised outlier detection** on legitimate email communications. By isolating “ham” (non-spam) emails, the analysis aimed to identify unusual patterns that deviate from typical legitimate messaging.

### Dataset & Pre-processing  

- **Dataset:** SpamBase Dataset (4,601 instances, 57 features)  
- **Filtering:** Only non-spam (“ham”) emails were retained; the class label was removed to ensure a fully unsupervised setting.  
- **Scaling:** Features were standardized using `StandardScaler` to normalize word and character frequency metrics.

### Algorithms Used  

- **Isolation Forest:** Identifies anomalies by randomly partitioning feature space.  
- **Local Outlier Factor (LOF):** Detects outliers based on local density relative to neighbouring data points.

### Analysis & Insights  

The models identified a small subset of legitimate emails as outliers. These emails represent rare communication patterns or edge cases where legitimate messages exhibit atypical characteristics, helping define the boundaries of “normal” behaviour.

---

## 2. “Hacker Theory” Identity Analysis

### Objective  
This project tested a hypothesis related to **identity spoofing** in fraudulent activity. Initial observations suggested that younger users were the primary outliers, raising the question of whether this pattern reflected genuine behaviour or data manipulation.

### Datasets & Methodology  

Two data sources were compared:

- **Claimed Transaction Data:** Demographic information (e.g. age) provided during transactions.  
- **Actual Account Data:** Verified demographic records of account owners.

### Method  

- **Mismatch Analysis:** Calculated the age gap between the claimed user and the actual account owner.  
- **Identity Noise Detection:** Identified discrepancies where the claimed age differed from the verified age.

### Logic & Processing  

- Custom mismatch logic quantified **identity noise** (e.g. a transaction claiming a 22-year-old user when the account owner is 55).  
- Data was filtered to isolate spoofed identity cases.

### Findings & Interpretation  

The results confirmed the **“Hacker Theory.”** The apparent concentration of Gen Z outliers was largely due to identity spoofing, where scammers impersonated younger users to avoid suspicion.

Once identity noise was removed, the number of genuine victims aged 18–30 dropped to zero. The analysis revealed that fraudsters primarily target older users (31–45 and above) while masquerading as younger individuals.

---

## Conclusion  

Together, these projects demonstrate how unsupervised anomaly detection and forensic data analysis can uncover hidden patterns, challenge misleading initial assumptions, and provide deeper insight into complex data behaviour.
