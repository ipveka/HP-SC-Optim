# HP-SC-Optim

## Goal of the Competition

The goal of this competition is to forecast the optimal inventory level that HP should for multiple products on a weekly basis.

## Context

This competition is sponsored by HP as part of the HackUPC 2023 event. It is about a real business need, as inventory optimization is one of the key area of operational efficiency for a company.

Some remarks:

- Data is not perfect – missing values, duplicates, errors, etc.
- Sales should decrease the inventory in the same week.
- You don’t have the future sales, since they have not happened.
- Cutoff is this current week. (May 9th, 2023)
- Data is fictitious.

## Evaluation metric

- RMSE

The RMSE is calculated by taking the square root of the mean of the squared differences between the predicted and actual values. RMSE is a popular metric because it emphasizes larger errors more than smaller ones, as it is a quadratic function of the differences between predicted and actual values. 

## Files

- train.csv - the training set.
- test.csv - the test set.
- sample_submission.csv - a sample submission file in the correct format.

## Columns

- id: yearweek + - + product_number. Unique identifier of the time series.
- date: YYYY-mm-dd
- yearweek: YYYYww
- product_number: Unique ID for each product.
- reporterhq_id: Unique ID for each reseller (vendor).
- prod_category: Product category with a funny name that groups products from the same product line together.
- specs - Specifications of the product. This can be the RAM + Graphics card, or other components.
- display_size:  Display size or screen of the PC.
- segment:  Target segment of the product.
- sales_units: Sales to the final customer of the product for that week.
- inventory_units:  Target variable. Inventory for each product_number and reporterhq_id for a specific week.

https://www.kaggle.com/competitions/hp-supply-chain-optimization/overview

## Libraries

Run pip install -r requirements.txt in terminal to get the necessary libraries

## Structure

There project is divided in 6 areas 

- 1.data_exploration
- 2.data_cleansing
- 3.feature_engineering
- 4.run_test_model
- 5.forecast
- 6.analysis

## Feature Engineering

### Numerical

- inventory_lag4
- inventory_lag12
- inventory_lag52
- sales

### Categorial

Categorial variables are encoded

- product_number
- reporterhq_id
- segment
- prod_category
- season
- year
- month
- week

## Further improvements

- Improve data cleansing of duplicates
- Apply Rolling Window for Testing
- Apply rolling backfilling for inventory lags
- Predict future sales: Now using Naive
- Add more models to test and compare
- Measure forecast bias in test

## Model

- XGBoost

June 2023
