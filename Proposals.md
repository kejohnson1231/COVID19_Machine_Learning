# Proposal 1 - Create a dataset and use it to study how certain factors are affecting COVID19 infection/death rates

### High Level Description

My goal for this project is to create a data set sourced from multiple websites. The data set will contain county by county information for COVID19 cases and COVID 19 deaths. It will also contain socio/economic data by county, and information about when the stay at home orders were announce and enforced. 

I plan to explore various features and how they interact with the number of cases, the number of cases per capita, and the death rate (number of deaths/number of cases). 


### Approach

<<<<<<< HEAD
First I will use scraping, APIs, githubs, to create a dataset that can be analyzed
=======
First I will have to use scraping, APIs, githubs, to create a dataset that can be analyzed
>>>>>>> 4db2e361c79a51083d92308dc1bd5bb25479a6e0

For analysis I plan to start with random forest, as that tends to work the best out of the box. I do also plan to verify that there isn't a better model for fitting the data intially. 

Once I have a baseline score, I plan to tune my model and attempt to maximize accuracy without overfitting. 

I hope to present my work in either a clean notebook or slides. 

Data would be organized by county. The features I would be interested in modeling would be things like personal income, demographics, broadband access,  distance from airports, date stay-home order announced, date stay home order enforced, health-it adoption.

<<<<<<< HEAD
The target I am most interested in is death-rate, but also open to checking out other targets listed in high level description, especially if model is more meaningful. 

=======

The target I am most interested in is death-rate, but 
>>>>>>> 4db2e361c79a51083d92308dc1bd5bb25479a6e0

### What are your data sources

I am sourcing information from the following places: 

<<<<<<< HEAD
>> CDC.gov (COVID-19 data)
>> bea.gov (personal income)
>> healthypeople.gov (healthcare data but typically not parsed by region so may have limited applicability)
>> fcc.gov (API to pull broadband data by county)
>> archives.gov/census.gov(demographic data)
>> healthit.gov (statewide adoption of health it in hospital and ambulatory settings, API also available, would need to apply to all counties in state, not sure if that's a good idea)
>> cms.gov (information about geographic requirements for telehealth reimbursements prior to COVID, potentially indicating readiness for switch to telehealth model by many healthcare providers)
>> NYtimes github (raw data sets), API also available
>> Johns Hopkins github (raw data sets), API also available
>> Kaggle (crowd-sourced data in covid discussion thread, would want to verify authenticity of data)

=======
> CDC.gov (COVID-19 data)
> bea.gov (personal income)
> healthypeople.gov (healthcare data but typically not parsed by region so may have limited applicability)
> fcc.gov (API to pull broadband data by county)
> archives.gov/census.gov(demographic data)
> healthit.gov (statewide adoption of health it in hospital and ambulatory settings, API also available, would need to apply to all counties in state, not sure if that's a good idea)
> cms.gov (information about geographic requirements for telehealth reimbursements prior to COVID, potentially indicating readiness for switch to telehealth model by many healthcare providers)
> NYtimes github (raw data sets), API also available
> Johns Hopkins github (raw data sets), API also available
> Kaggle (crowd-sourced data in covid discussion thread, would want to verify authenticity of data)
>>>>>>> 4db2e361c79a51083d92308dc1bd5bb25479a6e0




# Proposal 2 -Create a time series predicting COVID19 infections using data from the previous day

### High Level Description


### Approach


### What are your data sources



# Proposal 3 - Google searches relating to COVID19 


### High Level Description


### Approach



### What are your data sources

\
