# COVID-19 Predictive Modeling based on Sociohealth Data


### Rationale

There is obviously a lot of global interest in the COVID-19 pandemic, and lots of data to be used.  It has been explored and modeled a lot, but this is all a fairly recent situation and there remains a lot to learn

On a more personal level, my background prior to this program was in biology and health IT. I care a lot about disparities in health related access and how that affects outcomes. which is something that’s been mentioned in COVID related reporting. 

I found the idea for this from a data set shared in the discussion for the COVID forcasting competion on Kaggle. This data set was meant to model weather data for US counties but also included sociohealth data, and I thought it would be interesting to make my own sociohealth based data set to model the pandemic. 



### Data 

Initially I gathered data by county using CDC, and Politico to create my own initial dataset to use.The Original combined sociolhealth dataset had over 400 features, so I knew I had to pare it down and clean it up quite a bit.  
When I was looking through the features I could see that there seemed to be sortable into clear categories. My goal was to make representative selections across those categories of interest and remove duplicative data 



I ended up using features from the following categories for US county: 
>**Health**  
>- Prev. hospitalization rate  
>- Age-adjusted mortality rate  
>- % adults with diabetes  
>- % obese  
>- % fair/poor health  

>**Demographic**  
>>Population   
>>Population density  
>>% each race  
>>% minority  
>>% over 65  
>>% multi-unit housing  
>>% rural  
 
>**Access**  
>>PCP rate  
>>Health cost  
>>% insured  
>>% no vehicle  
>>% limited English  
>>% disabled  
 
>**Economic**  
>>Med Household Income  
>>% below poverty line  
>>% overcrowded  
>>% unemployed  
 
>**Behavioral**  
>>% smokers  
>>% insufficient sleep  
>>% physically inactive  
  
>**Other**  
>>Segregation index  
>>Air pollution   
>>% Clinton voters  
>>% Trump voters  
 
 
### Plan 

My initial plan was to use the above features, along with my target variable (data from the New York Times) to calculate cummulative deaths divided by cummulative cases per county. I tried this model with a Random Forest Regressor with different feature combinations but the score was always either negative or very small. A linear regression model performed slightly better but not by much, so I decided to see if I could pivot to get a working model. 

So I made some updates:

For features – I pulled data for stay at home orders. So the dates they were announced, effective, lifted or scheduled to be lifted, and also the dates states started to reopen businesses. Used time deltas to featurize this data for the model. I also created some data sets from the johns Hopkins github which has case and death metadata posted daily. I wrote the code to pull from the github so that it would always update with the latest day available. 

For Targets - I used some of the johns Hopkins data to create a new target, which was whether the active number of cases had increased since the day prior. 

Because I changed my target, I was also able to also change my model from a random forest regressor to a random forest classifier 


### Analysis and Results

Initially I ran the random forest classifier using just new feature data, to see a baseline for how it performed without any sociohealth data, the accuracy was running around 67%. 

When I added a few of the sociohealth features to the model, based of what I suspected to be most informative (both intuitively and based on feature importance in the first iteration of the model),the accuracy improved by over 10%. I tested with different combinations of features, but the model accuracy mostly stayed pretty close to 78% accuracy (although precision and recall were more variable based on which features I used). 

I also tested how the model would perform if I  threw in all the rest of the sociohealth features from the initial test, and 
it remained at about 78% accuracy. 


### Additional Takeaways

Initial model wasn’t great at predicting the death rate, but that in itself is still informative

I tried to see if I could improve the model beyond hyperparameter tuning, which wasn’t too consistently effective. Since I had months of time series data from johns Hopkins, I tested adding features for things like whether the previous day had seen an increase in active cases from the day prior to it, or whether there had been any new confirmed cases added for that county during the previous week. None of that data improved the model. 

Third point here is that, I ran gini importance and permutation importance every time I ran my model, the rankings were mostly pretty inconsistent, which seemed to indicate a relatedness or redundancy of the features I was using. As a group they improve the model, but it’s not really necessary to use all of them. 



### Future Steps 



I like the idea of adding more features to the model to see if it can be improved:

- I had some data that I had scraped but never included, like broadband access data from the fcc and ehr meaningful use data from Healthit.gov
- I also think it would be interesting to see how certain google searches might be predictive of cases  
> - With telemedicine readiness, prior to covid, telemedicine was only covered in certain regional situations, I think it would be interesting to infer how ready they were to accommodate a switch to telehealth and determine how that affects the model  
> - I theoretically had enough data to determine how far each county was from the closest airport, but I didn’t have the time budget to do that during this week  
> - Weather data was a big part of the data set I used for inspiration, so I'd be curious to see how it could affect themodel

I also think it would be cool to use the time series data to predict the cases for the next day



### Technology and Sources: 

Python, Jupyter, AWS, VGG16, scikit-learn, Tensorflow, Matplotlib, Pandas, Numpy, Selenium, instagram-scraper









