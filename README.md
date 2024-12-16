# Data Science in Stock market- JPX-Tokyo-exchange-Stock-prediction
This stock prediction project uses data contains historic data for a variety of Japanese stocks and options. The challenge is to predict the future returns of the stocks.

Little about ML.

### Table of Contents
Brief Intro - JPX Exchange group
Main Findings
Project Methodology
Cycle Description
01. Understand the data
02. Data Preparation
03. Feature Engineering
04. Exploratory Data Analysis (EDA)
05. Data Preprocessing
06. Feature Selection
07. Machine Learning Modeling
08. Hyperparameter Tuning
09. Error Interpretation and Business Performance
10. Deploy Machine Learning Model to Production
11. A Stock Predictor Bot
Conclusion


### JPX Exchange group
Japan Exchange Group, Inc. , abbreviated as JPX or Nippon Torihikijo, is a Japanese financial services company headquartered in Tokyo and Osaka. It is a "financial instruments exchange holding company" subject to the regulations of the Financial Instruments and Exchange Act enforced by the Financial Services Agency. It is also monitored by a separate self-regulatory body called Japan Exchange Regulation (JPX-R),dedicated to ensuring neutral and effective self-regulation operations defined under the Financial Instruments and Exchange Act.

The exchange group was formed by the merger of Tokyo Stock Exchange Group, Inc. [ja] and Osaka Securities Exchange Co., Ltd. on January 1, 2013. As a result of this merger and market reorganization, the Tokyo Stock Exchange (TSE) became the sole securities exchange of JPX and the Osaka Exchange (OSE) became the largest derivatives exchange of JPX.

JPX owns three licensed "financial instruments exchange" corporations: Tokyo Stock Exchange, Inc.,Osaka Exchange, Inc.,and Tokyo Commodity Exchange, Inc. (TOCOM). It also has an IT services and research arm, JPX Market Innovation & Research, Inc. (JPXI), and a central clearing counterparty, Japan Securities Clearing Corporation (JSSC).

As of June 2021, JPX is the world's fifth-largest stock exchange operator, behind NYSE, NASDAQ, SSE, and HKSE.


### Main findings


### project Methodology


###  A Business Objective
Rank the stocks from highest to lowest expected returns.

### 01. Understand the data
Available data:
financials.csv -  Results from quarterly earnings reports.
trades.csv - Aggregated summary of trading volumes from the previous business week.
stock_list.csv - Mapping between the SecuritiesCode and company names, plus general information about which industry the company is in.
stock_prices.csv -The core file of interest. Includes the daily closing price for each stock and the target column.

options.csv - Data on the status of a variety of options based on the broader market. Many options include implicit predictions of the future price of the stock market and so may be of interest even though the options are not scored directly.

secondary_stock_prices.csv - The core dataset contains on the 2,000 most commonly traded equities but many less liquid securities are also traded on the Tokyo market. This file contains data for those securities, which aren't scored but may be of interest for assessing the market as a whole.

Main focus is on stock_prices.csv but other datasets help to further improve our predictions.
Here's why each file might be relevant:

financials.csv: Contains corporate disclosure data.
Use: Understand events like earnings reports or mergers that might impact stock prices.

secondary_stock_prices.csv: Adds more details than stock_prices.csv.
Use:  This file contains data on stocks that are less liquid and not as frequently traded. These securities might not be "scored" (i.e., they might lack some quality data), but they are still part of the market and could provide insights about less prominent stocks.

trades.csv: Summarizes trading activity.
Use: High trading activity (TotalSales, TotalPurchases) might indicate investor interest or volatility.

options.csv: Reflects options trading data.
Use: High or low option prices can indicate market sentiment about the stock's future direction.

#### Main focus dataset : stock_prices.csv
1. Open: First traded price on a day
2. High: Highest traded price on a day
3. Low : Lowest traded price on a day
4. Close: Last traded price on a day
5. Volume: Number of traded stocks on a day
6. AdjustmentFactor:Change in stock price due to a split/reverse split. Correction from the closing price to the beginning of the next day.
7. ExpectedDividend: Projected dividend amoun
8. SupervisionFlag:Flag for supervised and delisted stocks. High risk of delisting
9. Target:Target variable; rate of return derived from the difference between one and two days later
