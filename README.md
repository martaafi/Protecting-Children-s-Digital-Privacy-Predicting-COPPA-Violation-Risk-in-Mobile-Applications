# Protecting Children's Digital Privacy: Predicting COPPA Violation Risk in Mobile Applications
## Background
The digital world is increasingly accessible to children, with mobile apps playing a significant role in their entertainment, education, and social interaction. However, this increased access also brings potential risks, particularly regarding the collection and use of children's personal information. The Children's Online Privacy Protection Act (COPPA) in the United States, and similar regulations globally, aim to protect children's privacy online by requiring app developers to obtain parental consent before collecting data from users under 13.

In this competition, the objective is to build a machine learning model capable of predicting whether a mobile application poses a risk of non-compliance with COPPA. By identifying potentially high-risk apps, this project aims to support app stores, developers, and parents in fostering a safer digital environment. The model leverages various application attributes—including app category, download indicators (as a proxy for target audience), privacy policy characteristics, and developer-related information—to estimate the likelihood of COPPA violations.

## Problem Statement
The core objective is a binary classification task:
- Target Variable: coppaRisk (boolean: true or false) 
- Predict whether an app is at risk of violating COPPA, true indicates a higher risk of non-compliance, while false suggests a lower risk.

## Evaluation
Submissions will be evaluated based on a suitable classification metric, likely:
- AUC, or Area Under the ROC Curve, is a single metric that summarizes the overall effectiveness of a classifier. Its value ranges from 0 to 1, where 0.5 suggests the model performs no better than random guessing, and a value of 1 indicates perfect classification performance.

## Results
The best-performing model in this project achieved an AUC score of 0.8254 (82.54%) on the Kaggle leaderboard test dataset.
