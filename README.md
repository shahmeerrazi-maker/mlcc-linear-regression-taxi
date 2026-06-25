# mlcc-linear-regression-taxi
Linear Regression model for predicting Chicago taxi fares using TensorFlow, Keras, and the Google Machine Learning Crash Course (MLCC) dataset.
# MLCC Linear Regression Taxi

A machine learning project built as part of Google's Machine Learning Crash Course (MLCC). This project uses Linear Regression to predict taxi fares from the Chicago Taxi Trips dataset using TensorFlow and Keras.

## Overview

The goal of this project is to build and evaluate a regression model that predicts the fare of a taxi ride based on trip characteristics such as:

* Trip distance (miles)
* Trip duration (minutes)

The project includes:

* Data loading and preprocessing with Pandas
* Exploratory Data Analysis (EDA)
* Correlation analysis
* Data visualization
* Linear Regression model training
* Hyperparameter tuning
* Model evaluation using RMSE
* Fare prediction on sample rides

## Dataset

The dataset is derived from the Chicago Taxi Trips dataset and contains taxi ride information collected during a two-day period in May 2022.

Features used:

| Feature      | Description                      |
| ------------ | -------------------------------- |
| TRIP_MILES   | Distance traveled in miles       |
| TRIP_SECONDS | Trip duration in seconds         |
| TRIP_MINUTES | Derived trip duration in minutes |
| COMPANY      | Taxi company                     |
| PAYMENT_TYPE | Payment method                   |
| TIP_RATE     | Tip percentage                   |
| FARE         | Taxi fare (Target Variable)      |

Dataset Source:

https://download.mlcc.google.com/mledu-datasets/chicago_taxi_train.csv

## Technologies Used

* Python
* TensorFlow 2.18
* Keras 3.8
* Pandas
* NumPy
* Plotly
* Matplotlib
* Google ML Education Utilities

## Installation

Clone the repository:

```bash
git clone https://github.com/yourusername/mlcc-linear-regression-taxi.git
cd mlcc-linear-regression-taxi
```

Install dependencies:

```bash
pip install google-ml-edu==0.1.3 \
keras~=3.8.0 \
matplotlib~=3.10.0 \
numpy~=2.0.0 \
pandas~=2.2.0 \
tensorflow~=2.18.0
```

## Project Workflow

### 1. Data Exploration

* Load dataset into Pandas DataFrame
* Generate descriptive statistics
* Check for missing values
* Analyze feature distributions

### 2. Correlation Analysis

Correlation matrix used to identify features most strongly related to fare prediction.

Key findings:

* TRIP_MILES showed the strongest correlation with FARE.
* TRIP_SECONDS also showed strong correlation.
* TIP_RATE showed weak correlation.

### 3. Model Training

#### Experiment 1

Single Feature:

```text
TRIP_MILES
```

Hyperparameters:

```python
learning_rate = 0.001
epochs = 20
batch_size = 50
```

#### Experiment 2

Hyperparameter tuning:

* Increased learning rate
* Decreased learning rate
* Increased batch size

Observed how convergence changed under different settings.

#### Experiment 3

Two Features:

```text
TRIP_MILES
TRIP_MINUTES
```

Result:

Using both distance and trip duration improved prediction accuracy compared to a single-feature model.

## Evaluation Metrics

The model was evaluated using:

* Mean Squared Error (MSE)
* Root Mean Squared Error (RMSE)

RMSE provides an estimate of the average prediction error in dollars.

## Ground Truth Formula

Chicago taxi fares approximately follow:

FARE = 2.25 × TRIP_MILES + 0.12 × TRIP_MINUTES + 3.25

The trained model learned weights close to this formula.

## Sample Prediction

| Predicted Fare | Actual Fare |
| -------------- | ----------- |
| $25.28         | $25.25      |
| $53.84         | $52.75      |
| $44.77         | $45.00      |

Most predictions were within a few dollars of the observed fare.

## Key Learnings

* Linear Regression fundamentals
* Gradient Descent optimization
* Feature engineering
* Hyperparameter tuning
* RMSE interpretation
* Data visualization techniques
* TensorFlow/Keras model development

## Future Improvements

* Train on larger datasets
* Add train/validation/test split
* Feature scaling and normalization
* Use additional trip features
* Compare against more advanced regression models

## License

This project is for educational purposes and is based on exercises from Google's Machine Learning Crash Course (MLCC).
