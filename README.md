# Stock Pledge Default Prediction

Team machine-learning project for predicting listed-company stock-pledge defaults from financial and operational indicators.

## Overview

The project frames default-risk identification as a binary classification task for a venture-capital risk-control setting. It uses data from 1,442 listed companies and compares baseline, neural-network, regularised, and ensemble models.

## Approach

- Removed post-event distress variables to reduce target leakage risk.
- Cleaned and standardised financial variables, assessed multicollinearity with VIF, and removed redundant predictors.
- Used a stratified train/test split and SMOTE to address the minority default class.
- Evaluated Logistic Regression, Decision Tree, ANN, ElasticNet Logistic Regression, Random Forest, and AdaBoost using accuracy, precision, recall, F1, and ROC-AUC.
- Prioritised default recall during cross-validation and threshold selection to reduce missed defaults.

## Results

| Model | Test accuracy | Default recall | F1 | ROC-AUC |
| --- | ---: | ---: | ---: | ---: |
| Optimised Decision Tree | 96.9% | 86.8% | 0.911 | 0.964 |
| AdaBoost | 97.2% | 88.7% | 0.922 | 0.996 |

## Risk-control application

Predicted default probabilities can support tiered screening: companies above a high-risk threshold can be escalated for restrictive action, while borderline cases can be routed to manual review.

## Repository contents

- `notebooks/stock_pledge_default_prediction.ipynb`: reproducible project notebook.
- `requirements.txt`: Python dependencies.

## Data

The raw dataset is come from Kaggle. https://www.kaggle.com/datasets/jiaoyouzhang/stock-pledge-defaults-prediction Obtain the source data from the original Kaggle dataset and place `train.csv` in the same working directory as the notebook before running it.

## Note

This repository is a public presentation of a team academic project. The analysis is for educational and portfolio purposes only and is not investment or credit advice.
