---
PREDICTING S&P 500 INDEX USING RANDOM FOREST CLASSIFIER
---

S&P 500 is the world's most popular stock index. It is composed of 500 of the biggest publicly traded companies in the US like Apple, Amazon, Microsoft, and Tesla.

This project aims predict the S&P500 Index using feature engineering, and building a Random Forest Classifier model. Data has been webscraped with the following variables:

ShillerPERatio

- an inflation-adjusted 10-year earnings data to lessen the impact of short-term impacts, which helps investors determine whether an index was truly over or undervalued. It is the quotient of stock price and average inflation-adjusted 10-year Earnings Per Share (EPS).

Earnings

- amount you earn in profit for every share you own.

Treasury Rate

- the annual return investors can expect from holding a US government security with a given maturity.

Unemployment Rate

- the percentage of labor force without a job.

CPI (Consumer Price Index)

- CPI is based ona fixed basket of goods and services, whirch represents the average household's spending habits. A higher CPI indicates higher inflation, while falling CPI indicates lower inflation or even deflation.

USRealGDP

- is the inflation adjusterd measure that refl;ects the value of all goods and services produced by an economy in a given year.

---

FEATURE ENGINEERING

---

- US Real GDP has null value every 1st and 2nd month in a quarter. Therefore, forwardfill ffill() then bfill() are implemented so that each observation will have correct values.

- pct_change() will be applied to Price, Earnings, CPI and USRealGDP, while diff() will be implemented on ShllerPERatio, Treasury Rate and Unemployment Rate

- no missing values are found except for US Real GDP

- outliers are found and we leave them as they are

- MTrend categorical variable is added with values such as 'bullish', 'bearish', or 'neutral. Cutoff for bearish is less than quantile(0.4) while bullish cutoff is more than quantile(0.6). Neutral lies between the said cutoff.

---

DISTRIBUTION

---

Bearish has 360 observations.
Bullish has 360 observations.
Neutral has 360 observations.

---

RANDOM FOREST FEATURE IMPORTANCE

---

Two highest score on feature importance are SchillerPERatioDiff and EarningsDiff.

---

RANDOM FOREST CLASSIFIER ALGORITHM CLASSIFICATION REPORT FOR 2 VARIABLES

---

Accuracy is 88% for 2 vars and 87% for all diff variables
Precision, Recal, F1 Score are much improved for 2 independent variables than in all diff variable.
