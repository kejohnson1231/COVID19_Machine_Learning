# COVID-19 Predictive Modeling based on Sociohealth Data


### Rationale

There is obviously a lot of global interest in the COVID-19 pandemic, and lots of data to be used.  It has been explored and modeled a lot, but this is all a fairly recent situation and there remains a lot to learn

On a more personal level, my background prior to this program was in biology and health IT. I care a lot about disparities in health related access and how that affects outcomes. which is something that’s been mentioned in COVID related reporting. 

I found the idea for this from a data set shared in the discussion for the COVID forcasting competion on Kaggle. This data set was meant to model weather data for US counties but also included sociohealth data, and I thought it would be interesting to make my own sociohealth based data set to model the pandemic. 



### Data 

Gathered data by county using CDC, Politico, and various other sites (for shutdown orders) to create my own initial dataset to use.The Original combined sociolhealth dataset had over 400 features, so I knew I had to pare it down and clean it up quite a bit.  
When I was looking through the features I could see that there seemed to be sortable into clear categories. My goal was to make representative selections across those categories of interest and remove duplicative data 



I ended up using features from the following categories for US county: 
>Health  
*Prev. hospitalization rate
*Age-adjusted mortality rate
*% adults with diabetes
*% obese
*% fair/poor health

>Demographic
*Population 
*Population density
*% each race
*% minority
*% over 65
*% multi-unit housing
*% rural

>Access
*PCP rate
*Health cost
*% insured
*% no vehicle
*% limited English
*% disabled

Economic
Med Household Income
% below poverty line
% overcrowded
% unemployed

Behavioral
% smokers
% insufficient sleep
% physically inactive

Other
Segregation index
Air pollution
% Clinton voters
% Trump voters
Shutdown data
 
### Plan 

My goal was to create a model that can be used to predict the popularity of Instagram posts. In this first phase of the project, I wanted to determine whether the content of an instagram photo, analyzed with a convolutional neural network, could be used to predict whether a post would receive a certain threshold of engagement (number of likes divided by number of followers). 




### Analysis

The first step in my analysis was to try to use a pretrained CNN, but I ran into various issues with applicability. 

Since I couldn’t use fully pre-trained CNN,  and with time constraints I couldn’t build my own from scratch, I decided to use a partially pretrained model. 

I took a pretrained model VGG16 which has multiple layers – picking up different aspects of the image. I froze most of the pretrained layers, and then trained the last layers, the dense layers, on my data to see if it could successfully predict which images received higher levels of engagement (like count/follower count > 5%). 


### Results

In this first phase of the project I was able to get consistent predictions at 65% accuracy or greater. 


Over time I could train more layers and adjust parameters to improve that, but for now I was satisfied that there seemed to be at least some association between image content and engagement, and that gave me the confidence to keep moving forward on this project in the future


### Future Steps 

In future phases, I would like to:
  
> *Create a fully-trained CNN  from scratch,  which would be very time intensive project. See how it compared to the alt text provided by Instagram.  
> *Take image probabilities, captions parsed with natural language processing, datetime of posts, hashtags, and other captured elements and feed that all into a classification model, to better drill down which features are predictive of an engaging post.   
> *Create a flask app upload a potential post and it could tell you, based on the model, whether it was expected to meet or surpass an engagement threshold  



### Technology and Sources: 

Python, Jupyter, AWS, VGG16, scikit-learn, Tensorflow, Matplotlib, Pandas, Numpy, Selenium, instagram-scraper









