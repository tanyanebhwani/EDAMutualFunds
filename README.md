# EDAMutualFunds(Note all of this is written by me and to retain individuality,so the tone is conversational, not formal)
Exploratory Data Analysis of Mutual Funds
## Overview

I analyzed the mutual fund dataset and found the following conclusions.

### Individual Feature Analysis

Each feature was analyzed separately.

### Fund Manager

The fund manager was an individual on whom a presumption could be made — maybe an influencer of the returns made by the fund. He may even influence the asset value or size of the fund.

### Fund Size

A point I found was that the fund size was measured by its monetary value (asset value) or its age.

### Fund Category

Here, the fund category was a very important feature. Almost every important feature’s analysis was done on the basis of the category of the fund.

### Minimum SIP and Lumpsum

Now there were two really important features — Minimum SIP and Minimum Lumpsum.
Basically, SIP is the systematic investment which you pay monthly or at specific intervals for a fixed time, whereas Lumpsum is the amount you invest at once.

When we plotted histplots and boxplots (basically their distribution in space) of minimum SIP and minimum lumpsum, we found that:

Minimum SIP amounts were 0, 500, and 1000 — most funds had the same SIP values.

Lumpsum values were 0, 5000, and 10,000 — very few had 10,000 as lumpsum.

### Process of Analysis

One thing I noticed was that you analyze a feature on the basis of the entire dataset first, and then analyze it across various categories — which they have done here.

### Subcategories

They also analyzed the data across subcategories. But what I found was that category was the most important feature that served as a major distinction among the funds. Subcategories were pretty comprehensive and didn’t yield much value.

### Expense Ratio

The analysis of Expense Ratio was what I found the most interesting.

The expense ratio measures how much of a fund’s assets are used for administrative and other operating expenses. It is said that a fund’s expense ratio, if it’s less than that of its peers, is ideal.

They used a barplot of fund_size (categorical) vs expense ratio (a different bar plot for each category).
I didn’t see any clear conclusion — expense ratio was almost the same for different fund size categories. But they noticed that the Debt category had the least expense ratio, which was observed not by one graph but by combining multiple ones.

To check the distribution of data, we use histplots and boxplots. For expense ratio, both showed that most schemes had values between 0 and 1.0.

Since category was the most important column, they segregated the funds across categories and plotted boxplots for each category individually.

We found that Equity and Hybrid funds had the highest expense ratios. Usually, one would assume size could influence expense ratio, but when it didn’t show any relation, category turned out to be more relevant.

When we used rating as a segregator, we found that expense ratio was lowest for the highest-rated funds.

Then, to understand the relationship between rating and category, we used a crosstab.
It showed that most 0-rated funds were Equity funds, which explained their high expense ratio.

### Fund Size Analysis

When analyzing fund size, they first visualized its distribution, then logically analyzed it with fund age.

They didn’t find a direct correlation but saw that 10-year-old funds had the maximum size.

When analyzing fund size with rating, a direct correlation appeared — higher-rated funds had larger sizes.
Maybe this was because people were more interested in investing in higher-rated funds.

When comparing fund size with risk, people tended to invest more in high and very high risk categories.

They also looked at the cumulative fund sizes of AMCs and found that ICICI Prudential had the maximum total size.

As expected, Equity had the largest cumulative fund size, which means people invested more in equity funds.

### Fund Size and Returns

One personal observation I made was that since comparing two continuous variables can make a scatterplot complex, they converted fund size into categories (making it a categorical variable) and compared it with 5-year returns separately for each category.

### Fund Age

They analyzed fund age with category and found that Debt funds were recent while Equity funds were older.
Interestingly, the older Equity funds were low-rated but were giving the highest 5-year returns.

It made sense — funds survive on the returns they give, not necessarily on their rating.

The main question was: Does fund age affect returns?
The answer turned out to be no.

### Risk Level Analysis

We plotted a countplot of the risk categories and found that very high risk had the most funds invested in them.

To analyze AMC relationships with risk, we divided AMCs based on risk and plotted a heatmap, which showed that most AMCs had very high risk funds.

When analyzing rating vs risk, we saw that 0-rated funds had a higher concentration of high-risk funds.

Surprisingly, 0-rated funds had the highest returns, which revealed something about human psychology — we tend to be impatient with our investments. The longer we waited before withdrawal, the higher the returns.

When we plotted barplots of risk level vs returns (for 1-year, 3-year, and 5-year), we saw that 3-year and 5-year returns had a positive correlation with risk — higher the risk, higher the returns.

### Category-Wise Analysis

Interestingly, the category analysis came later, even though it was one of the most important.

Equity had the highest returns.

The most important columns in the dataset were returns, category, risk, and rating, yet their analysis appeared in the middle — this was my first insight.

EDA was done in great detail, but I realized that EDA should mainly be used in relation to the column that has to be predicted and the features dependent on it.

In the category analysis, barplots were plotted for:

Number of schemes per category

Average returns per category

We found that Equity gave the highest average return (for 1-year, 3-year, and 5-year periods).
Debt performed better for 1-year returns, but Equity outperformed others for 3 and 5 years.

Equity funds were also the oldest, and even though many of them were 0-rated, they gave high returns. I also think maybe rating is not strongly related to category because Equity funds appeared in both 0 and 5-rated categories.

### Subcategory Analysis

We further segregated subcategories based on main categories and found the best subcategory (based on returns) for the 1st, 3rd, and 5th years for each category.

### Alpha Analysis

We plotted the distribution of Alpha using a countplot.

A scatterplot of Alpha vs Returns (both continuous variables) showed that higher alpha meant higher returns.

When comparing category vs alpha, Equity again had the highest alpha.

When analyzing risk vs alpha, we found that moderately high risk (less than high or very high) had the highest alpha.

When comparing rating vs alpha, 5-rated funds had the highest alpha, followed by 0-rated funds.
This was probably because most 0-rated funds were Equity funds.

### Standard Deviation

The Standard Deviation (SD) of a stock or mutual fund represents its riskiness.
Higher SD means higher volatility, and thus, higher risk.

Using a histplot, we plotted the distribution of SD.
Using a barplot, we plotted SD across categories and found that Equity again had the highest SD — which made sense because it had the highest risk.

Higher volatility means the fund should ideally be held long-term.

The barplot of Risk Level vs SD showed a direct relationship —
“Very High Risk” had the highest SD, followed by “High,” “Moderately High,” and so on.

When we plotted Rating vs SD, we saw that 0 and 5-rated funds mostly belonged to the Equity category.

### Beta Analysis

When analyzing Beta with category, we found that Debt funds had negative beta, meaning that when the market goes down, returns for these funds increase, and vice versa.

#### Beta Variation Across Risk Level

When we analyzed beta across categories, the same pattern appeared — Debt funds had negative beta, showing that their returns rise when the market falls.

### Pairplot of Technical Metrics
I think Alpha, Beta, SD, and Sortino are more mathematical and technical characteristics. That’s why a pairplot was created between all of them to show their interrelations.

### My Overall Understanding

This EDA demonstrated how to analyze features both individually and in relation to each other.
It taught me that while many analyses can be performed, the most meaningful insights come when we relate the variables to what we aim to predict — in this case, returns.

The most influential features turned out to be returns, category, risk, and rating, and the strongest insight was that high risk combined with patience often results in higher long-term returns.


I think Alpha, Beta, SD, and Sortino are more mathematical and technical characteristics. That’s why a pairplot was created between all of them to show their interrelations.

