# Airline Delay Prediction and Analysis
 Capstone project on predicing an airline delay from a point of origin. 
 
 ## Problem statement:
 Anyone who has traveled by air knows that delays can be frustrating and costly to the customer. 
 This project will attempt to predict a delay and a delay's duration in an air travel itinerary and further attempt to ascribe a possible cost to that delay. 
 Hopefully, this will empower consumers with a bit more inforamtion if their trip will be 'smooth sailing' or a 'disaster' from a customer standpoint. 

## Folder structure:
### Code
1. Data intake & cleaning. 
2. EDA
3. Data Modeling Trainning and Testing
4. ~Data predictions/app output~ 
* An app of this prediction tool is still under development as of this writing 23 December, 2021.

### Data
Due to virtual hosting resource limitations. The dataset used on the repo will be a randomized sampling of the original _all flights_ file. 
To proceed and reproduce results. 

**Please use the `sampled_all_flights.csv` file** to proceed through the notebooks. 


### Presentation
A slide deck showing the results of this research is located here. A collection of un-anotated charts and figures are located here as well. 

---

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
| 21  | _Arr_Delay_  | Measures the number of minutes delayed. This is a focus metric that is used for the entire project. |    _integer_ | discrete  |
| 22  | _ArrDelayMinutes_  | Measures the number  |   |   |
| 23  | _Cancelled_  |   |   |   |
| 24  | _CancellationCode_  |   |   |   |
| 25  | _Diverted_  |   |   |   |
| 26  | _CRSElapsedTime_  |   |   |   |
| 27  | _Flights_  |   |   |   |
| 28  | _Distance_  |   |   |   |
| 29  | _CarrierDelay_  |   |   |   |
| 30  | _WeatherDelay_  |   |   |   |
| 31  | _NASDelay_  |   |   |   |
| 32  | _SecurityDelay_  |   |   |   |
| 33  | _LateAircraftDelay_  |   |   |   |
| 34  |   |   |   |   |
