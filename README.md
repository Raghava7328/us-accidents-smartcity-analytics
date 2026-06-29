# us-accidents-smartcity-analytics
# 🚦 US Accidents Smart City Analytics (AWS Big Data Project)

A cloud-native big data analytics pipeline built using AWS services to analyze over 7M+ US traffic accident records and generate insights for smart city planning and road safety improvement.

---

## 📌 Project Overview

This project demonstrates an end-to-end **Big Data Analytics pipeline** on AWS for analyzing road accidents in the United States. It includes:

- Data ingestion from Kaggle using EC2
- Scalable storage using Amazon S3
- ETL processing using AWS Glue
- SQL analytics using Amazon Athena
- Interactive dashboards using Amazon QuickSight
- Machine Learning model for accident severity prediction

---

## ☁️ Cloud Architecture

This project is built using **Amazon Web Services (AWS)**:

- Amazon S3 – Data Lake storage  
- Amazon EC2 – Data ingestion & preprocessing  
- AWS Glue – ETL and data transformation  
- Amazon Athena – Serverless SQL analytics  
- Amazon QuickSight – Data visualization  
- Amazon CloudWatch – Monitoring & logs  
- IAM – Secure access control  

---

## 🧰 Tech Stack

- Python (Pandas, Boto3, PyArrow)
- SQL (Athena Queries)
- AWS Cloud Services
- Machine Learning (Random Forest)
- Parquet Data Format

---

## 📂 Dataset

- Source: Kaggle US Accidents Dataset  
- Size: ~1GB+  
- Records: 7+ million accident records  
- Features: Weather, severity, location, timestamps, traffic conditions

---

## ⚙️ Project Pipeline

### 1. Data Ingestion
- Dataset downloaded from Kaggle using EC2
- Uploaded to Amazon S3 (`raw/` folder)

### 2. Data Storage
- Organized S3 structure:

raw/
processed/
scripts/
athena-results/
models/

### 3. Data Processing (AWS Glue)
- Removed duplicates
- Handled missing values
- Feature engineering (hour, day, month, year)
- Converted CSV → Parquet
- Partitioned by state and year

### 4. Data Analysis (Athena)
Key insights:
- Accident hotspots by state
- Weather impact on severity
- Peak accident hours
- Weekday vs weekend comparison
- Traffic signal impact

### 5. Visualization (QuickSight)
- KPI dashboards
- Geographic analysis
- Trend analysis
- Severity distribution

### 6. Machine Learning Model
- Algorithm: Random Forest Classifier
- Accuracy: ~68.5%
- Prediction: Accident severity levels

---

## 📊 Key Insights

- California has the highest accident rate
- Peak accidents occur during rush hours (7–9 AM, 4–6 PM)
- Rain, snow, and fog increase severity
- Weekdays have significantly more accidents than weekends
- Areas without traffic signals have higher accident severity

---

## 🤖 Machine Learning

- Model: Random Forest
- Features:
  - Weather conditions
  - Temperature, humidity, visibility
  - Traffic signals
  - Time-based features
- Output: Accident severity prediction

---

## 💰 Cost Optimization

- Used serverless AWS architecture
- Converted CSV → Parquet (reduced cost)
- Partitioned datasets (year/state)
- Used AWS Glue & Athena pay-per-use model
- S3 lifecycle policies for storage savings

---

## 🔐 Security

- IAM roles instead of hardcoded credentials
- S3 Block Public Access enabled
- Secure access using least privilege principle
- Encrypted data transfer (HTTPS)

---

## 📈 Monitoring

- AWS CloudWatch logs for Glue jobs
- ETL performance tracking
- Error monitoring and debugging
- Glue crawler tracking for schema updates

---

## 📁 Project Structure
.
├── ec2_ingestion/
├── glue_etl/
├── athena_queries/
├── ml_model/
├── dashboards/
├── s3_screenshots/
├── cloudwatch_logs/
└── README.md

---

## 🚀 How to Run

1. Launch EC2 instance (Ubuntu)
2. Install dependencies:
```bash
pip install boto3 pandas pyarrow kagglehub
Run ingestion script:
python download_upload.py
Run AWS Glue job for ETL
Query data using Athena
Visualize using QuickSight
Train ML model using processed Parquet data
📌 Future Improvements
Real-time streaming with AWS Kinesis
Deep Learning for severity prediction
API deployment for predictions
Live traffic integration
📚 References
AWS Documentation
Kaggle US Accidents Dataset
Research papers on smart city analytics
👨‍💻 Author

Raghava Krishna Anumari
MSc Data Science
United Kingdom 🇬🇧

⭐ Acknowledgement

This project demonstrates a full end-to-end cloud-based big data pipeline for smart city accident analytics using AWS services.
