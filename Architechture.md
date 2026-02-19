# Enterprise Architecture Overview

Layer 1: Data Lake
- Raw CSV stored in Amazon S3

Layer 2: Serverless Data Warehouse
- AWS Athena external tables

Layer 3: AI Orchestration
- Amazon Bedrock (Meta LLaMA 3)
- Multi-model experimentation (OpenAI, Anthropic, Titan)

Layer 4: SQL Governance
- SQL sanitization
- Query validation
- Unsafe command blocking

Layer 5: Predictive Intelligence
- Logistic Regression model
- Probability scoring
- Explainable AI

Layer 6: Business Intelligence Integration
- Athena integration with Power BI
- Dashboard-ready outputs
