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

This repository is a public presentation of academic project. The analysis is for educational and portfolio purposes only and is not investment or credit advice.


# 上市公司股权质押违约预测

基于财务与经营指标预测上市公司股权质押违约风险的机器学习小组项目。

## 项目概述

本项目面向创投机构贷前风控场景，将违约识别定义为二分类问题。基于 1,442 家上市公司的数据，对比基准模型、神经网络、正则化模型及集成学习模型的预测效果。

## 分析方法

- 剔除可能包含事后风险信息的变量，降低目标泄露风险。
- 清洗并标准化财务指标，通过 VIF 检验评估多重共线性，删除冗余特征。
- 采用分层抽样划分训练集与测试集，并使用 SMOTE 缓解违约类别样本不平衡问题。
- 对比逻辑回归、决策树、人工神经网络、ElasticNet 逻辑回归、随机森林和 AdaBoost 等模型，使用准确率、精确率、召回率、F1 值和 ROC-AUC 进行评估。
- 在交叉验证和阈值设定中优先优化违约召回率，尽可能减少高风险企业的漏判。

## 模型结果

| 模型 | 测试集准确率 | 违约召回率 | F1 值 | ROC-AUC |
| --- | ---: | ---: | ---: | ---: |
| 优化决策树 | 96.9% | 86.8% | 0.911 | 0.964 |
| AdaBoost | 97.2% | 88.7% | 0.922 | 0.996 |

## 风控应用

基于模型输出的违约概率设计分层筛查机制：高风险企业进入审慎处理或限制名单，处于临界区间的企业进入人工复核流程，从而平衡违约漏判风险与审核成本。

## 仓库内容

- `notebooks/stock_pledge_default_prediction.ipynb`：可复现的项目分析 Notebook。
- `requirements.txt`：项目所需的 Python 依赖。

## 数据来源

原始数据来自 [Kaggle：Stock Pledge Defaults Prediction](https://www.kaggle.com/datasets/jiaoyouzhang/stock-pledge-defaults-prediction)。

下载数据后，请将 `train.csv` 放置在 Notebook 的同一工作目录下再运行。

## 说明

本仓库为学术项目的公开展示版本，仅用于学习和作品集展示，不构成投资或信贷建议。

