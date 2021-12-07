# Airline Delay Prediction and Analysis
 Capstone project on predicing an airline delay from a point of origin. 
 
 ## Problem statement:
 Anyone who has traveled by air knows that delays can be frustrating and costly to the customer. 
 This project will attempt to predict a delay and a delay's duration in an air travel itinerary and further attempt to ascribe a possible cost to that delay. 
 Hopefully, this will empower consumers with a bit more inforamtion if their trip will be 'smooth sailing' or a 'disaster' from a customer standpoint. 

## Folder structure:
1. Data and Data Cleaning. 
2. EDA
3. Data Modeling Trainning and Testing
4. Data predictions/app output
---
## Project Milestones
1. Initial data acquisition
    1. Application to APIs
    - [Amadeus](https://developers.amadeus.com/self-service/category/air)
    - [Bureau of Transportaion Statistics](https://www.transtats.bts.gov/DL_SelectFields.asp?gnoyr_VQ=FGJ)
2. Data Dictionary Document
3. Join of of all tables in dataset and cleaning.
4. Exploratory of the final frame.
    - Should the model be interpretable? 
    - What specific metrics will be used at each level of modeling?
    - Should this be a time series analysis or a feature?
    - Should WX be a feature in the analysis?
    - Consider *scaling* to dollar per mile.
5. Level 1 classification; Delay probability. 
6. Level 2 regression; determining how long a delay will be and applying a cost per minute figure to data
