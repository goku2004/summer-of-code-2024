# Inventory Prediction and Sales Forecasting

## Installation
1. Clone this repository.
2. Install the dependencies:
   ```bash
   pip install -r requirements.txt

## Dataset

This project uses data governed by the GNU General Public License v2.0 (GPL-2.0). 

- **Dataset Source**: [Online Retail Dataset](https://www.gnu.org/licenses/old-licenses/gpl-2.0.en.html#SEC1)
- **License**: GNU General Public License v2.0 (GPL-2.0)

### License Terms
The dataset is licensed under the GPL-2.0 license. Users must adhere to the following terms when using the dataset:
- Redistributions of the dataset must include a copy of the GPL-2.0 license.
- The dataset must not be used in proprietary software.
- Any modifications to the dataset must be clearly stated.

For full details of the license, refer to the [GPL-2.0 License](https://www.gnu.org/licenses/old-licenses/gpl-2.0.en.html).


## Table of Contents

1. [Introduction](#introduction)
2. [Why Time Series Forecasting for Inventory and Sales?](#why-time-series-forecasting-for-inventory-and-sales)
3. [Workflow Overview](#workflow-overview)
4. [Detailed Task Breakdown](#detailed-task-breakdown)
    - [4.1. Load and Explore the Dataset](#42-load-and-explore-the-dataset)
    - [4.2. Data Preprocessing](#43-data-preprocessing)
    - [4.3. Feature Engineering](#44-feature-engineering)
    - [4.4. Apply Machine Learning Approaches](#46-apply-machine-learning-approaches)
    - [4.5. Model Evaluation and Cross-Validation](#47-model-evaluation-and-cross-validation)
5. [Results](#results)

## 1. Introduction
I implemented three models for time-series forecasting which is a crucial concept used in stock market as well as many dynamic data retrieval systems and to predict statistics using classical ML based approaches.

## 2. Why Time Series Forecasting for Inventory and Sales?

Effective inventory management and accurate sales forecasting are critical for any business. Traditional methods may fail to capture complex patterns and trends in the data. ML methods can find patterns in large streams of data.

Time series forecasting models, especially when combined with machine learning approaches, can adapt to changes and provide more precise predictions, leading to better decision-making and cost savings.

## 3. Workflow Overview

1. Load and explore a suitable dataset.
2. Preprocess data and engineer features.
3. Apply machine learning approaches (Prophet, LSTM).
4. Evaluate models using cross-validation.

## 4. Detailed Task Breakdown

### 4.1. Load and Explore the Dataset
I used the following dataset for applying my ML model on:
- [Superstores Dataset](https://www.kaggle.com/datasets/rohitsahoo/sales-forecasting)

### 4.2. Data Preprocessing
- Handle missing values using imputation methods.
- Encode categorical variables, and normalize numerical features.
- Use `pandas` for data cleaning and transformation. 

### 4.3. Feature Engineering

- Create new features based on date-time information (e.g., day of the week, month, etc.).
- Make a new feature called 'trend' to identify growing or decreasing amount of sales which would normally be ignored by an XGBoost model.

### 4.4. Apply Machine Learning Approaches

- Try using Prophet for automatic forecasting.
- Implement LSTM networks using Keras for sequence prediction.
- Implement a linear regression model for trend capturing and XGBoost model for stationary prediction.
- Apply ADFuller Statistical tests to check the number of lags appropriate to characterise the sales in the given dataset.

### 4.5. Model Evaluation and Cross-Validation

- Use Scikit-learn's TimeSeriesSplit for cross-validation.
- Evaluate models using metrics like MAE, RMSE, and MAPE.
## 5. Results

- We managed to predict the sales of 15 days into the future with a mean squared error of 0.375 using a hybrid model of linear regression to capture trend and XGBoost to capture stationarity. 
- For this dataset it was not suitable to use LSTM model which failed to find any meaningful pattern due to high dimensionality of the model and small dataset size.
- The FBProphet model gave an unusually large error which I believe was due to its inability to capture pattern in missing values.
