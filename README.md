#  Ticket Categorizer

## Overview

This project implements a lightweight Natural Language Processing (NLP) solution that automatically classifies incoming support tickets into the appropriate department. The objective is to simulate the ticket triage process used in enterprise helpdesk systems by routing tickets quickly and efficiently.

The classifier predicts one of the following departments:

- BILLING
- TECHNICAL
- HR
- GENERAL



## Features

- Automatic support ticket classification
- TF-IDF text vectorization
- Logistic Regression classifier
- Hyperparameter tuning using GridSearchCV
- Confidence score for each prediction
- Human review recommendation for low-confidence predictions
- Rule-based priority tagging (Urgent/Normal)
- Interactive command-line prediction demo
- Model evaluation using multiple metrics



## Tech Stack

- Python
- Pandas
- Scikit-learn



## Project Workflow

1. Load/Create dataset
2. Text preprocessing
3. Train-test split
4. TF-IDF feature extraction
5. Train Logistic Regression classifier
6. Hyperparameter tuning using GridSearchCV
7. Model evaluation
8. Real-time ticket prediction
9. Confidence score generation
10. Human review threshold
11. Priority tagging



## Model Choice

A Scikit-learn Pipeline was used to combine TF-IDF vectorization and Logistic Regression into a single workflow.

Logistic Regression was selected because it performs well on high-dimensional sparse text data, provides probability estimates for confidence scoring, and is computationally efficient for real-time ticket routing.



## Edge Case Handling

The solution includes several mechanisms to improve reliability:

- Predictions include a confidence score.
- Tickets with confidence below **60%** are flagged for **manual review** instead of being automatically assigned.
- Tickets containing keywords such as **"urgent"**, **"down"**, **"error"**, **"failed"**, or **"not working"** are tagged as **Urgent**.



## Evaluation Metrics

The model is evaluated using:

- Accuracy
- Classification Report
- Confusion Matrix

These metrics help assess the classifier's overall performance across all departments.


## Example Output

Ticket:
API returns 500 error

Department:
TECHNICAL

Confidence:
95.62%

Priority:
Urgent

Status:
Auto Assigned

Top Predictions

TECHNICAL   95.62%
GENERAL      2.83%




## Reflection

Given additional time and a larger dataset, the following improvements could be implemented:

- Train on real-world enterprise support tickets.
- Compare TF-IDF with transformer-based models such as BERT or DistilBERT.
- Incorporate additional ticket metadata (customer information, product type, historical tickets) to improve classification accuracy.
- Deploy the solution as a web application using Streamlit or Flask.
- Continuously retrain the model using new support tickets to adapt to evolving ticket patterns.


## Author

Ben Jigi
