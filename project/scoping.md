# Scoping

## Outline:

- [Introduction](introduction.md)
- [Scoping](scoping.md)
- [Data Pipeline](data.md)
- [Modeling](modelling.md)
- [Deployment](deployment.md)
- [AWS Deployment Setup](aws_deployment_setup.md)
- [CI/CD](cicd.md)
- [Monitoring](monitoring.md)

## 1. Overview

MedifyAI is an AI-driven healthcare analytics system for medical symptom analysis and case-based diagnosis. It integrates conversational AI, retrieval-augmented generation (RAG), and cloud-based MLOps to assist healthcare professionals. 

The system is built on the PMC-Patients dataset, which includes 167,034 anonymized patient summaries extracted from PubMed Central. More details on the dataset can be found here: [PMC-Patients Dataset](https://huggingface.co/datasets/zhengyun21/PMC-Patients).

## 2 Problem Statement

Healthcare systems often lack structured patient symptom collection and real-time medical assistance. Doctors rely on incomplete patient histories, leading to diagnostic delays. MedifyAI aims to improve this by enabling structured symptom collection, retrieval-based case comparison, and patient interaction with their medical reports.

## 3 Objectives

1. Improve patient engagement through AI-driven conversation  
2. Provide treatment recommendations using historical medical data  
3. Reduce bias in patient interactions  
4. Monitor retrieval performance and maintain data updates  
5. Deploy a scalable AI solution in a cloud environment  

## 4 Key Features

### 4.1 Medical Chatbot  
- Uses GPT-3.5 for patient symptom collection  
- Detects emergency situations in real time  
- Generates clinical summaries for doctors  

### 4.2 Medical Case Analysis  
- Uses sentence-transformers/all-MiniLM-L6-v2 for embeddings  
- Employs GPT-4 to analyze retrieved cases  
- Tracks system performance with MLflow  

### 4.3 Patient Report Interaction  
- OpenBioLLM (LLaMA 3 - 70B) enables question-answering on reports  
- Explains complex medical findings in simple terms  
- Provides context-aware responses for better patient understanding  

## 5 System Workflow

1. The chatbot collects symptoms and creates a structured summary  
2. The system retrieves similar cases from the PMC-Patients dataset  
3. GPT-4 generates a medical summary based on retrieved cases  
4. [OpenBioLLM: LLaMA 3 - 70B](https://www.saama.com/introducing-openbiollm-llama3-70b-8b-saamas-ai-research-lab-released-the-most-openly-available-medical-domain-llms-to-date/)  allows patients to interact with their reports  
5. Data processing and storage are handled using [Apache Airflow](https://airflow.apache.org/docs/apache-airflow/stable/)  and [Pinecone](https://www.pinecone.io/)  
6. The system is deployed on AWS EKS, with monitoring via CloudWatch  

## 6 Technical Components

| Component | Technology Used |
|-----------|----------------|
| Cloud Provider | AWS (EKS, Lambda, SageMaker) |
| Data Processing | Apache Airflow |
| Embedding Model | sentence-transformers/all-MiniLM-L6-v2 |
| Language Models | GPT-3.5, GPT-4, OpenBioLLM |
| Vector Database | Pinecone |
| Deployment | Docker, Kubernetes |
| CI/CD | GitHub Actions |
| Monitoring | Prometheus, CloudWatch, Grafana |
| Experiment Tracking | MLflow |

## 7 MLOps Pipeline

The MLOps pipeline automates training, deployment, and monitoring. It consists of:  
1. Data ingestion from PMC-Patients dataset  
2. Embedding generation and storage in Pinecone  
3. Retrieval and response generation using GPT-4  
4. Model deployment through [Amazon SageMaker](https://docs.aws.amazon.com/sagemaker/)  
5. CI/CD automation via GitHub Actions  
6. System monitoring through Prometheus and CloudWatch  

## 8 Challenges and Considerations

1. Addressing bias in chatbot responses across demographics  
2. Improving retrieval accuracy to ensure relevant case recommendations  
3. Managing cloud resource costs and optimizing infrastructure  
4. Ensuring patient data security and regulatory compliance  

## 9 Expected Impact

PatientInsight aims to enhance healthcare decision-making by providing structured patient data, assisting doctors with case-based recommendations, and allowing patients to engage with their medical reports. The system is designed to be scalable, efficient, and accessible.  

