# Deployment Replication Guide

## Outline:

- [Introduction](introduction.md)
- [Scoping](scoping.md)
- [Data Pipeline](data.md)
- [Modeling](modelling.md)
- [Deployment](deployment.md)
- [AWS Deployment Setup](aws_deployment_setup.md)
- [CI/CD](cicd.md)
- [Monitoring](monitoring.md)


### 1.1 Prerequisites Setup

To replicate the deployment, ensure the following prerequisites are met:

1. **AWS Account and CLI Configuration**: Install and configure the AWS CLI to interact with AWS services.
   ```bash
   curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
   unzip awscliv2.zip
   sudo ./aws/install
   aws configure
   ```

2. **Required Tools Installation**: Install Docker, kubectl, and eksctl for container management and Kubernetes operations.
   ```bash
   sudo apt-get update
   sudo apt-get install docker.io
   sudo usermod -aG docker $USER
   curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
   sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
   curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp
   sudo mv /tmp/eksctl /usr/local/bin
   ```

### 1.2 Infrastructure Setup

1. **Create EKS Cluster**: Set up a Kubernetes cluster using eksctl, which manages the orchestration of containerized applications.
   ```bash
   eksctl create cluster \
       --name patient-insight-eks-cluster \
       --region us-east-2 \
       --node-type c4.xlarge \
       --nodes-min 2 \
       --nodes-max 4 \
       --with-oidc \
       --ssh-access \
       --ssh-public-key your-key-name \
       --managed
   ```

2. **Create ECR Repositories**: Establish repositories for frontend and backend components to manage Docker images.
   ```bash
   aws ecr create-repository --repository-name frontend
   aws ecr create-repository --repository-name backend
   ```

### 1.3 Application Deployment

1. **Clone Repository**: Download the project repository and navigate to the project directory.
   ```bash
   git clone https://github.com/your-repo/PatientInsight.git
   cd PatientInsight
   ```

2. **Environment Configuration**: Set up environment variables in a `.env` file to configure the deployment environment.
   ```env
   AWS_REGION=us-east-2
   OPENAI_API_KEY=your_openai_key
   PINECONE_API_KEY=your_pinecone_key
   AWS_ACCESS_KEY_ID=your_aws_key
   AWS_SECRET_ACCESS_KEY=your_aws_secret
   ```

3. **Automated Deployment**: Execute the deployment script to automate the setup process.
   ```bash
   chmod +x deploy.sh
   ./deploy.sh
   ```

### 1.4 Validation and Troubleshooting

- **Validation**: The deployment script outputs the status of pods and nodes, along with frontend and backend URLs for application access.
- **Troubleshooting**: Common issues include pod startup problems, service connection issues, and image pull errors. Use `kubectl` commands to diagnose and resolve these issues.

### 1.5 Cleanup Instructions
To clean up resources, delete services, deployments, and the EKS cluster.
```bash
kubectl delete service frontend-service backend-service
kubectl delete deployment frontend backend
eksctl delete cluster --name patient-insight-eks-cluster --region us-east-2
```

### 1.6 Security Considerations
- Regularly rotate AWS access keys.
- Use AWS Secrets Manager for sensitive information.
- Implement network policies in EKS.
- Monitor CloudWatch logs for security events.

More details on to the deployment can be found [here](https://github.com/deepaku23/MedifyAI/blob/main/docs/README.md)