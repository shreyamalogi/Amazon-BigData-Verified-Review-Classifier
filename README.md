
# Amazon-BigData-Verified-Review-Classifier

### **Scalable Predictive Intelligence | PySpark MLlib | GCP Dataproc**

## 📌 Executive Summary

This project engineered a **Scalable Big Data Pipeline** to classify review authenticity within the Amazon ecosystem. By deploying a distributed **Random Forest Classifier** on **Google Cloud Platform (GCP)**, the system analyzes millions of records to identify "Verified Purchases" with high precision. This mitigates the impact of fraudulent reviews on recommender systems and search rankings, ensuring data integrity in consumer analytics.

## 🛠️ Technical Architecture & System Design

This repository demonstrates professional-grade proficiency in cloud-native data engineering and machine learning:

### 1. Distributed Data Processing (PySpark)

* **High-Volume ETL**: Orchestrated a distributed pipeline to process **~8GB of JSONL data**, leveraging Spark's lazy evaluation for memory optimization.
* **Schema Management**: Managed complex nested structures into optimized DataFrames for downstream analytics.

### 2. Cloud Infrastructure (GCP)

* **Dataproc Orchestration**: Provisioned and managed a **Google Cloud Dataproc** cluster (Spark/Hadoop) to handle compute-intensive training tasks.
* **Cloud Storage (GCS)**: Optimized I/O performance by integrating **Google Cloud Storage** as the primary data lake for raw and processed assets.

### 3. Machine Learning & Predictive Modeling

* **Predictive Classifier**: Developed a **Random Forest Model** via **PySpark MLlib** to predict review verification status based on feature sets like helpfulness ratios and rating distributions.
* **Feature Engineering**: Implemented advanced transformations to extract signals from unstructured review metadata.

### 4. Big Data Analytics (Apache Hive)

* **Query Optimization**: Integrated **Apache Hive** for SQL-style aggregations, providing deep-dive insights into trust signals.
* **Data Persistence**: Managed relational table structures to support rapid analytical reporting.

## 📊 Dataset Insights

The model analyzes the **Amazon Product Review Dataset (Toys & Games)** focusing on the following feature vectors:

* **Verified Status**: The target variable for classification.
* **Helpfulness Ratio**: Derived feature predicting user engagement and review validity.
* **Metadata Processing**: Handling ~8GB of raw JSONL data via distributed clusters.
- **Location**: `gs://toys555/raw_data/Toys_and_Games.js`
  
## 🧰 Tech Stack

| Tier | Tool / Platform | Purpose |
| --- | --- | --- |
| **Compute** | **Apache Spark (PySpark)** | Distributed data processing and ML. |
| **Cloud** | **GCP Dataproc** | Managed Spark/Hadoop cluster infrastructure. |
| **Storage** | **GCP GCS / Hive** | Scalable object storage and analytical warehousing. |
| **Modeling** | **PySpark MLlib** | Production-scale classification algorithms. |

## 🚀 Business Impact

* **Trust Calibration**: Automated the detection of unverified reviews to improve consumer confidence.
* **Scalable ROI**: Proven ability to handle enterprise-level datasets (GB to TB scale) with near-linear performance gains on multi-node clusters.
* **End-to-End Ownership**: Demonstrates complete lifecycle management from cloud ingestion to predictive deployment.

## 👨‍💻 Project Stewardship

* **Lead Developer**: **Shreya Malogi** (Founder @ [Codemacrocosm](https://github.com/shreyamalogi))
* **Status**: **Production-ready architectural proof-of-concept**. The system is designed for horizontal scalability and modular integration into larger enterprise ecosystems.



---









