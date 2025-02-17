# PatientInsight: Advanced Medical Analysis System

![Architecture](images/28.png)

### Video Link: https://northeastern-my.sharepoint.com/personal/tripathi_am_northeastern_edu/_layouts/15/stream.aspx?id=%2Fpersonal%2Ftripathi%5Fam%5Fnortheastern%5Fedu%2FDocuments%2FMicrosoft%20Teams%20Chat%20Files%2FMedify%5FMLOps%5FGroup10%2Emp4&ga=1&referrer=StreamWebApp%2EWeb&referrerScenario=AddressBarCopied%2Eview%2E97e30119%2D08a2%2D49ae%2Db898%2D168f58a3b907

## Project Overview
PatientInsight is a comprehensive healthcare analytics platform that combines advanced AI capabilities with robust data processing to revolutionize medical symptom analysis and patient care. The system leverages state-of-the-art language models, sophisticated data pipelines, and cloud infrastructure to provide accurate medical insights and treatment recommendations.

## Key Components

### 1. Data Pipeline
- Processes the PMC-Patients dataset containing 167,034 anonymized medical records
- Implements automated data processing through Apache Airflow DAGs
- Features comprehensive data preprocessing and statistical analysis
- Maintains data quality through automated testing and validation

### 2. AI Model Architecture
The system operates through two main phases:

#### Medical Chatbot (HealthcarechatLLM)
- Conducts structured symptom collection conversations
- Implements real-time emergency detection
- Generates clinical summaries
- Ensures unbiased patient interaction through comprehensive bias detection

#### Medical Analysis (RAG System)
- Utilizes Retrieval-Augmented Generation for case analysis
- Leverages historical medical cases for informed insights
- Provides treatment recommendations based on similar cases
- Implements comprehensive experiment tracking through MLflow

### 3. Cloud Deployment
- Deployed on AWS using a cloud-native architecture
- Utilizes EKS for container orchestration
- Implements serverless computing through AWS Lambda
- Features comprehensive monitoring through CloudWatch and Prometheus

### 4. CI/CD Pipeline
- Automated testing and deployment through GitHub Actions
- Continuous integration process for ML and data components
- Automated container building and deployment
- Comprehensive notification system for deployment status

### 5. Monitoring and Maintenance
- Implements sophisticated data drift detection
- Monitors retrieval performance for RAG system
- Features automated alerts for system issues
- Maintains comprehensive logging through CloudWatch

## Technical Stack
- **Cloud Provider**: Amazon Web Services (AWS)
- **Container Orchestration**: Kubernetes (EKS)
- **CI/CD**: GitHub Actions
- **Monitoring**: CloudWatch, Prometheus, Grafana
- **ML Experiment Tracking**: MLflow
- **Data Processing**: Apache Airflow
- **Vector Database**: Pinecone
- **Model Deployment**: Amazon SageMaker

## Impact
PatientInsight represents a significant advancement in medical analytics, providing:
- Improved patient care through accurate symptom analysis
- Enhanced decision support for healthcare providers
- Scalable and reliable medical insights
- Continuous system improvement through automated data processing
- Comprehensive monitoring and maintenance capabilities

This system demonstrates the potential of combining advanced AI capabilities with robust cloud infrastructure to create a reliable and scalable healthcare analytics solution.
