Supply Chain ML Lab
Daily Demand Forecasting in Python

This repository contains a lightweight machine learning workflow for forecasting daily product demand. The project uses synthetic but realistic time-series data to mirror typical patterns seen in supply chain environments—trend, weekly seasonality, and random variability.

The goal is to demonstrate a clear, reproducible forecasting pipeline that can scale to real-world data when available.

-Project Summary-

The forecasting workflow includes:

Generating one year of synthetic daily demand

Visualizing demand patterns

Engineering standard time-series features (lags, moving averages, day-of-week)

Building two baseline models:
Naive (lag-1) and 7-day moving average

Training a machine learning model using Random Forest Regression

Evaluating all models on a chronological test split

Producing an iterative 30-day forward forecast

Visualizing performance and forecast horizons

The notebook is self-contained and can be run end-to-end without external data.

This project also includes a Power Bi dashboard where the data was exported from the notebook into 

a CSV file that can be plugged into Power Bi, this file is in the dashboard folder.

-Motivation-

Demand forecasting is a core requirement in supply chain operations. Even simple forecasting pipelines reveal the constraints and considerations that appear in real production systems:

Time-aware train/test splits

Respecting lag structure

Comparing against operational baselines

Producing multi-step forecasts where each prediction depends on the previous one

Understanding forecast error and bias through residual analysis

This project establishes the foundation for a broader set of supply chain ML tools.

-Methods and Approach Data-

Synthetic daily demand is generated to simulate:

A constant base level,

A mild upward trend,

Weekly seasonality,

Random noise.

Although simulated, the data closely follows patterns found in warehousing, retail, and distribution demand streams.

Features

The model uses:

Lag 1 demand

7-day moving average

Day of week

These are standard operational forecasting features used in many real supply chain systems.

Models

Three approaches are evaluated:

Naive baseline (yesterday = tomorrow)

7-day moving average baseline

Random Forest Regressor

Performance is measured using MAE and MAPE.

Forward Forecasting

The notebook generates a 30-day iterative forecast where each predicted day becomes the input for the next. This mirrors how production forecasting systems operate.

Repository Structure
supplychain-ml/
│
├── notebooks/
│   └── demand_forecasting_basics.ipynb
│
├── data/              # placeholder for real datasets
│
└── README.md

Tools and Libraries

Python 3.11

Pandas / NumPy

Scikit-Learn

Matplotlib

VS Code + Jupyter Notebook

Power Bi

Next Steps

Planned enhancements for this lab include:

Forecasting multiple SKUs simultaneously(Done)

Adding holiday and promotion effects(Done)

Testing gradient boosting models(Done)

Packaging feature engineering and forecasting logic into reusable modules

Experimenting with probabilistic forecasts or prediction intervals


Integrating real-world datasets when available
