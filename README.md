# St-Clair-Project-Financial-Markets-
This is the repository for the college project for St Clair (DAB100 Course).

This code is for analyzing the financial statements of all the companies listed in the S&P500 index. It starts by importing necessary libraries such as pandas, numpy, matplotlib, seaborn, etc. Then it sets the required directories to access the financial data and output data saved on Google Drive.

The code then pulls real-time data on the performance of the S&P500 index from a reliable source, macrotrends.net. It prints the year-to-date (YTD) performance of the index.

Next, the code uses an API provided by Financial Modelling Prep (FMP), which is a data vendor, to gather raw data for all the companies listed in the S&P500 index. The data is stored on Google Drive in the JSON format. The code loops through the list of tickers and pulls the financial data for each individual ticker, such as company profile, income statements, balance sheets, cash flow, financial ratios, and financial scores, and stores them locally.


The next part of the code reads the stock data from a CSV file and creates an empty list to store the sector-wise data. It then groups the stock data by sector and iterates over each sector group to calculate sector performance as the mean of percentage change (YTD) column. The calculated data is saved into a CSV file for each sector. Other sector-wise performance metrics are calculated, such as Sector PE, Sector - EPS, and Sector - Net Profit Margin (TTM). The calculated data is saved into a CSV file for all sectors.

The next part of the code creates visualizations for each sector. The function sector_performance_visual(i) is used to plot the graphs for all the sectors in the S&P500 Index. The function reads data from a CSV file for each sector and creates a filtered table for plotting a bar chart for the top 5 and least 5 performing companies per sector. The function sets the plot style, colors for the bars in the plot, and creates the plot. The top and bottom performing companies are plotted as bars, and their values are shown above the bars. Finally, the function saves the plot into a PNG file.

Overall, this part of the code provides valuable insights into sector-wise performance and helps identify which companies and sectors are driving growth and which are underperforming, which can provide valuable insights for investors and analysts.


This next block of code block is a profitability analysis of the companies in the S&P 500 Index. The analysis focuses on the Net Profit Margin ratio, which measures the rate of return earned on shareholder equity. The goal is to identify which companies and sectors are generating the highest returns for their shareholders. The analysis involves creating visualizations using data visualization tools to make it easy to compare the Net Profit Margin Ratio of individual companies and sectors within the index.

This code block contains a function named sector_profitability_visual that takes a sector name as input and produces a visualization for the profitability analysis of that sector. The function reads in a CSV file that contains the data for the companies in that sector and creates a filtered table for plotting a bar chart for the top 5 and bottom 5 performing companies per sector. It then sets the plot style and creates a bar plot using the seaborn library, with the net profit margin on the y-axis and the company names on the x-axis. The plot also includes a horizontal line for the S&P500 Index performance and the sector average performance.

This code block also contains a for loop that iterates over all sectors in the S&P500 Index and applies the sector_profitability_visual function to each sector. The loop prints a summary of the plot for each sector, including the most profitable company, the least profitable company, and the average profitability of companies in that sector.
