# AI-Powered Text-to-SQL Analytics Engine (AWS Athena + Bedrock + ML)
### AWS Athena • Amazon Bedrock • Multi-LLM Evaluation • Predictive ML

---

## Executive Overview

This project demonstrates a cloud-native AI analytics platform designed to:

- Convert natural language business questions into SQL
- Execute serverless analytics on AWS Athena
- Analyze churn risk, fraud exposure, and revenue impact
- Predict churn probability using machine learning
- Deliver explainable AI insights

The system simulates an enterprise-grade financial analytics environment.

---

## Business Problem

Financial institutions face revenue loss due to:

- Customer churn
- Fraud exposure
- High-value customer attrition

This platform enables:

✔ Churn rate segmentation  
✔ Revenue exposure analysis  
✔ Fraud risk detection  
✔ Predictive churn probability scoring  
✔ Explainable churn drivers  

---

## Quantitative Scope

| Dataset | Records |
|----------|----------|
| Customers | ~10,000 |
| Transactions | 500,000 |
| Fraud Signals | 500,000 |
| Features | 13 customer attributes |

---

## Predictive Model Performance

Model: Logistic Regression  
Train/Test Split: 80/20  

- Accuracy: **0.815**
- ROC-AUC: **0.734**

Top churn drivers identified:
- Inactive membership
- Credit score
- Balance
- Geography
- Product count

---

## AWS Services Used

- Amazon S3 (Data Lake)
- AWS Athena (Serverless SQL)
- Amazon Bedrock (LLM orchestration)
- IAM (Access control)
- boto3 SDK (Programmatic execution)

---

## LLM Models Evaluated

| Provider | Model | Outcome |
|----------|--------|----------|
| OpenAI | GPT-4o-mini | Rate limit exceeded |
| Anthropic | Claude Haiku | Marketplace payment restriction |
| Amazon Titan | titan-text-lite-v1 | Deprecated |
| Amazon Titan Express | Invalid model version |
| Meta (Bedrock) | LLaMA 3 | Production model |

Demonstrates real-world LLM evaluation under enterprise constraints.

---

## Key Capabilities

- Multi-table SQL generation
- Fraud analysis by geography
- Revenue exposure quantification
- High-value customer risk detection
- Predictive churn modeling
- Explainable AI
- SQL governance & validation

---

## Architecture Diagram

See ARCHITECTURE.md for full cloud architecture.
