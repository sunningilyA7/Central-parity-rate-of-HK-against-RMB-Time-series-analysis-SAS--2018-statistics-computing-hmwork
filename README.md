# Centralparity-rate-of-HKdollar-RMB-Time-series-analysis-SAS-2018-statistics-computing-hmwork

## BackGround
Since 2018, the exchange rate of the US dollar against the Hong Kong dollar has hit the weak side exchange guarantee of 7.85, and the Hong Kong Monetary Authority has entered the market for the first time in 13 years to buy Hong Kong dollars. Afterwards, the Hong Kong Monetary Authority conducted a total of 13 foreign exchange interventions, selling US dollars in the foreign exchange market and buying around 51 billion Hong Kong dollars to maintain the linked exchange rate. The recent weakening of the Hong Kong dollar exchange rate has repeatedly touched upon weak side guarantees and the intervention of the Hong Kong Monetary Authority in the market. This is a normal phenomenon for Hong Kong to follow the United States into the process of substantial interest rate hikes in the context of the current US dollar interest rate hike, and does not mean that the Hong Kong linked exchange rate system will change.

This article first analyzes the data of Hong Kong dollar against Chinese yuan through descriptive statistics, specifically screens the data, studies the data characteristics of this variable, and observes the skewness and kurtosis of the data; Secondly, the future trend of the Hong Kong dollar against the Chinese yuan will be analyzed through time series analysis. Two months after the completion of this article, the advantages and disadvantages of using time series analysis methods will be analyzed by comparing the real trend of the Hong Kong dollar against the Chinese yuan; Finally, obtain specific results and attempt to explore the most suitable interest rate tool for # hedging # against the Hong Kong dollar against the Chinese yuan.



## Descriptive statistics


# Table 1: HKDCNY Average  
**Analysis Variable:** HK  

| Count | Mean      | Standard Deviation | Minimum   | Maximum   |
|-------|-----------|--------------------|-----------|-----------|
| 1218  | 82.3443358 | 3.4421556          | 78.5750000 | 89.6380000 |


We can observe that among the 1218 data points, the minimum value is around 78.5, and the maximum value is around 89.63. The minimum value represents the moment when the Hong Kong Dollar (HKD) had the highest value compared to the same amount of Renminbi (CNY), while the maximum value represents the time when the Hong Kong Dollar had the lowest value.

Next, we will look at the distribution of the HKD to CNY midpoint exchange rate through Figure 1:
![](./Figure1.png)

We found that, over five years, the HKDCNY value of 79.2 occurred the most frequently, followed by 79.8 and 78.6.

## 2. Exploratory Descriptive Statistics
Using SAS software, we obtained the exploratory descriptive statistics of the HKDCNY midpoint exchange rate over the given time period, as shown below:

### Table 2: Exploratory Data on HKD to CNY Midpoint Exchange Rate

| Metric | Value | Metric | Value |
|--------|-------|--------|-------|
| Count            | 1218        | Weighted Sum     | 1218       |
| Mean             | 82.3443358  | Total Observations | 100295.401 |
| Standard Deviation | 3.4421556 | Variance         | 11.8484352 |
| Skewness         | 0.58840951  | Kurtosis         | -1.064352  |
| Uncorrected SS   | 8273177.72  | Corrected SS     | 14419.5456 |
| Coefficient of Variation | 4.18019718 | Standard Error of Mean | 0.09862951 |

#### Basic Statistical Measures
| Position | Variability |
|----------|-------------|
| Mean     | 82.34434    |
| Standard Deviation | 3.44216 |
| Median   | 80.96250    |
| Variance | 11.84844    |
| Mode     | 79.56200    |
| Range    | 11.06300    |
| Interquartile Range | 5.65100 |

#### Position Test: Mu0 = 0
| Test    | Statistic | p-value |
|---------|-----------|---------|
| Student t | 834.8854  | Pr > t  < .0001 |
| Sign M | 609        | Pr >= M < .0001 |

#### Signed-Rank Test: Mu0 = 0
| Test    | Statistic  | p-value |
|---------|------------|---------|
| Signed-Rank S | 371185.5 | Pr >= S < .0001 |

#### Extreme Observations
| Minimum Value | Observation | Maximum Value | Observation |
|---------------|-------------|---------------|-------------|
| 78.575        | 1046        | 89.560        | 324         |
| 78.594        | 1037        | 89.577        | 332         |
| 78.601        | 1047        | 89.583        | 323         |
| 78.620        | 1036        | 89.586        | 321         |
| 78.623        | 1055        | 89.638        | 320         |


Since the analysis here focuses mainly on time series data, **skewness** and **kurtosis** are usually good measures for evaluating time series data. 

**Skewness** is a statistic that describes the degree of asymmetry in a distribution. It is used to measure symmetry in a time series. If the skewness is negative, the left side of the mean has more spread than the right side. If the skewness is positive, the left side of the mean has less spread than the right side. For a **normal distribution** (or strictly symmetrical distribution), skewness equals 0. Skewness is the **standardized 3rd central moment** of the distribution (for a normal distribution, skewness = 0). If skewness > 0, it indicates a **right-tailed distribution**, and if skewness < 0, it indicates a **left-tailed distribution**. 

When the skewness is greater than 0, the distribution is **right-skewed** with a heavier tail on the right. In stock markets, **A-shares** (stock indices) tend to be **left-skewed**, while individual stocks are more often right-skewed. In the stock market, stocks with right-skewed returns are often attractive to speculators, as there is a chance of achieving large returns, i.e., "small bets for big gains." Therefore, it is advised to avoid these stocks.

### Kurtosis
The concept of **kurtosis**: Kurtosis is a measure used to reflect the sharpness or flatness of the peak of a frequency distribution curve. Sometimes, two data sets can have the same arithmetic mean, standard deviation, and skewness but differ in the sharpness of their distribution peaks. Here, the kurtosis is less than 0. The closer the kurtosis is to 0, the more the distribution resembles a **normal distribution**. The further from 0 it is, the less the data resembles a normal distribution. If the kurtosis is negative, it indicates that the data is more concentrated, with fewer data points on either side. If it's positive, the opposite is true.

