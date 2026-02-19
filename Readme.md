# AI-Powered Customer Churn & Risk Intelligence Platform
### AWS Athena • Amazon Bedrock • Multi-LLM Evaluation • Machine Learning

---

## Executive Summary

This project demonstrates a production-style AI analytics platform built on AWS that enables:

- Natural language business queries
- Automatic SQL generation using Large Language Models
- Multi-table cloud data warehouse analytics
- Fraud exposure analysis
- Revenue risk detection
- Predictive churn modeling
- Explainable AI insights

The system simulates an enterprise-grade financial analytics environment, integrating cloud-native architecture, LLM orchestration, and predictive modeling.

---

# Business Context

Customer churn is one of the largest revenue risks for financial institutions.

This platform answers:

- Which geography has highest churn risk?
- What is total revenue exposure from churned customers?
- Which high-value customers are at risk?
- What fraud exposure exists across regions?
- What is the predicted churn probability for key segments?

The goal is to bridge business language and data intelligence.

---

# Cloud Architecture

User → LLM → SQL → Athena → DataFrame → ML Model → Insight

### Cloud Stack Used

| Service | Purpose |
|----------|----------|
| Amazon S3 | Data Lake Storage |
| AWS Athena | Serverless SQL Engine |
| Amazon Bedrock | LLM-based SQL generation |
| IAM | Access control |
| boto3 | Programmatic AWS access |
| Google Colab | ML training environment |

---

# Multi-Model LLM Evaluation Strategy

During development, multiple enterprise-grade models were evaluated:

| Provider | Model | Outcome |
|----------|--------|----------|
| OpenAI | GPT-4o-mini | API rate limit (quota exceeded) |
| Anthropic | Claude Haiku (Claude 3 Haiku) | Marketplace payment restriction |
| Amazon Titan | titan-text-lite-v1 | Model deprecated |
| Amazon Titan Express | Invalid model version |
| Anthropic Claude Sonnet | Payment restriction |
| **Meta LLaMA 3 (Bedrock)** | meta.llama3-8b-instruct-v1:0 | Final production model |

This reflects real-world LLM governance, billing constraints, and cloud-native evaluation processes.

Final production model: **Meta LLaMA 3 via Amazon Bedrock**

---

# Dataset Overview

## 1. Customer Churn Dataset
Source: European Bank Customer Dataset (Maven Analytics)

Records: ~10,000 customers  
Columns: 13 features including:

- CustomerId
- CreditScore
- Geography
- Gender
- Age
- Tenure
- Balance
- NumOfProducts
- HasCrCard
- IsActiveMember
- EstimatedSalary
- Exited (Churn Flag)

## 2. Transaction Dataset (PaySim Simulation)

Records: 500,000 transactions

Features:

- step
- type
- amount
- nameOrig
- nameDest
- oldbalanceOrg
- newbalanceOrig
- oldbalanceDest
- newbalanceDest
- isFraud
- isFlaggedFraud

---

# Data Engineering Process

1. Uploaded raw CSV datasets to Amazon S3
2. Created external Athena tables:
   - customers
   - transactions
3. Created synthetic aligned table:
   - customer_transaction_summary_fixed
4. Ensured referential integrity:
   customers.customer_id = customer_transaction_summary_fixed.customer_id
5. Validated JOIN row counts
6. Verified multi-table analytics results

---

# Natural Language to SQL Engine

Implemented using Amazon Bedrock (Meta LLaMA 3).

Enhancements included:

- Prompt engineering with schema awareness
- Multi-table JOIN enforcement
- SQL sanitization
- SQL safety validator
- Syntax auto-correction
- Separation of prediction vs analytics logic
- Error handling for truncated model responses

---

# Example Business Queries Executed

✔ Show churn rate by geography  
✔ Show fraud count by geography  
✔ Show revenue exposure of churned customers  
✔ Identify high-value churn segments  
✔ Detect customers with high transaction activity  
✔ Predict churn probability for high-value customers  

---

# Predictive Analytics Layer

Model: Logistic Regression  
Train/Test Split: 80/20  

Performance:

- Accuracy: 0.815
- ROC-AUC: 0.734

The model predicts churn probability and integrates directly into the chatbot pipeline.

---

# Explainable AI

Model coefficients analyzed to identify top churn drivers:

- Inactive membership
- Credit score
- Balance levels
- Geographic segmentation
- Product count

This enables strategic retention campaign planning.

---

# Business Impact Simulation

If 32% churn rate exists in Germany and high-balance customers average €119,000:

Estimated revenue exposure from churned customers can exceed millions in portfolio value.

This platform allows proactive identification of those segments.

---

# Power BI & BI Strategy Alignment

---

# Key Capabilities Demonstrated

- Cloud-native analytics architecture
- Serverless data warehousing
- Multi-LLM experimentation
- Production-grade prompt engineering
- SQL sanitization and governance
- Multi-table modeling
- Predictive ML integration
- Explainable AI
- Cloud IAM integration
- Real-world error troubleshooting

---

# Future Roadmap

- XGBoost model upgrade
- Streamlit executive dashboard
- EC2 deployment
- REST API endpoint
- Automated retraining pipeline
