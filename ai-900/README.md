[Introduction to AI in Azure](https://learn.microsoft.com/en-us/training/paths/introduction-to-ai-on-azure/)  
[Micrpspft Foundry Documentation](https://learn.microsoft.com/en-us/azure/ai-foundry/?view=foundry-classic)  

# Fundamental principles of machine learning on Azure
Maching Learning: creat a model to predict unknown values  
Features: the inputs to a machine‑learning model  
Labels: the output the model is trying to predict  
Dataset:
  * Training dataset:
  * Validation dataset: to tune the model's hyperparameters and prevent overfitting  
  * Test dataset: to provide a final, unbiased measure of the model's performance after all
    training is complete.
     
**Hyperparameter**: a setting  - **inference parameter**  
- set by you, not learned from data
- external to the model, controlling its behavior
- tuned to improve performance
- In contrast, **parameters** are learned automatically during training and are internal variables.  
Lineage: end-to-end tracking of data, code, and processes through a model's lifecycle

Azure Automated ML: build and deploy ML models  
* Classification (e.g., fraud detection, churn prediction): predict a category or class 
* Regression (e.g., price prediction): predict numerical value
* Clustering: group items based on features. No label. Unsupervised training
* Time‑series forecasting (e.g., demand forecasting)
* Computer vision (object detection, image classification)
* Natural language processing (text classification, sentiment analysis)
* 
Azure ML Designer: build machine learning pipelines visually  
Azure Automated Machine Learning (AutoML): to simplfy and accelerate the process of finding a high-quality model

Deep Learning: udentify patterns in the unstructured data  

Data preparation:  
  Cleaning, normalizing, splitting (split data into training and validation sets)  

R-squared  
* Scale: Ranges from 0 to 1
* R^2=1: Perfect Fit
* R^2=0: No Fit

Multiclass classification: assigns an input to one of three or more distinct, mutually exclusive classes  
Binary classification (two classes)  
Multi-label classification (multiple labels per input)  

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

## Transformer architecture
Replacing sequential models like RNNs and LSTMs with a highly parallel, attention‑based system.  
Hugging Face: NLP transformers library  

1. Self‑Attention (the core innovation)  
Each token (word, subword, or character) “attends” to every other token to understand context.   
This allows the model to capture long‑range relationships efficiently.  

2. Parallel Processing  
Unlike RNNs, Transformers process all tokens **simultaneously**.

3. Positional Encoding  
Because Transformers don’t process text sequentially, they add **positional encodings** to
represent word order.  

The original Transformer uses an **Encoder-Decoder** structure, though modern variations often use just one or the other.

### **The Encoder (The "Reader")**

The encoder’s job is to understand the input. It breaks the text down into "embeddings" (mathematical vectors) and 
processes them through multiple layers to capture deep meaning.

* **Input Embedding:** Converts words into numbers.
* **Positional Encoding:** Adds a "time stamp" to each word so the model knows where it sits in the sentence (since
  it processes everything at once).
* **Multi-Head Attention:** Several attention mechanisms running at once to catch different types of relationships
  (e.g., one head for grammar, another for meaning).

### **The Decoder (The "Writer")**

The decoder takes the encoder's "understanding" and generates an output (like a translation or a response).

* **Masked Self-Attention:** Ensures that when the model is predicting the next word, it can't "cheat" by looking at
  the words that come after it in the training data.
* **Encoder-Decoder Attention:** Connects the decoder back to the encoder’s findings to ensure the output stays
  relevant to the original input.

### Why Transformer architecture Changed AI
The Transformer architecture is the foundation for almost all current state-of-the-art AI:

* **GPT (Generative Pre-trained Transformer):** Uses only the **Decoder** part of the architecture to predict
  the next word in a sequence.
* **BERT:** Uses only the **Encoder** to understand the nuances of language for search engines.
* **Vision Transformers (ViT):** Applies the same logic to images by breaking them into small patches (like
  words in a sentence), proving that Transformers aren't just for text.

## Theory behind the Transformer architecture - Scaled Dot-Product Attention mechanism
It uses three distinct vectors for every single word (token) in a sentence: **Query ()**, **Key ()**, and **Value ()**.

A helpful analogy is a **filing cabinet** or a **search engine**:

* **Query ():** What you are looking for (the current word asking "Who is relevant to me?").
* **Key ():** The label on the folder (every word saying "Here is what I contain").
* **Value ():** The actual information inside the folder.

### 1. The Mathematical Steps

The model calculates the relationship between words using the following formula:

#### Step A: The Score (Dot Product)

The model takes the **Query** of one word and multiplies it by the **Key** of every other word (including itself).

* If the Query and Key are similar, the resulting number is high.
* If they are unrelated, the number is low.

#### Step B: Scaling and Softmax

1. **Scaling:** The score is divided by  (where  is the dimension of the keys). This prevents the numbers from
   getting too large, which helps with stable training.
3. **Softmax:** This turns the scores into **probabilities** (weights) that add up to  (or 100%). A word might
   give 80% of its attention to itself and 20% to a related noun.

#### Step C: The Weighted Sum

Finally, the model multiplies these weights by the **Value ()** vectors. The output is a new representation of 
the word that is "enriched" by the information from all the other relevant words in the sentence.


### 2. Multi-Head Attention

Instead of doing this once, the Transformer does it many times simultaneously. This is called **Multi-Head Attention**.

Think of it like a committee of experts looking at the same sentence:

* **Head 1** might focus on grammar (subject-verb agreement).
* **Head 2** might focus on vocabulary (which definition of "bank" is being used?).
* **Head 3** might focus on pronouns (who does "it" refer to?).

The results of all these "heads" are concatenated together and passed to the next layer of the network.

## Deep learning
Artificial neural networks with multiple "deep" layers to extract patterns.  

Ttraditional **machine learning** often requires humans to identify and label features (like "wheels" or "eyes") manually  
Deep learning techniques learn these features directly from the raw data.  

### 1. Key Architectural Features

* **Multi-Layered (Deep) Structure:** Models consist of an input layer, an output layer, and many **hidden layers**  
  in between. Each layer acts as a filter that transforms raw data into a more abstract representation (e.g., from
  pixels to edges, then to shapes, and finally to objects).
* **Non-Linearity:** By using **activation functions** (like ReLU or Sigmoid), deep learning can model complex,
  non-linear relationships that simple linear models cannot.
* **Massive Parameter Count:** Deep learning models often have millions of "weights" and "biases" that are fine-tuned
  during training to improve accuracy.


### 2. Core Operational Capabilities

* **Automated Feature Engineering:** This is the most significant advantage. Deep learning automatically discovers  
  which features are important for a task (e.g., identifying a cat's ears in a photo) without human intervention.
* **Scalability with Data:** While traditional algorithms often hit a performance plateau as data increases, deep  
  learning models generally continue to improve their accuracy the more data they are given.
* **End-to-End Learning:** These techniques can take raw input (like a sound wave) and produce the final output  
  (like a text transcript) in one single process, rather than breaking it into multiple independent steps.


### 3. Specialized Techniques & Architectures

| Technique | Best Used For | Key Feature |
| :----------------------- | :------------------- | :--- |
| **CNNs** (Convolutional) | Images / Video       | Detects spatial patterns and hierarchies. |
| **RNNs** (Recurrent)     | Speech / Time-series | Has "memory" to process sequences of data. |
| **Transformers**         | Text / Translation   | Uses "attention" to understand the context of words. |
| **GANs** (Generative)    | Creating new content | Uses two networks (Generator vs. Discriminator) to compete. |
