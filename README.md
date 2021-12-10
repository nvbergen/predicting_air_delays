# Airline Delay Prediction and Analysis
 Capstone project on predicing an airline delay from a point of origin. 
 
 ## Problem statement:
 Anyone who has traveled by air knows that delays can be frustrating and costly to the customer. 
 This project will attempt to predict a delay and a delay's duration in an air travel itinerary and further attempt to ascribe a possible cost to that delay. 
 Hopefully, this will empower consumers with a bit more inforamtion if their trip will be 'smooth sailing' or a 'disaster' from a customer standpoint. 

## Folder structure:
### Code
1. Data intake, cleaning and EDA. 
2. EDA
3. Data Modeling Trainning and Testing
4. Data predictions/app output
<br>
### Data
The single CSV containing 68 months of raw flight data. 

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

This section has two parts, the description and the dictionary. 
- The _Description_ talks about the dataset in general terms while the dictionary provides a macro-level understanding of the data types and organization of the data in our dataframe. 
### Data Description
Having obtained 65 complete months of daily flights in the North American air system, I compiled the baseline table by joining all 65 data tables together for more that _blank!!!!!!!!!!!!!!!!!_ million rows of labeled data.

### Data Dictionary
Below is a table of each column in the dataset. 
| No.  | **Column** | **Description**  | **Units**  | **Type**  |
|:---:|:---|:---|:---:|:---:|
| 1  | _YEAR_   | The Year of the flight YYYY format  | _integer_  | categorical |
| 2 |  _MONTH_ | The number representation of the month MM | _integer_  | categorical |
| 3  | _DAY_OF_MONTH_| The day of the month dd format |  _integer_ | categorical  |
| 4  | _DAY_OF_WEEK_  | A number representation for the day of the week Monday = 1, Sunday = 7, Unknown = 9 | _integer_  | categorical  |
| 5  | _FL_DATE_| Full recorded Date of the flight yyyy-mm-dd | _string_ | categorical  |
| 6  | _OP_UNIQUE_CARRIER_ | Reporting Airline by Two-Letter Designator, EG AA = American Airlines.   | _string_ | categorical |
| 7  | _Tail_Number_  | The identification number of the aircraft used for the flight. N831AA | _string_ | categorical |
| 8  | _OP_CARRIER_FL_NUM_ |  The flight number of the reporting airline. EG 5574  | _string_ | categorical |
| 9  | _Origin_   | The IATA three-letter airport code identifying the station of origin for the flight. EG _SYD_ | _string_ | categorical |
| 10  | _ORIGIN_CITY_NAME_ | City, ST. formatted city name of the _origin_ airport | _string_ | categorical |
| 11  | _DEST_  | The IATA three-letter airport code identifying the station of origin for the flight. EG _SFO_ | _string_ | categorical |
| 12  | _DEST_CITY_NAME_  | City, ST. formatted city name of the _destination_ airport  | _string_ | categorical |
| 13  | _CRS_DEP_TIME_  | **Scheduled departure time** stored as an integer, 11:52 pm is 2352  | _integer_  | categorical  |
| 14  | _DEP_TIME_  | _Actual_ departure time recorded at airport and stored as a float. 7:13 pm is 1913.0  | _float_  | categorical  |
| 15  | _DEP_DELAY_  | Total time in minutes measured as difference between CRS_DEP_TIME and DEP_TIME  | _integer_  | discrete  |
| 16  | _CRS_ARR_TIME_  | **Scheduled arrival time** stored as an integer, 07:52 pm is 1952  | _integer_  | categorical  |  
| 17  | _ARR_TIME_  | _Actual_ arrival time recorded at airport and stored as a float. 7:13 pm is 1913.0  | _float_  | categorical  |
| 18  | _ARR_DELAY_  | Total time in minutes measured as difference between CRS_ARR_TIME and ARR_TIME  | _integer_  | discrete  |
| 19  | _CANCELLED_  |  Binary designator if the flight was canceled | _binary int_  | categorical  |
| 20  | _CANCELLATION_CODE_  | Description that with Cancellation _reason_ represented by letter code A - G  | _string_  | categorical  |
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
