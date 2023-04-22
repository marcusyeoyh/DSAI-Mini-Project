# Welcome to our DSAI MiniProject Repository!

## About
Hi! We are a team consisting of Lim Sui Kiat and Marcus Yeo, currently Year 2 Computer Science students in NTU. This is a Mini-Project for SC1015 (Introduction to Data Science and Artificial Intelligence) which focuses on data from Yahoo Finance using the yFinance Python Library

If you're interested, you can see our [project video](https://www.youtube.com/watch?v=VFHYOmRooUY&ab_channel=MARCUSYEO) and [slide deck](https://www.canva.com/design/DAFgudHeVtk/eeOHe96Y1mWe2a6eJTeXXQ/edit?utm_content=DAFgudHeVtk&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton) here!

## For a detailed walkthrough, please view the source code in order form:
[Full Code](https://github.com/sktlim/PairsTradingExploration/blob/main/DSAI_Project.ipynb)
1. Problem Definition
* [README.md](https://github.com/sktlim/PairsTradingExploration/blob/main/README.md)
2. Data Collection and Preperation

The notebook in this portion is used to extract data from S&P 500 symbols list to find cointegrated pairs of stocks to conduct our pairs trading strategy upon. After obtaining the data, we use the Missingno library for data cleaning to remove any NULL values. We then go on to find cointegrated pairs. For our clustering task, we are interested in the volatility and performance of stocks and thus we want to obtain the variance and returns on an annual level. Data scaling is then used to reduce noise. We then apply K-Means clustering to identify groups of stocks with their nearest mean. Using the elbow method, we identified that the optimal number of clusters that we should have is around 6. We then analyzed each cluster to determine highly cointegrated pairs

3. Exploratory Analysis of Target Pair

Having identified the two highly conintegrated pairs, we did more analysis on each stock and their prices, namely plotting a boxplot, histogram and violin plot to conduct uni-variate analysis as well as a graph to observe trends in stock prices. The correlation between the two stocks, as well as the degree of cointegration and stationarity was calculated using the p-value test and ADF test respectively, which all passed. We then calculated the buy/sell signals of Rolling Z-Score Pairs Trading by calculating Rolling Z-Score values using the 5 and 20 day Moving Averages and the standard deviation. This will be used throughout the project as the prediction set,

4. Use of Machine Learning

After carrying out exploratory data analysis/visualization, we then went on to use machine learning models to derive a solution to our problem. We utilised Decision Trees, Random Forest and Neural Networks to obtain different buy/sell signals, which were then compared to the earlier calculated Rolling Z-Score signals to determine classification accuracy

5. Final insights

Lastly, in this notebook we utilised the signals we obtained to calculate the predicted profit/loss if we were to apply the models to 2022. We managed to identify which model gave us the best profitability. We also added some concluding thoughts on the problem, solution and models used.

## Contributors
* @sktlim (Lim Sui Kiat)
* @marcusyeoyh (Marcus Yeo)

## Background
Sui Kiat and I had always been interested in stock trading and finance. One day, we came across a new trading strategy called Pairs Trading. While we were very excited about the upside of this trading method and saw it as a viable strategy, we noticed some glaring weaknesses with it, namely how Rolling Z-Score is derived:
* False Signals
* Limited Market Opportunities
* Overfitting
* Correlation Breakdown

Surely there has to be a better alternative for Rolling Z-Score, yet maintain the effectiveness and profitability of Pairs Trading?

## Problem Formulation
Hence we ask:
* How can we leverage machine learning techniques and other stock indicators to replace the Rolling Z-Score in pairs trading, while ensuring consistent profitability?

To answer this question, we set out to uncover the different parameters and stock indicators that could act as a replacement, as well as suitable Machine Learning models that we could use.

## Models Used
1. K-Means Clustering
2. Decision Tree
3. Random Forest
4. Neural Networks

## Conclusion
Challenges:
* Did not know what window to choose to evaluate buy/sell as well as window to calculate MA when determining RZS
* How to define the profit function and how to use it as a basis for comparison amongst ML models

Insights:
* Overall, all our models were able to produce buy/sell signals that made sense when referenced with the Ratio graph. All methods made money over the course of a year
* Data from different years (2019-2020) could have a profound impact on the accuracy and profitability of the different methods
* Application of the findings could be affected by the stock/industry that was chosen to conduct Pairs Trading in
* More sets of stocks and greater time periods can be analyzed to optimize the feasibility of ML techniques in Pairs Trading

Future Improvements:
* Gather and incorporate more financial indicators from various aspects to improve Random Forest Algo
* Conduct more investigation into different stocks and see if the observation holds across industries
* Create a more robust profit/loss algorithm to better assess the true profitability of a model

## What did we learn from this project?
* The use of many different Machine Learning Models
* How to work and communicate as a team to complete a project
* The importance of using the Data Science Flowchart to determine how to approach a data science problem

## References
* [Spencer Pao's Github](https://github.com/SpencerPao/Quantitative_Strategies)
*  https://towardsdatascience.com/random-forest-in-python-24d0893d51c0
* https://algotrading101.com/learn/cluster-analysis-guide/
* https://www.youtube.com/watch?v=J4Wdy0Wc_xQ
