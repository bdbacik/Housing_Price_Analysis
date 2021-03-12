# Housing Price Analysis

### Problem Statement 
* Evaluate the hypothesis that university towns have their mean housing prices less effected by economic recessions

### Project Summary
* Collected data on housing prices from Zillow, college towns from Wikipedia, and GDP from Bureau of Economic Analysis, US Department of Commerce
* Cleaned and formatted data for modeling
* Conducted t-test to evaluate hypothesis 
* Reported conclusions 

### Code and Resources Used
* Python Version: 3.8
* Packages: pandas, numpy, sklearn, matplotlib, seaborn, statsmodels, scipy

### Data Description
* From the Zillow research data site there is housing data for the United States. In particular the datafile for all homes at a city level, City_Zhvi_AllHomes.csv, has median home sale prices at a fine grained level.
* From the Wikipedia page on college towns is a list of university towns in the United States which has been copy and pasted into the file university_towns.txt.
* From Bureau of Economic Analysis, US Department of Commerce, the GDP over time of the United States in current dollars (use the chained value in 2009 dollars), in quarterly intervals, in the file gdplev.xls. For this assignment, we'll only look at GDP data from 2000 onward. 

### Data Cleaning and Exploration

Created dataframe of college towns by state from Wikipedia data
![college_towns_bar_chart](https://github.com/bdbacik/Housing_Price_Analysis/blob/main/images/college_towns_bar_chart.png)

Created dataframe with GDP by quarter from Bureau of Economic Analysis dataset, with flags for recession start, bottom, and end
![gdp by quarter](https://github.com/bdbacik/Housing_Price_Analysis/blob/main/images/gdp_by_quarter_scatter.png)

Created dataframe for housing prices by quarter using Zillow dataset, then merged with college town dataframe to classify each town as college town or not
![home prices scatter](https://github.com/bdbacik/Housing_Price_Analysis/blob/main/images/home_prices_scatterplot.png)

### Hypothesis Testing
* **Null hypothesis H0:** there is no difference between the ratio of mean housing price in university towns the quarter before the recession starts relative to the end of the recession when compared to the ratio in non-universirty towns vs. Ha there is a difference between the ratio of mean housing price in university towns compared to non university towns
* **Test statistic:** independent sample t-test statistic
* **Alpha:** 0.05 (95% confidence)
* **Decision rule:** if abs(t) > 1.96 reject H0, or if p-value < 0.05 reject H0
* **Interpretation:** if test statistic < -1.96, conclude with 95% confidence that price ratio is lower in college towns, implying prices decrease less during recession compared to non-college towns. If test statistic is > 1.96, then concluude prices decrease more in college towns.

![ttest results](https://github.com/bdbacik/Housing_Price_Analysis/blob/main/images/ttest%20results.png)

* **Conclusion:** for all three time periods during the recession, housing prices in college towns are significantly less affected compared to housing prices in non-college towns.  There is no significant relationship between college towns and housing price changes in the period leading up to the recession, or the recovery period after the recession.  With these findings we can recommend that buying a house in a college town is a good way to minimize the risk of housing price decreases during an economic recession.
