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
---
## Data
---
This section has two parts, the description and the dictionary. 
- The _Description_ talks about the dataset in general terms while the dictionary provides a macro-level understanding of the data types and organization of the data in our dataframe. 
### Data Description


### Data Dictionary
Below is a table of each column in the dataset. 
| No.  | **Column** | **Description**  | **Units**  | **Type**  |
|:---:|:---|:---|:---|:---|
| 1  | Year   | The Year of the flight   | YYYY  | Discrete  |
| 2 |  Month | The number representation of the month  | MM  |  Discrete |
| 3  | Day of Month  | The day of the month  | DD  | Discrete  |
| 4  | Day of Week  | A number representation for the day of the week Monday = 1, Sunday = 7 | N  | Discrete  |
| 5  | Flight Date (yyyymmdd)  |   |   |   |
| 6  | Reporting Airline |   |   |   |
| 7  | Tail_Number  |   |   |   |
| 8  | Flight_Number_Reporting_Airline   |   |   |   |
| 9  | Origin   |   |   |   |
| 10  | OriginCityName   |   |   |   |
| 11  | OriginStateName  |   |   |   |
| 12  | DEST  |   |   |   |
| 13  | DestCityName  |   |   |   |
| 14  | DestStateName  |   |   |   |
| 15  | CRSDepTime  |   |   |   |
| 16  | DepTime  |   |   |   |
| 17  | DepDelay  |   |   |   |
| 18  | DepDelayMinutes  |   |   |   |
| 19  | CRSArrTime  |   |   |   |
| 20  | ArrTime  |   |   |   |
| 21  | ArrDelay  |   |   |   |
| 22  | ArrDelayMinutes  |   |   |   |
| 23  | Cancelled  |   |   |   |
| 24  | CancellationCode  |   |   |   |
| 25  | Diverted  |   |   |   |
| 26  | CRSElapsedTime  |   |   |   |
| 27  | Flights  |   |   |   |
| 28  | Distance  |   |   |   |
| 29  | CarrierDelay  |   |   |   |
| 30  | WeatherDelay  |   |   |   |
| 31  | NASDelay  |   |   |   |
| 32  | SecurityDelay  |   |   |   |
| 33  | LateAircraftDelay  |   |   |   |
| 34  |   |   |   |   |
