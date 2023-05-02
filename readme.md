# Uncovering Relationships between Macroeconomic Indicators and Stock Market Performance: A Predictive Modeling Approach
This repository contains the datasets and code used for the aforementioned project. 

## Project Description
The project involves gathering macroeconomic and securities price data from different sources, transforming the data, and combining it to uncover correlations among macroeconomic indicators and to predict S&P500 index with them. Raw datasets downloaded are available in `/datasets/raw`. 

Different models have been developed using the final dataset to predict S&P500 index. Different models attempted to predict S&P500 index are available in `/Models/` folder.

## Dataset Description
The `datasets` directory contains:
* `macroeconomic_indicators.xlsx`: Different macroeconomic indicators daily/monthly data collected from FRED, gold price data from Kaggle
* `Securities.csv`: Stock & Industry ETF data downloaded using yFinance library

## Installation
* Download macroeconomic indicator datasets from [FRED website](https://fredhelp.stlouisfed.org/fred/data/downloading/using-the-download-data-link/)
* Clone the repository
* Install the required libraries using `pip install -r requirements.txt`

## Usage
### Data Cleaning and Transformation
Run the following jupyter notebooks sequentially to get the `final_output.csv` which will be used for modeling and Tableau dashboards
* `data_preprocessing.ipynb` - combine macroeconomic data from different Excel worksheets and use forward fill for market close days
* `Script_to_download_stock_data.ipynb` - notebook to download security price data using yFinance library
* `feature_selection.ipynb` - Principal Component Analysis to select features (did not use in the final model/viz)
* `final_dataset.ipynb` - merge macroeconomic indicators and security price data

### Modeling
In this project we have built three different models - Binary Classification, LSTM Prediction, Vector Auto Regression. The code for each of the models can be found in `/Models/` folder. Run the following files for the respective models.
* `Binary_Classification_Models.ipynb`
* `LSTM_Modeling_Prediction.ipynb`
* `VAR_Model.ipynb`

### Tableau Dashboard
Our final product on this project is a Tableau dashboard that provides an interactive visualization of correlations among different macroeconomic indicators and security prices. We have also included the results of our best model in the dashboard. Link to the dashboard can be found here - [Uncovering Relationships between Macroeconomic Indicators and Stock Market Performance](https://public.tableau.com/app/profile/karthick.mani/viz/CSE-6242DVAProjectTeam065/CorrelationofMacroEconomicFactors#1). On the Tableau dashbaord, user can interact in the following ways:
* Click on Correlation Matrix to see the time series plot with the two indicators and with S&P500
* Adjust the paramter `Toggle Indicators` to see the correlation matrix of stocks and Industry ETFs
* Adjust the `Date` range to study different periods like Great Financial Crisis, Dotcom Bubble, COVID Lockdowns
* Click on `Show Predictions` to see the prediction from our best model - LSTM
