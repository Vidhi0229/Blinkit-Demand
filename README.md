# Blinkit-Demand
> **Real-Time Product Demand Forecasting in Quick Commerce using Deep Learning**

This project implements a **ConvLSTM-based model** for **real-time demand forecasting** of products in Blinkit, a leading quick commerce platform. It explores time-series modeling with extensive preprocessing and feature engineering to enhance prediction accuracy.

## Table of Contents

* [Overview](#overview)
* [Dataset](#dataset)
* [Preprocessing](#preprocessing)
* [Model Architecture](#model-architecture)
* [Evaluation Metrics](#evaluation-metrics)
* [Results](#results)
* [Installation](#installation)
* [License](#license)
* [Authors](#Authors)


## Overview

Blinkit's dynamic nature of product consumption across different cities and categories demands robust forecasting mechanisms. This project uses a **ConvLSTM (Convolutional LSTM)** model to learn spatiotemporal patterns in sales data for short-term demand prediction for next 7 days. The key contributions are:

* Data engineering for time-series forecasting.
* Scaled and encoded features.
* Exploration of ConvLSTM to capture spatial (city/item) and temporal (daily) demand patterns.


## Dataset

CSV file with daily sales of multiple items across cities that contain features:

  * `date`: Date of transaction
  * `city_name`, `item_name`, `category`
  * `qty_sold`, `mrp`
  * Derived Features: `revenue`, `weekday`, `is_weekend`, `price_tier`, `order_size`

##  Preprocessing

Data preprocessing involves:

* Handling missing values (median for numerical, mode for categorical).
* Time features extraction: `weekday`, `month`, `is_weekend`, etc.
* Label encoding for categorical variables.
* Scaling strategies:

  * Standard Scaler
  * MinMax Scaler
  * Log + MinMax
* Derived Features:

  * `revenue = qty_sold × mrp`
  * Price tiers and order sizes via quantile binning


## Model Architecture

We use a **ConvLSTM** model that combines:

* CNN layers to learn spatial dependencies (e.g., product categories, cities)
* LSTM layers to learn temporal dependencies (e.g., daily/weekly trends)


## Evaluation Metrics

* **MAE** (Mean Absolute Error)
* **RMSE** (Root Mean Squared Error)
* **MAPE** (Mean Absolute Percentage Error)
* **R² Score**

## Results

The ConvLSTM model successfully captured demand fluctuations across cities and product categories with significantly lower error than baseline linear or naive forecasting methods. Visualizations highlight prediction vs. actual trends.

**Achieved:**
- R-squared: 0.9532 (95.32%)
- Normalized Accuracy: 97.13%
- MAPE-based Accuracy: 49.02%
- Overall Model Accuracy: 91.41%


## Installation

Ensure you have the following libraries:

```bash
pip install pandas numpy scikit-learn matplotlib seaborn
```

You’ll also need:

* TensorFlow or PyTorch (depending on the implementation of ConvLSTM)
* Jupyter Notebook or Colab (for interactive exploration)

## License

This project is licensed under the MIT License.

## Authors
**Vidhi Srivastava**

[Linkedin](https://www.linkedin.com/in/vidhisrivastava01/)

[Github](https://github.com/Vidhi0229)

