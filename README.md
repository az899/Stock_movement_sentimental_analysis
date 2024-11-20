Stock Movement Sentiment Analysis
This repository contains an R Markdown script for analyzing stock movements and performing sentiment analysis. The project is centered around Apple's stock (AAPL), combining technical analysis using Bollinger Bands and moving averages with sentiment analysis of news articles fetched from the GDELT database. The results are used to evaluate stock trends and their correlation with market sentiment.

Features
1. Stock Market Analysis
Technical Indicators:
Bollinger Bands (20-day moving average with ±2 standard deviations).
10-day Simple Moving Average (SMA).
Signal Classification:
Identifies bullish, bearish, and neutral trends based on technical indicators.
Detects divergence between Bollinger Bands and SMA signals.
2. Sentiment Analysis
Fetches news articles on non-divergent dates using the GDELT database.
Performs sentiment analysis using the AFINN lexicon.
Compares GDELT's avgTone sentiment scores with AFINN sentiment scores.
3. Data Visualization
Visualizes stock price trends, Bollinger Bands, and SMA signals.
Highlights divergent and non-divergent signals.
Displays sentiment trends and their correlation with stock movements.
Generates animated plots and visualizations.
Setup Instructions
Prerequisites
Ensure you have the following installed:

R (≥ 4.0)
RStudio (optional, for R Markdown rendering)
Required R packages (see below).
Required R Packages
Install the following packages before running the script:

r
Copy code
install.packages(c('quantmod', 'TTR', 'lubridate', 'ggplot2', 'plotly', 
                   'reshape2', 'dplyr', 'tidytext', 'textdata', 'rvest', 'animation', 
                   'devtools', 'purrr'))
Additionally, install gdeltr2 and its dependencies:

r
Copy code
devtools::install_github("abresler/gdeltr2")
How to Use
Load the Project: Clone this repository and open the ass3.Rmd file in RStudio or any R Markdown editor.

Run the Analysis:

Execute the R Markdown file to fetch stock data, calculate technical indicators, and analyze sentiment.
View Results:

Visualizations are automatically generated for:
Stock trends and signals.
Correlation between sentiment and stock movements.
Sentiment and market movement correlations are saved as visualizations and in datasets.
Outputs:

Stock movement data: apple_stockmovement_data.csv
News data: apple_news_data.csv
Animated plots and visualizations.
Project Workflow
1. Stock Data Analysis
Fetch stock data for Apple (AAPL) over a 360-day period.
Apply Bollinger Bands and SMA indicators.
Classify signals (bullish, bearish, neutral, divergent).
2. Fetch News Data
Use gdeltr2 to fetch relevant news for non-divergent dates.
Perform sentiment analysis on the fetched news.
3. Sentiment Correlation
Compare AFINN sentiment scores with GDELT's avgTone sentiment scores.
Normalize scores and classify market sentiment.
4. Visualization
Generate interactive plots using plotly and ggplot2.
Create animations to visualize stock trends and sentiment over time.
Key Visualizations
Stock Trends: Stock price with Bollinger Bands and SMA indicators.
Sentiment Analysis: Correlation between sentiment and stock trends.
Combination Trends: Bar plots showing sentiment and stock trend combinations.
Limitations & Recommendations
Lexicons: The project uses the AFINN lexicon for sentiment analysis. Using additional lexicons (e.g., NRC, Bing) can improve robustness.
Data Quality: GDELT data may have incomplete or noisy records. Cross-checking with other sources is recommended.
