## Fundamental principles of machine learning on Azure
Maching Learning: creat a model to predict unknown values  
Features: the inputs to a machine‑learning model  
Labels: the output the model is trying to predict  
Training data set and validation dataset  
Hyperparameter: a setting  
- set by you, not learned from data
- external to the model, controlling its behavior
- tuned to improve performance
- In contrast, parameters are learned automatically during training.
Lineage: end-to-end tracking of data, code, and processes through a model's lifecycle

Azure Automated ML: build and deploy ML models  
* Classification (e.g., fraud detection, churn prediction): predict a category or class 
* Regression (e.g., price prediction): predict numerical value
* Clustering: group items based on features. No label. Unsupervised training
* Time‑series forecasting (e.g., demand forecasting)
* Computer vision (object detection, image classification)
* Natural language processing (text classification, sentiment analysis)
Azure ML Designer: build machine learning pipelines visually

Deep Learning: udentify patterns in the unstructured data  

Data preparation:  
  Cleaning, normalizing, splitting (split data into training and validation sets)  

### Quick Summary of Clustering Scenarios

| Scenario                          | Description                  |
|-----------------------------------|------------------------------|
| Customer segmentation             | Find natural customer groups   
| Recommendation systems            | Group similar items  
| Anomaly detection                 | Identify outliers (Fraud, Security, Manufacturing)    
| Image segmentation                | Group similar pixels  
| Gene analysis                     | Discover biological patterns  
| Geographic grouping               | Optimize spatial decisions  
| Document clustering               | Organize large text collections  
| Preprocessing for other ML Tasks  | Improve downstream ML models   

## Azure Data Services for Data Science & ML
* Azure Data Lake Storage (ADLS)  
* Azure AutoML: end‑to‑end ML lifecycle platform
* Azure Synapse Analytics
* Azure Data Factory: a cloud ETL/ELT service
* Azure SQL Database / Azure Cosmos DB  

## Azure Compute Services for Machine Learning
* Azure Machine Learning Compute: supporting training, deployment, and governance
  * Serverless Compute
  * Compute Clusters
  * Compute Instances: for experimenting
* Azure Databricks: distributed ML training
* Azure Kubernetes Service (AKS): custom containerized ML workloads
* Azure Functions / Azure Container Apps: Lightweight compute options 

## Model Management & Deployment in Azure Machine Learning
* Model Management: tracking, versioning, registering, and governing ML models
  * Model Registration and Versioning
  * Lineage and Governance
* Model Deployment (Inference)
* Deployment Strategies
  - Blue/Green Deployment
  - Canary Deployment (Gradually route traffic)
  - A/B Testing (split testing / bucket testing) — compares the performance of two versions of content 
* CI/CD & MLOps Integration
  - GitHub Actions
  - Azure DevOps
  - Azure ML Pipelines
* Security & Governance
  - Role-Based Access Control (RBAC)
  - Audit logs
* Monitoring & Maintenance
  * Latency & throughput metrics
  * Error rates
  * Resource usage
  * Data & model drift detection
  * Integrated with
    - Azure Monitor
    - Application Insights




