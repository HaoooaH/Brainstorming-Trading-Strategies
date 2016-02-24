#Brainstorming Trading Strategies

A list of resource for generating trading strategy.  
If you want to add or change anything, feel free to send me a pull request.   
If you find any error or mistake, feel free to send me a pull request too.   

Thanks!

## Table of Contents

<!-- MarkdownTOC depth=4 -->
- [Generate Hypothesis](#GenerateHypothesis)
- [Feature Transformation](#FeatureTransformation)
- [Exploratory Data Analysis](#ExploratoryDataAnalysis)
- [What to Investigate](#WhattoInvestigate)
- [Model Selection](#ModelSelection)
- [Parameter and Feature Selection](#ParameterandFeatureSelection)
- [Credits](#credits)

<!-- /MarkdownTOC -->

<a name="GenerateHypothesis" />
## Generate Hypothesis 
Resources for generating hypotheses or explain data observation.

### Market Behavior
**Behavioural Finance**: http://www.behaviouralfinance.net/

### News and Event
**Features**:   
1.NGrams (keywords, tags)  
Example. N Gram of wording difference [WSJ Fed Statement Tracker](http://projects.wsj.com/fed-statement-tracker)  
2.Entity  
3.Relevance Score  
4.Novelty Score  
5.Sentiment Score   

### Economic Indicator and Index
[List of Economic Indicators](http://www.tradingeconomics.com/indicators)

### Third Party API Data   
**Features**:      
1.Supply     
2.Demand    
3.Sales  
4.Inventory  
5.Price Change  
6.Job Posting (Linkedin API)  
7.Traffic  
8.Google Trend   
9.Social Networks (Reddit)   
10.Technology Trend (Github, Stackoverflow, NSF)  

<a name="FeatureTransformation" />
#### Feature Transformation / Extraction  
Goal: Minimize information loss, increase model performance     

**Sign**    
+1 for BUY, -1 for SELL    

[**Log and Exponetial**](http://people.duke.edu/~rnau/411log.htm)    


**Dispersion**:      
1.Standard deviation      
2.Range (Max - Min, OHLC)      
3.Average deviation      
4.Variance      
5.Difference    

**Data Regrouping**    
1. Aggreate (useful when dealing with sparse data)      
2. Split      
3. Combine    

**Ratio**    

**Rates of Change**    
1.Speed    
2.Acceleration  

**Time**
1.Time Shift (Leading/Lagging)   
2.Time Bucket (Slice time window)    
3.Window  

**Average**     
1. Mean (useful data intropolation)    
2. [Moving Average](http://people.duke.edu/~rnau/Notes_on_forecasting_with_moving_averages--Robert_Nau.pdf)    

**Sum**  
1.Count  
2.Culmative Sum  
3.Weighted Sum  
4.Count of distinct value  

[**Convert to Technical Indicators**](http://mrjbq7.github.io/ta-lib/)    

**Logic Operation**    
1.AND (Union)      
2.OR (Intersection)    
3.XOR (Exclusive)      
4.NOT (Inverse)    
	
**Rule**  
1.Inequitilites    

**Rank**  

**Scale and Projection**    
1.Projection    
2.Scale    
3.Normalization(Certain model is sensetive to scale)    

**Density and Intensity**    
1.Average Intensity    
2.Power Transform    
3.Square Root    

[**Numerical Transform**](http://www.sympy.org/en/features.html)    

**Sampling**    

**Regulazartion (For overfitting)**   


<a name="ExploratoryDataAnalysis" />    
#### Exploratory Data Analysis

**Network  Minning**[http://www.cl.cam.ac.uk/~cm542/teaching/2011/stna-pdfs/stna-lecture11.pdf
](http://www.cl.cam.ac.uk/~cm542/teaching/2011/stna-pdfs/stna-lecture11.pdf
)  

**Distribution**   
Distribution of features may change after feature engineering  
1. Check shape (example. Variance Skewness Kurtosis Moments)  
2. Descriptive Statistics: Mode Median  
  
**Association/Cocurrence**    
[Association Rule Minning](http://en.wikipedia.org/wiki/Association_rule_learning)  

**Regression**  

**Anomaly Detection**  
1.Clustering  
2.Z-Score / Standard Deviation  
3.Nearest Neighbour (example: Local outlier factor)  
4.Range,Measures of Variation   
5.Quartile  
6.Distance and Density  
7.Percentage Threshold  

**Clustering**  
1.DBSCAN/KNN  

**Statistical Properties**  
1.Stable  
2.[Stationary](http://people.duke.edu/~rnau/411diff.htm)  
3.Causal  
4.Linear  
5.Cointegration  

**Energy and Density**  
[Spectral Density](https://onlinecourses.science.psu.edu/stat510/node/80)  

**Measure of Information**  
1.Informatin Gain  
2.Information Entropy (Measure of Disorder)  

**Filter**    
Low amplititude may be noise  
1.[Choose filter](http://zone.ni.com/reference/en-XX/help/371268J-01/expresswb/filter/)  
2.[Filtering in Finnace](http://www.cis.upenn.edu/~mkearns/finread/filtering_in_finance.pdf)  
3.Wavelet Decomposition  

**Reduce Dimensionality (Denoise)**  

**Factor Analysis**  

**Similarity Analysis**  
1.Euclidean Distance  
2.Manhattan Distance 
3.Chebyshev Distance   
4.Minkowski Distance  
5.Standardized Euclidean Distance  
6.Mahalanobis Distance  
7.Cosine Distance  
8.Hamming Distance  
9.Jaccard Similarity Coefficient  
10.Correlation Coefficient / Correlation Distance / Cross Correlation  

**Discrinmant Analysis**  
1.LDA  

**Independence**  

**Limit / Bound**  

<a name="WhattoInvestigate" />  
## What to Investigate  

What to predict for model. For example, rather than predict price, we can predict change of price. If it is a binary labels for predication model, then need to check positive / negative labels imbalance.  

### Price
1.Bid/Ask/Mid (Average, Percent, Range)  
2.Deviation from mid price    (+1/-1)(+1 Buyer Driven -1 Seller Driven)  
3.Trend: Open - Close  
4.Peak to peak width and depth  
5.Relative Value  
6.Spread with yielf curve  
7.VWAP  
8.Gap Price. Price between period N and current price.   P(t)-P(t-N). For example, current price different from price 5 points ago  
9.Best Bid vs. Best Ask  
	a. Best Bid(t+delta) > Best Ask(t) => Price Spread Upward  
	b. Best Ask(t+detla) < Best Bid(t) => Price Spread Downward  


###Holding time  
Executation cost is a function of holding time and filled quantity, need to minimize this function  
[The Execution Puzzle: How and When to Trade to Minimize Cost](http://faculty.baruch.cuny.edu/jgatheral/campos2011.pdf)  

### Yield  
1.Yield Curve  

###Volume  
1.Balance: Bid volume > Sale Volume?  

### Volatility   
Volatility of Price / Volume /Return   

### Liquidity  
1.Breadth: Bid - Ask     
2.Depth: Number of orders at each price level    
	Price increase only happen after all the bid depth at a given level is exhausted.    
	So if P_bid(t)>P_bid(t-1), mor people try to buy, price less likely go down  
3.Elastic: Inter order price difference P(t+1) - P(t)  
4.Rates of change: Number of quotes/trades over period of time    
5.Share turnover  
6.[Variance Ratio](http://arxiv.org/pdf/1112.6169.pdf)  

### Order  
1. Number of transactions  

### Spread  
1.Tick Movement  
2.Effective Spread,Realized Spread   [http://www.cambridge.org/us/download_file/204487/](http://www.cambridge.org/us/download_file/204487/)  

###Direction  
Direction: Up or Down  

###Ratio  
Put/Call Ratio  

<a name="ModelSelection" />  
## Model Selection  
1.[**Scikit-Learn: Choosing the Right Estimator**](http://scikit-learn.org/dev/tutorial/machine_learning_map/index.html)
2.[**Choosing the Correct Statistical Test**](http://bama.ua.edu/~jleeper/627/choosestat.html)
3.[**Steps for choosing a timeseries model**](http://people.duke.edu/~rnau/411fcst.htm)  
![TimeSeries](http://people.duke.edu/~rnau/411flow.gif)  
4. [**Timeseries Analysis using Statsmodel**](http://conference.scipy.org/proceedings/scipy2011/pdfs/statsmodels.pdf)  
5. [**Machine Learning Guide**](https://github.com/soulmachine/machine-learning-cheat-sheet/raw/master/machine-learning-cheat-sheet.pdf)  
6. [**Machine Learning Algorithm Computation Complexity**](http://eferm.com/wp-content/uploads/2011/05/cheat3.pdf)  
7. [**Optimization and Root Finding**](http://docs.scipy.org/doc/scipy/reference/optimize.html)  
8. [**Neural Network Forcasting Finnnicial Time Series](http://www.cs.cmu.edu/afs/cs/academic/class/15782-f06/slides/timeseries.pdf)  

<a name="ParameterandFeatureSelection" />  
## Parameter and Feature Selection  
1.[**Scikit Learn Grid Search**](http://scikit-learn.org/stable/modules/grid_search.html
)  
2.[**Scikit Learn's Feature Selection Feature**](http://scikit-learn.org/stable/modules/feature_selection.html)  

<a name="credits" />
## Credits
