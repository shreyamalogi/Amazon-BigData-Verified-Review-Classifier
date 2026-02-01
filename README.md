# Amazon-BigData-Verified-Review-Classifier

### **Scalable Predictive Intelligence | PySpark MLlib | GCP Dataproc**

## 📖 The Narrative: Securing the Digital Marketplace

In a global marketplace like Amazon, the integrity of a **"Verified Purchase"** is the cornerstone of consumer trust. Fraudulent or unverified reviews can distort recommender systems and mislead millions of shoppers. This project tells the story of building a **Scalable Big Data Pipeline**—moving beyond local processing to the cloud—to automate the detection of review authenticity using distributed Machine Learning.



---

## 🏗️ Chapter 1: The Heavy Lifter (Distributed ETL)

Processing ~8GB of raw JSONL data is impossible on a standard machine. I architected a distributed pipeline to handle the volume.

* **Lazy Evaluation**: Leveraged Spark's execution engine to optimize memory usage during high-volume ingestion.
* **Schema Evolution**: Handled complex, nested JSON structures by flattening metadata for relational compatibility.
* **Sampling for Speed**: During the development phase, I implemented a **10% sampling strategy** (`fraction=0.1`) to iterate rapidly on the model without incurring unnecessary cloud costs.

---

## ☁️ Chapter 2: The Cloud Engine (GCP Dataproc)

To solve the computational challenge, I took the project to the **Google Cloud Platform (GCP)**.

* **Dataproc Orchestration**: I provisioned a multi-node cluster specifically for compute-intensive Spark jobs.
* **The Data Lake**: Optimized I/O performance by integrating **Google Cloud Storage (GCS)** as the primary storage layer, ensuring seamless data flow between the lake and the Spark driver.

---

## 🤖 Chapter 3: Predictive Intelligence at Scale

With the infrastructure set, I deployed **PySpark MLlib** to build a classifier that doesn't just run—it scales.

* **Distributed Random Forest**: Built a classification model to predict "Verified" status based on feature tensors like helpfulness ratios and rating distributions.
* **Feature Tensors**: Used `VectorAssembler` and `Tokenizer` to transform unstructured review text and metadata into high-dimensional tensors ready for distributed training.
* **Relational Insights**: Integrated **Apache Hive** to perform SQL-style analytics, identifying top-reviewed products and verifying purchase percentages across the dataset.

---

## 🌐 Cloud Infrastructure & Deployment Guide

This project is architected to run on a multi-node distributed cluster. Follow these steps to provision the production environment:

### 1. Data Lake Configuration (GCS)

* **Create Bucket**: Provision a Google Cloud Storage bucket (e.g., `gs://amazon-review-analytics/`).
* **Data Ingestion**: Upload the `Toys_and_Games.jsonl` file into a directory named `/raw_data/`.
* **Script Upload**: Move your `main.py` and `mllib_model.py` into a `/scripts/` folder.

### 2. Provisioning the "Engine" (GCP Dataproc)

Submit this command via the **GCP Cloud Shell** to create a managed Spark/Hadoop environment:

```bash
gcloud dataproc clusters create toy-analytics-cluster \
    --region=europe-west3 \
    --master-machine-type=n1-standard-2 \
    --worker-machine-type=n1-standard-2 \
    --num-workers=2 \
    --image-version=2.0-debian10 \
    --enable-component-gateway \
    --optional-components=HIVE_WEBHCAT

```

### 3. Submitting the Spark Job

Once the cluster status shows **"Running,"** submit the PySpark job:

```bash
gcloud dataproc jobs submit pyspark gs://[YOUR_BUCKET]/scripts/main.py \
    --cluster=toy-analytics-cluster \
    --region=europe-west3

```

---



## 📊 Dataset & Analytical Insights
* **Source**: [Amazon Product Review Dataset (2018) - Toys & Games](https://nijianmo.github.io/amazon/index.html)
* **Volume**: ~8GB of raw review metadata (JSONL format).
* **KPIs Tracked**: Average ratings, review helpfulness density, and stopword-optimized word frequency distributions.
* **Scope**: This project specifically processes the "Toys and Games" category to evaluate trust signals at scale.

| Tier | Tool / Platform | Purpose |
| --- | --- | --- |
| **Compute** | **Apache Spark (PySpark)** | Distributed data processing and ML. |
| **Cloud** | **GCP Dataproc** | Managed Spark/Hadoop cluster infrastructure. |
| **Storage** | **GCS / Hive** | Scalable object storage and analytical warehousing. |
| **Modeling** | **PySpark MLlib** | Production-scale classification algorithms. |

---

## 🚀 Business Impact

* **Trust Calibration**: Automated the detection of unverified reviews to improve consumer confidence.
* **Scalable ROI**: Proven ability to handle enterprise-level datasets (GB to TB scale) with near-linear performance gains.
* **End-to-End Ownership**: Managed the complete data lifecycle—from cloud ingestion to predictive deployment.

## 👨‍💻 Project Stewardship

* **Lead Developer**: **Shreya Malogi** (Founder @ [Codemacrocosm](https://github.com/shreyamalogi))
* **Status**: **Production-ready architectural proof-of-concept**. Optimized for horizontal scalability within enterprise ecosystems.



