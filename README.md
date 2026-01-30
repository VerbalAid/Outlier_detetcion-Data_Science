This README provides a concise overview of two distinct data science projects focused on anomaly detection and forensic data analysis.
Data Science Projects: Outlier & Identity Analysis
#1. SpamBase Outlier Detection
Why?

The objective was to perform unsupervised outlier detection on legitimate communications. By isolating "ham" (non-spam) emails, the project aimed to identify unusual patterns or "odd" emails that deviate from standard legitimate messaging.

#Datasets & Pre-processing

    Dataset: The SpamBase Dataset (4,601 instances, 57 features).

#Cleaning: The data was filtered to include only non-spam instances, and the 'class' label was removed to ensure the models operated in a purely unsupervised manner.

    Preparation: Features were scaled using StandardScaler to ensure uniform variance across word and character frequency metrics.

#Algorithms Used

    Isolation Forest: Used to isolate anomalies by randomly partitioning features.

    Local Outlier Factor (LOF): Used to detect outliers based on the local density of data points relative to their neighbours.

##Analysis & Interpretation

The models successfully identified a small percentage of "ham" emails as outliers. These represent rare communication types or instances where legitimate emails share characteristics typically found in anomalies, providing insight into the boundaries of "normal" data.
#2. The "Hacker Theory" Analysis
Why?

This project was designed to test a hypothesis regarding Identity Spoofing. It investigated why initial data suggested younger users were the primary outliers in fraudulent activity.

##Datasets & Methodology

    Datasets: A comparative study between two data sources:

        Claimed Transaction Data: Demographics (age) provided during a transaction.

Actual Account Data: Verified records of the account owners.

##Method: A Mismatch Analysis was conducted to calculate the age gap between the person performing the transaction and the actual owner.

##Algorithms & Logic

    Custom Mismatch Logic: Calculated the "Identity Noise" by identifying discrepancies (e.g., a transaction claiming a 22-year-old user when the owner is actually 55).

    Data Filtering: Isolated instances where the claimed age did not match the record age.

##Analysis & Interpretation

    The Findings: The "Hacker Theory" was proven correct—the high number of Gen Z outliers in initial charts was actually "Identity Noise" caused by scammers pretending to be younger to blend in.

Conclusion: Once identity noise was removed, the 18–30 age group for victims dropped to zero. The analysis proved that hackers primarily target older users (aged 31–45 and above) while spoofing younger identities.
