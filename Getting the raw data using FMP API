import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import os
import time
from google.colab import drive
from IPython.display import HTML
import plotly.graph_objs as go
import plotly.offline as pyo


drive.mount('/content/drive')

save_path = "drive/MyDrive/St Clair/Project/Financial Data/"

out_path = "drive/MyDrive/St Clair/Project/Output Data/"

op_files_path ="drive/MyDrive/St Clair/Project/Output Data/Sector Wise Analysis/" 

index_data = pd.read_html("https://www.macrotrends.net/2526/sp-500-historical-annual-returns")

api_key = "48eef5fba10cd7e9b35ca3418d4e3fac" # Please use your own API Key to use this analysis. It is completely free and you will get the key, once you enroll on Financial Modelling Prep Website.

stocklist = pd.read_csv("https://financialmodelingprep.com/api/v3/sp500_constituent?datatype=csv&apikey="+ str(api_key))
tickers = list(stocklist['symbol'])


# Looping the entire code through the list of tickers to get the data for each individual ticker and store that data locally.
# Use indexing in the list because API only allows 250 calls per day. We are currently at 35th stock in the S&P500 list

for i in tickers:
    # Creating the save path for the financial data sets to be downloaded
    directory = save_path + i
    if not os.path.exists(directory):
        os.makedirs(directory)

    # Mentioning the URLs for individual datasets for each company
    profile_url = "https://financialmodelingprep.com/api/v3/profile/" + i + "?apikey=" + str(api_key)
    income_statement_url = "https://financialmodelingprep.com/api/v3/income-statement/" + i + "?limit=120&apikey=" + str(api_key)
    balance_sheet_url = "https://financialmodelingprep.com/api/v3/balance-sheet-statement/" + i + "?limit=120&apikey=" + str(api_key)
    cash_flow_url = "https://financialmodelingprep.com/api/v3/cash-flow-statement/" + i + "?limit=120&apikey=" + str(api_key)
    financial_ratios_url = "https://financialmodelingprep.com/api/v3/ratios-ttm/" + i + "?apikey=" + str(api_key)
    financial_scores_url = "https://financialmodelingprep.com/api/v4/score?symbol=" + i + "&apikey=" + str(api_key)
    price_pct_change_url = "https://financialmodelingprep.com/api/v3/stock-price-change/" + i + "?apikey=" + str(api_key)

    # Saving the datasets to the file path mentioned above.
    profile = pd.read_json(profile_url).T
    profile.to_json(save_path + i + "/Company Profile.json")

    income_statements = pd.read_json(income_statement_url).T
    income_statements.to_json(save_path + i + "/Income Statements.json")

    balance_sheets = pd.read_json(balance_sheet_url).T
    balance_sheets.to_json(save_path + i + "/Balance Sheets.json")

    cash_flow = pd.read_json(cash_flow_url).T
    cash_flow.to_json(save_path + i + "/Cashflow.json")

    financial_ratios = pd.read_json(financial_ratios_url).T
    financial_ratios.to_json(save_path + i + "/Financial Ratios.json")

    financial_scores = pd.read_json(financial_scores_url).T
    financial_scores.to_json(save_path + i + "/Financial Scores.json")

    percentage_change = pd.read_json(price_pct_change_url).T
    percentage_change.to_json(save_path + i + "/Percentage Change.json")

    print("The data is successfully downloaded for "+i)
    time.sleep(0.05)
