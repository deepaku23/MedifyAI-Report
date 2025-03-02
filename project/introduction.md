# MedifyAI: Advanced Medical Analysis System

## Team Information

| Name | Email |
|------|-------|
| Deepak Udayakumar | [udayakumar.de@northeastern.edu](mailto:udayakumar.de@northeastern.edu) |
| Amitesh Tripathi | [tripathi.am@northeastern.edu](mailto:tripathi.am@northeastern.edu) |
| Dinesh Sai Pappuru | [pappuru.d@northeastern.edu](mailto:pappuru.d@northeastern.edu) |
| Rohit Kumar Gaddam | [gaddamsreeramulu.r@northeastern.edu](mailto:gaddamsreeramulu.r@northeastern.edu) |
| Sneha Amin | [amin.sn@northeastern.edu](mailto:amin.sn@northeastern.edu) |

---

## Table of Contents

- [Introduction](introduction.md)
- [Scoping](scoping.md)
- [Data Pipeline](data_pipeline.md)
- [Modeling](modelling.md)
- [Deployment](deployment.md)
- [CI/CD](cicd.md)
- [Monitoring](monitoring.md)

---

## Demo Video

[Watch the demo](https://northeastern-my.sharepoint.com/personal/tripathi_am_northeastern_edu/_layouts/15/stream.aspx?id=%2Fpersonal%2Ftripathi%5Fam%5Fnortheastern%5Fedu%2FDocuments%2FMicrosoft%20Teams%20Chat%20Files%2FMedify%5FMLOps%5FGroup10%2Emp4&ga=1&referrer=StreamWebApp%2EWeb&referrerScenario=AddressBarCopied%2Eview%2E97e30119%2D08a2%2D49ae%2Db898%2D168f58a3b907)

---

## Introduction

### 1. Problem Statement and Overview

PatientInsight is a healthcare analytics system that enhances medical symptom analysis and patient care through AI-powered tools. The system integrates medical chatbots, retrieval-augmented generation (RAG) models, and automated data pipelines to provide accurate medical insights and treatment recommendations. 

It uses the **PMC-Patients dataset** ([link](https://huggingface.co/datasets/zhengyun21/PMC-Patients)), which contains 167,034 anonymized patient summaries from PubMed Central (PMC).

---

## 2. Methodology

### AI Model Architecture

The system is structured into three primary phases:

#### 2.1. **Medical Chatbot (HealthcarechatLLM)**
- **Model Used:** GPT-3.5
- **Purpose:** Dynamic symptom collection and clinical summaries.
- **Capabilities:**
  - Structured symptom gathering.
  - Real-time emergency detection.
  - Clinical summary generation.
  - Bias detection for fair patient interactions.

#### 2.2. **Medical Analysis (RAG System)**
- **Embedding Model:** `sentence-transformers/all-MiniLM-L6-v2`
- **Generation Model:** GPT-4
- **Purpose:***Retrieval-based medical analysis.
- **Capabilities:**
  - Retrieval-Augmented Generation (RAG) for case-based diagnosis.
  - Historical medical case-based recommendations.
  - Comprehensive tracking via MLflow.

#### 2.3. **Patient Report Interaction (OpenBioLLM)**
- **Model Used:** `OpenBioLLM (LLaMA 3 - 70B)` ([More Info](https://www.saama.com/introducing-openbiollm-llama3-70b-8b-saamas-ai-research-lab-released-the-most-openly-available-medical-domain-llms-to-date/))
- **Purpose:** Patients can **interact with doctor reports**.
- **Capabilities:**
  - Provides clarifications** and explanations about medical findings.
  - Ensures accurate, context-aware responses.

---

## 3. Goals

1. **Enhance Patient Interaction** – AI-powered symptom collection chatbot.
2. **Improve Diagnosis** – Retrieval-based medical case insights.
3. **Enable Patient Empowerment** – AI-assisted medical report explanations.
4. **Ensure Bias-Free AI** – Robust bias detection and fairness checks.
5. **Seamless MLOps Deployment** – Cloud-based automation & monitoring.

---

The source code for our project can be found here:  [GitHub](https://github.com/deepaku23/MedifyAI).

## Tools Used for MLOps

| Category | Tools Used |
|----------|------------|
| **Cloud Provider** | AWS (EKS, S3, Lambda, SageMaker) |
| **Model Training & Tracking** | MLflow |
| **Data Pipeline** | Apache Airflow |
| **Containerization & Orchestration** | Docker, Kubernetes (EKS) |
| **CI/CD** | GitHub Actions |
| **Monitoring & Logging** | Prometheus, CloudWatch, Grafana |
| **Vector Database** | Pinecone |

---

## Project Architecture

![Architecture](images/28.png)

---
