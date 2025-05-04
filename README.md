# Walmart Sales Forecasting

## Project Overview
This project is developed based on the [Kaggle M5 Forecasting - Accuracy](https://www.kaggle.com/competitions/m5-forecasting-accuracy). The challenge aims to estimate unit sales of Walmart retail goods over a 28-day forecasting horizon using historical sales data.
Sales forecasting is critical for efficient inventory management and supply chain planning. In this competition, participants were tasked to predict daily item-level sales across 3 U.S. states (CA, TX, WI), using hierarchical time series data that includes information on product categories, store locations, calendar events, and price fluctuations.

## Objective
Accurately predict 28 days of unit sales for over 30,000 Walmart products across 10 stores, using historical sales, calendar, and price data.
The project explores multiple forecasting approaches, including:
- Traditional Machine Learning (LightGBM)
- Deep Learning with Recurrent Neural Networks (LSTM & GRU)

## Dataset Description
The dataset is provided by Walmart and includes:
- Sales data: Daily unit sales per item per store
- Calendar: Holiday/event indicators, weekday information
- Prices: Weekly prices per item-store combination

## Modeling Approaches
###  LightGBM
A gradient boosting framework that provides fast, high-accuracy results. Categorical features are one-hot encoded and continuous variables are normalized. Features such as lag sales, moving averages, and event flags are engineered to enrich model learning.

### LSTM
LSTM (Best Performing Model)
LSTM models are built per store to reduce computation load and better capture store-specific temporal dynamics. The model learns from a 28-day input sequence to predict 56 days ahead using a sliding window mechanism.
LSTM Performance: Public Score: 1.37348 / Private Score: 1.50406

### GRU
Gated Recurrent Unit (GRU) models are trained per product category (FOODS, HOBBIES, HOUSEHOLD). GRU offers faster training with fewer parameters compared to LSTM and is effective in capturing short-term seasonality.

## Insights & Recommendation
LSTM models effectively capture complex sequential patterns, incorporating promotion and holiday effects.
Item-level forecasts allow Walmart to tailor inventory plans. For example:
- Store CA_1 shows high demand in Week 2
- Store WI_1 shows increased sales on weekends
Moving forward, developing an automated forecasting pipeline can enable dynamic inventory adjustment and reduce stockouts or overstocking.
