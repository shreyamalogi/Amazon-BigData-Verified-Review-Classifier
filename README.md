

# Amazon-BigData-Verified-Review-Classifier

### **Scalable Predictive Intelligence | PySpark MLlib | GCP Dataproc**

## 📌 Executive Summary

This project engineered a **Scalable Big Data Pipeline** to classify review authenticity within the Amazon ecosystem. By deploying a distributed **Random Forest Classifier** on **Google Cloud Platform (GCP)**, the system identifies "Verified Purchases" with high precision. This mitigates the impact of fraudulent reviews on recommender systems and search rankings, ensuring data integrity in consumer analytics.

## 🛠️ Technical Architecture & System Design

This repository demonstrates professional-grade proficiency in cloud-native data engineering and machine learning:

### 1. Distributed Data Processing (PySpark ETL)

* **High-Volume Ingestion**: Orchestrated a distributed pipeline to process **~8GB of JSONL data**, leveraging Spark's lazy evaluation for memory optimization.
* **Schema Evolution**: Successfully managed complex nested JSON structures, including flattening image attachment metadata for relational compatibility.
* **Resource Optimization**: Implemented a 10% sampling strategy (`fraction=0.1`) for rapid model iteration and cost-efficiency during cluster development.

### 2. Cloud Infrastructure (GCP)

* **Dataproc Orchestration**: Provisioned and managed a **Google Cloud Dataproc** cluster to handle compute-intensive training tasks.
* **GCS Integration**: Optimized I/O performance by using **Google Cloud Storage** as the primary data lake for raw assets and processed results.

### 3. Machine Learning & Predictive Modeling

* **Predictive Pipeline**: Developed a **Random Forest Model** via **PySpark MLlib** to predict review verification status based on feature sets like helpfulness ratios and rating distributions.
* **Feature Engineering**: Utilized `VectorAssembler` to create feature tensors and `Tokenizer` for unstructured review text analysis.
* **Evaluation**: Achieved measurable accuracy in classification, proving the viability of automated trust-signal detection.

### 4. Big Data Analytics (Apache Hive)

* **SQL-Style Analytics**: Integrated **Apache Hive** for complex analytical queries, identifying top-reviewed products and calculating verified purchase percentages.
* **Data Persistence**: Managed the export of partitioned data back to GCS using `coalesce(1)` for consolidated reporting.

## 📊 Dataset & Analytical Insights

* **Source**: Amazon Product Review Dataset (Toys & Games).
* **Volume**: ~8GB of raw review metadata.
* **KPIs Tracked**: Average ratings, review helpfulness density, and stopword-optimized word frequency distributions.

## 🧰 Tech Stack

| Tier | Tool / Platform | Purpose |
| --- | --- | --- |
| **Compute** | **Apache Spark (PySpark)** | Distributed data processing and ML. |
| **Cloud** | **GCP Dataproc** | Managed Spark/Hadoop cluster infrastructure. |
| **Storage** | **GCP GCS / Hive** | Scalable object storage and analytical warehousing. |
| **Modeling** | **PySpark MLlib** | Production-scale classification algorithms. |

## 🚀 Business Impact

* **Trust Calibration**: Automated the detection of unverified reviews to improve consumer confidence.
* **Scalable ROI**: Proven ability to handle enterprise-level datasets (GB to TB scale) with near-linear performance gains.
* **End-to-End Ownership**: Managed the complete data lifecycle—from cloud ingestion to predictive deployment.

## 👨‍💻 Project Stewardship

* **Lead Developer**: **Shreya Malogi** (Founder @ [Codemacrocosm](https://github.com/shreyamalogi))
* **Academic Context**: Portfolio project refined during MSc Data Analytics studies to demonstrate production-scale engineering.
* **Status**: **Production-ready architectural proof-of-concept**. Optimized for horizontal scalability within enterprise ecosystems.
