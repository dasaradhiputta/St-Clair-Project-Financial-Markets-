# St-Clair-Project-Financial-Markets-
This is the repository for the college project for St Clair (DAB100 Course).

This code is for analyzing the financial statements of all the companies listed in the S&P500 index. It starts by importing necessary libraries such as pandas, numpy, matplotlib, seaborn, etc. Then it sets the required directories to access the financial data and output data saved on Google Drive.

The code then pulls real-time data on the performance of the S&P500 index from a reliable source, macrotrends.net. It prints the year-to-date (YTD) performance of the index.

Next, the code uses an API provided by Financial Modelling Prep (FMP), which is a data vendor, to gather raw data for all the companies listed in the S&P500 index. The data is stored on Google Drive in the JSON format. The code loops through the list of tickers and pulls the financial data for each individual ticker, such as company profile, income statements, balance sheets, cash flow, financial ratios, and financial scores, and stores them locally.

Overall, the code is designed to provide an efficient and reliable way to monitor and analyze the financial performance of all the companies listed in the S&P500 index.
