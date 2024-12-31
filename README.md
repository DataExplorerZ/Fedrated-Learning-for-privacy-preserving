# Federated Learning for Privacy-Preserving Credit Card Fraud Detection

This repository contains the implementation of a **federated learning framework** applied to **credit card fraud detection**. Federated learning allows multiple clients to collaboratively train a global model without sharing their local datasets, ensuring data privacy while maintaining high model performance.

---

## Project Overview

Federated learning is a decentralized approach to machine learning that enables collaborative model training while preserving data privacy. This project focuses on applying federated learning to detect credit card fraud using a distributed dataset.

**Key Highlights**:
- **Clients**: 
  - Client 1 trains using **Random Forest**.
  - Client 2 trains using **Artificial Neural Networks (ANN)**.
  - Client 3 trains using **Multi-Layer Perceptrons (MLP)**.
- **Data Privacy**: Each client's dataset remains local, and only gradients are aggregated to update the global model.
- **Performance Metrics**: F1 score, precision, recall, accuracy, loss, and AUC are used to evaluate the models.

**Global Model Approach**:
- Aggregates gradients from client models iteratively.
- Distributes updated weights back to clients for further training.

---

## Files in the Repository

- **`federated_learning.ipynb`**:  
  Jupyter Notebook containing:
  - Data preprocessing and EDA.
  - Implementation of client models (Random Forest, ANN, MLP).
  - Federated learning framework with gradient aggregation and global model updates.
  - Model evaluation metrics.

- **`federated_learning_report.pdf`**:  
  A detailed report covering:
  - Methodology, results, and privacy analysis.
  - Discussion of federated learning's advantages in sensitive data domains.

---

## Dataset

The dataset consists of **284,807 credit card transactions**, including:
- Anonymized features (`V1` through `V28` from PCA transformations).
- Transaction amounts.
- Target variable (`Class`): 0 for legitimate transactions, 1 for fraudulent transactions.

**Dataset Details**:
- Highly imbalanced: Fraudulent transactions are less than 1% of total data.
- Source: [Kaggle Credit Card Fraud Detection](https://www.kaggle.com/mlg-ulb/creditcardfraud).

---

## Results

| **Metric**      | **Client 1 (RF)** | **Client 2 (ANN)** | **Client 3 (MLP)** | **Global Model** |
|------------------|-------------------|--------------------|--------------------|------------------|
| **F1 Score**     | 0.9986           | 0.9974            | 0.9977            | 0.9980           |
| **Precision**    | 0.9986           | 0.9982            | 0.9983            | 0.9984           |
| **Recall**       | 0.9988           | 0.9982            | 0.9984            | 0.9983           |
| **Accuracy**     | 99.88%           | 99.82%            | 99.84%            | 99.85%           |
| **AUC**          | 0.92             | 0.51              | 0.71              | 0.80             |

**Key Insights**:
- The global model effectively combines insights from all clients, achieving high performance across metrics.
- Federated learning ensures data privacy without compromising detection accuracy.

---
