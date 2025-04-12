# Predicting Customer Behavior and Revenue

## Overview
This project aims to **predict customer behavior and revenue** for an e-commerce business using **customer transactional data**. The goal is to derive actionable insights that can optimize **business strategies**, **marketing campaigns**, and **resource allocation**.

The analysis includes:
- **Exploratory Data Analysis (EDA)**: Understanding sales trends, distribution, and regions of interest.
- **Classification Models**: Predicting **customer purchase likelihood**.
- **SMOTE**: Balancing **imbalanced datasets** for better model performance.
- **Regression Models**: Predicting **revenue**.
- **Churn Prediction**: Identifying customers at risk of **churning**.
- **Association Mining**: Finding frequently co-purchased items to improve **cross-selling strategies**.

## Table of Contents
1. [Introduction](#introduction)
2. [Dataset](#dataset)
3. [Objectives](#objectives)
4. [Exploratory Data Analysis](#exploratory-data-analysis)
5. [Classification Models](#classification-models)
6. [SMOTE for Balancing](#smote-for-balancing)
7. [Regression Models for Revenue Prediction](#regression-models-for-revenue-prediction)
8. [Churn Prediction](#churn-prediction)
9. [Association Mining](#association-mining)

## Introduction
Understanding and predicting **customer behavior** is essential for **e-commerce businesses** to stay competitive. By predicting **customer purchase patterns** and **revenue potential**, businesses can optimize **inventory**, plan **marketing efforts**, and enhance the **customer experience**. This project explores **customer data** to provide insights into business growth strategies.

## Dataset
The dataset used contains **transactional data** for an e-commerce store. Each row represents an individual item purchased, with attributes including:
- **InvoiceNo**: Unique transaction identifier
- **StockCode**: Unique product code
- **Description**: Product description
- **Quantity**: Number of units purchased
- **InvoiceDate**: Transaction timestamp
- **UnitPrice**: Price per unit
- **CustomerID**: Unique customer identifier
- **Country**: Customer’s country

## Objectives
The main objectives of this project are:
1. Perform **Exploratory Data Analysis (EDA)** to identify trends and patterns.
2. Classify customers into **likely purchasers** or **non-purchasers** using classification models.
3. Predict **revenue** using **regression models**.
4. Identify at-risk customers for **churn prediction**.
5. Use **association mining** to find frequent product associations for marketing strategies.

## Exploratory Data Analysis
Key findings from the EDA include:
- **Revenue Trends**: Peaks observed in **January 2010** and **mid-2011**, suggesting **seasonal trends**.
- **Geographical Insights**: The **UK** dominates in transactions and revenue, while other regions have lower activity, indicating areas for **expansion**.
- **Product Insights**: A significant portion of sales is from a few products, with over **3900 unique products**.

## Classification Models
We used two classification models to predict whether a customer will make a purchase:
1. **Logistic Regression**: A **binary classification model**.
2. **Random Forest Classifier**: A more robust model combining **multiple decision trees**.

Initial results showed high **class imbalance**, prompting the use of **SMOTE** for balancing.

## SMOTE for Balancing
**SMOTE (Synthetic Minority Oversampling Technique)** was used to balance the dataset:
- **Before Balancing**: 3904 **Purchasers** vs. 8 **Non-Purchasers**
- **After Balancing**: Equal distribution of **Purchasers** and **Non-Purchasers** (2732 samples in both training and testing sets).

Balanced classification results show:
- **Logistic Regression**: **Accuracy** of 98.42%
- **Random Forest**: **Accuracy** of 99.91%, with perfect **precision** and **recall**.

## Regression Models for Revenue Prediction
To predict customer **revenue**, we used the following **regression models**:
- **Linear Regression**: Simpler but less accurate.
- **Decision Tree Regression**: Captures **non-linear relationships**.

**Results**:
- High **Mean Squared Error (MSE)** initially, but performance improved significantly after applying **log transformation** to the target variable.

**Best Model**: **Gradient Boosting Regressor** with **MSE = 0.1793** and **R² = 0.8926**.

## Churn Prediction
**Churn prediction** identifies customers who are likely to stop purchasing based on their **recency** of transactions:
- **Features**: **Total amount spent**, **total items purchased**, **recency**, and **frequency** of purchases.
- **Models Used**: **Logistic Regression** and **Random Forest**.

**Results**:
- **Logistic Regression**: 99.75% **accuracy**.
- **Random Forest**: 100% **accuracy**, outperforming Logistic Regression in identifying churned customers.

## Association Mining
Using the **FP-Growth algorithm**, we identified frequently purchased **item pairs**. **Association rules** provide valuable insights for **product placement** and **cross-selling strategies**. For example:
- Customers who purchased "**Green Regency Teacup and Saucer**" are likely to buy "**Roses Regency Teacup and Saucer**."

## How to Use
1. Clone this repository.
2. Install dependencies:
   ```bash
   pip install -r requirements.txt




