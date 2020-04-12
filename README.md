# Unit 4 Homework Assignment: A Whale Off the Port(folio)

![Portfolio Analysis](Images/portfolio-analysis.png)

## Background

The investment division of Harold's company has been investing in algorithmic trading strategies. Some of the investment managers love them, some hate them, but they all think their way is best.

You just learned these quantitative analysis techniques with Python and Pandas, so Harold has come to you with a challenge—to help him determine which portfolio is performing the best across many areas: volatility, returns, risk, and Sharpe ratios.

You will need to create a tool (an analysis notebook) that analyzes and visualizes the major metrics of the portfolios across all of these areas, and determine which portfolio outperformed the others. You will be given the historical daily returns of several portfolios: some from the firm's algorithmic portfolios, some that represent the portfolios of famous "whale" investors like Warren Buffett, and some from the big hedge and mutual funds. You will then use this analysis to create a custom portfolio of stocks and compare its performance to that of the other portfolios, as well as the larger market (S&P 500).

In this homework assignment, you will be accomplishing three main tasks:

1. [Read in and Wrangle Returns Data](#Prepare-the-Data)
2. [Determine Success of Each Portfolio](#Conduct-Quantitative-Analysis)
3. [Choose and Evaluate a Custom Portfolio](#Create-Custom-Portfolio)

---

## Instructions

**File:** [Whale Analysis Starter Code](Starter_Code/whale_analysis.ipynb)

### Prepare the Data

First, read and clean several CSV files for analysis. The CSV files include whale portfolio returns, algorithmic trading portfolio returns, and S&P 500 historical prices. Use the [Whale Analysis Starter Code](Starter_Code/whale_analysis.ipynb) to complete the following steps:

1. Use Pandas to read in each of the [CSV files](Starter_Code/Resources) as a DataFrame. Be sure to convert the dates to a `DateTimeIndex`.

2. Detect and remove null values.

3. Remove dollar signs from the numeric values and convert the data types as needed.

4. The whale portfolios and algorithmic portfolio CSV files contain daily returns, but the S&P 500 CSV file contains closing prices. Convert the S&P 500 closing prices to daily returns.

5. Join `Whale Returns`, `Algorithmic Returns`, and the `S&P 500 Returns` into a single DataFrame with columns for each portfolio's returns.

  ![returns-dataframe.png](Images/returns-dataframe.png)

### Conduct Quantitative Analysis

Analyze the data to see if any of the portfolios outperform the stock market (i.e., the S&P 500). 
Using a .sum() function, we can see that the 

#### Performance Analysis

1. Calculate and plot cumulative returns. Does any portfolio outperform the S&P 500? 
Both Algo 1 and Berkshire Hathaway Inc outperform the S&P 500 over our date range. 

#### Risk Analysis

1. Create a box plot for each of the returns. Which box has the largest spread? Which has the smallest spread?
The largest spread is the Tiger Global Management hedge fund. The smallest spread is Paulson & Co Inc.

2. Calculate the standard deviation for each portfolio. Which portfolios are riskier than the S&P 500? 
Both Berkshire Hathaway Inc and Tiger Global Management are riskier portfolios than the S&P 500. 

#### Rolling Statistics

1. Plot the rolling standard deviation of the firm's portfolios along with the rolling standard deviation of the S&P 500. Does the risk increase for each of the portfolios at the same time risk increases in the S&P?
The Tiger Global Management Fund has risk changes that are not in line with risk changes in the S&P 500. The other portfolios match the timing, if not the itensity of the risk changes. 

2. Construct a correlation table for the algorithmic, whale, and S&P 500 returns. Which returns most closely mimic the S&P?
The Algo 2 portfolio most closely mimics the S&P 500. 

3. Choose one portfolio and plot a rolling beta between that portfolio's returns and S&P 500 returns. Does the portfolio seem sensitive to movements in the S&P 500?
I chose Algo 2. As expected, since i chose the most highly-correlated portfolio, the changes in the portfolio are sensitive to the S&P500

### Plot Sharpe Ratios

Investment managers and their institutional investors look at the return-to-risk ratio, not just the returns. (After all, if you have two portfolios that each offer a 10% return, yet one is lower risk, you would invest in the lower-risk portfolio, right?)

1. Using the daily returns, calculate and visualize the Sharpe ratios using a bar plot.

2. Determine whether the algorithmic strategies outperform both the market (S&P 500) and the whales portfolios.
The Algo 1 strategy outperforms the S&P 500 both at a total-return and risk-adjusted(Sharp Ratio) level, while Algo 2 falls short on both counts. Algo 1 also beats all of the whales portfolios, while Algo 2 falls in the middle in comparison to the other portfolios. 

### Create Custom Portfolio

Harold is ecstatic that you were able to help him prove that the algorithmic trading portfolios are doing so well compared to the market and whales portfolios. However, now you are wondering whether you can choose your own portfolio that performs just as well as the algorithmic portfolios. Investigate by doing the following:

1. Visit [Google Sheets](https://docs.google.com/spreadsheets/) and use the in-built Google Finance function to choose 3-5 stocks for your own portfolio.
Chose a basket of 22 stocks and 1 cash position that represents a porfolio currently managed by the firm I work for. 

2. Download the data as CSV files and calculate the portfolio returns.

3. Add your portfolio returns to the DataFrame with the other portfolios and rerun the analysis. How does your portfolio fair?
After downloading one year of history for 22 stocks and combining all of the data, I realized that the previous year had very little overlap with the data provided in the starter files. I then calculated all of the statistics for the current portfolio, but the comparison for risk and performance statistics will not be an "apples to apples" comparison due to the lack of overlapping data. I did, however, import SPY for the previous year for the S&P Beta and Risk comparisons. 


---

## Resources

[Pandas API Docs](https://pandas.pydata.org/pandas-docs/stable/reference/index.html)

---

## Hints

* After reading each CSV file, don't forget to sort each DataFrame in ascending order by the Date using `sort_index`. This is especially important when working with time series data as we want to make sure Date indexes go from earliest to latest.

* The Pandas functions used in class this week will be useful for this assignment.

* Be sure to use `head()` or `tail()` when you want to look at your data but don't want to print to a large DataFrame.

---

## Submission

1. Create a Jupyter Notebook containing your data preparation, analysis, and visualizations. Put your analysis and answers to the assignment questions in raw text (markdown) cells in the report.

2. Submit your notebook to a new GitHub repository.

3. Add the URL of your GitHub repository to your Assignment when submitting via Bootcamp Spot.

---

© 2019 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.
