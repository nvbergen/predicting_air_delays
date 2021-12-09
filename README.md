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
|:---:|:---|:---|:---:|:---:|
| 1  | _YEAR_   | The Year of the flight   | YYYY  | Discrete  |
| 2 |  _MONTH_ | The number representation of the month  | MM  |  Discrete |
| 3  | _DAY_OF_MONTH_| The day of the month  | DD  | Discrete  |
| 4  | _DAY_OF_WEEK_  | A number representation for the day of the week Monday = 1, Sunday = 7, Unknown = 9 | N  | Discrete  |
| 5  | _FL_DATE_| Full recorded Date of the flight  | yyyy-mm-dd  | Discrete  |
| 6  | _OP_UNIQUE_CARRIER_ | Reporting Airline by Two-Letter Designator, EG AA = American Airlines.   | --  | _string_   |
| 7  | _Tail_Number_  | The identification number of the aircraft used for the flight. N831AA | --  | _string_  |
| 8  | _OP_CARRIER_FL_NUM_ |  The flight number of the reporting airline. EG 5574  | --  | _string_  |
| 9  | _Origin_   | The IATA three-letter airport code identifying the station of origin for the flight | --  | _string_  |
| 10  | _ORIGIN_CITY_NAME_ | City, ST formatted city name  | --  | _string_  |
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
