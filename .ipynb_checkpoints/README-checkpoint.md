# Airline Delay Prediction and Analysis.
## Capstone project on predicing an airline delay from a point of origin. 
---
##### Nicholas Van Bergen <br> General Assembly Data Science Immersive <br> Cohort 0927-Remote

# Airline Delay Prediction and Analysis, Executive Summary:

### Problem statement:
Anyone who has traveled by air knows that delays can be frustrating and costly to the customer. 

This project will attempt to predict a delay and a delay's duration in an air travel itinerary and further attempt to ascribe a possible cost to that delay. 
 
Hopefully, this will empower consumers with a bit more inforamtion if their trip will be 'smooth sailing' or a 'disaster' from a customer standpoint.  

### Solution:
Starting with 35+million observations, I used a gradient descent algorithm (_XGBoost_) and was able to improve our predictive `accuracy` over the null model by 13% and our baseline model by 4%.   

### Results:
* `Null model` is one were we would randomly guess if there is a delay. Since the classes of delay vs not delayed were 50/50 in composition we can say that we have an accuracy of 50%. 
* `XGBoost baseline` was computed using 'out of the box' hyperparameters and the metrics shown below are pulled from those predictions made on that model. 
* `XGBoost tuned` was computed on hyperparameter settings tuned using a gridsearch.

| **Metric**| **_Null Model_**|**XGBoost Baseline Predictions**| **XGBoost Tuned Predictions**| $$\Delta$$ Baseline - Tuned| $$\Delta$$ Null-Tuned|  
| :--------- |:-----------: | :---------:| :---:| :-------:|:---------------:|
| **Accuracy**| 0.50| 0.59 | 0.63 |0.04| 0.13 |
|**Recall**| \---| 0.62 | 0.66  | 0.04 | \--- |
|**Precision**| \---| 0.60 | 0.63 | 0.03 | \--- |
|**F1**| \---| 0.60 | 0.64 | 0.04| \--- |
|**ROC AUC**| \---| 0.59 | 0.63 | 0.04 | \--- |


### Conclusion
The prototype mvp has been promising. Additional tuning of the model and testing should be completed to improve model accuracy and reduce Type One errors from the testing and training data. 

The ultimate goal of this project is to have an app that is viewable and useable based on the trained model data. The model should need, as I imagine it, monthly maitenence as new delay data is release from BTS.

Our mvp product is the first step to such a useful and helpful customer friendly tool. 


## Folder structure:
### Code
1. Data intake & cleaning. 
2. EDA
3. Data Modeling Training and Testing
4. ~Data predictions/app output~ 
* An app of this prediction tool is still under development as of this writing 23 December, 2021.

### Data Folder
Due to virtual hosting resource limitations. The dataset used on the repository will be a randomized sampling of the original _all flights_ file noted in the notebook. You can still use the smaller subsample as the beginning to go through the entire notebook end to end to proceed and reproduce results. 

**Please use the `sampled_all_flights.csv` file** to proceed through the notebooks. 


### Presentation Folder
A slide deck showing the results of this research is located here. A collection of un-anotated charts and figures are located here as well.

---
## Summary of sources and data dictionary

## Data Sources
All data obtained by download of CSV files from the Bureau of Transportation Statistics ([BTS]('https://www.transtats.bts.gov/DL_SelectFields.asp?gnoyr_VQ=FGJ')). Follow the link above for access to the data portal. 

This section has two parts, the description and the dictionary. 
- The _Description_ talks about the dataset in general terms while the dictionary provides a macro-level understanding of the data types and organization of the data in our dataframe. 

### Data Description
Having obtained 65 complete months of daily flights in the North American air system, I compiled the baseline table by joining all 65 data tables together for more that _34,409,230_ million rows of labeled data.

The data was then sorted by delay or not delayed and then sampled to generate an even split of a randomized sampling. This was still far too many rows so the sample was save and resampled to something more manageable. 

This setup allows us to be able to conduct a binary classification task. That is, will there be a delay or not. 

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
| 22  | _Cancelled_  | Describes if the flight had been canceled 0 for not-canceled, 1 for canceled.  | _integer_  | categorical  |
| 23  | _CancellationCode_  | Describes the type of cancellation with encoded values.  | _string_  | categorical  |
| 24  | _Diverted_  | Describes the diverted status of the flight. 1 was diverted and 0 not diverted  | _integer_  | categorical  |
| 25  | _Distance_  | Measures the total distance flown from origin to destination in miles.  | _float_   | discrete  |
| 26  | _CarrierDelay_  | Measures the total amount of time spent on a delay that is attributed to a controllable reason for the airline   | _integer_  | discrete  |
| 27  | _WeatherDelay_  | Measures the total amount of time spent on a delay that is attributed by weather/environmental reasons  | _float_  | discrete  |
| 28  | _NASDelay_  | Measures the total amount of time spent on a delay that is attributed by Air Traffic Control (ATC) reasons  | _float_  | discrete  |
| 29  | _SecurityDelay_  | Measures the total amount of time spent on a delay that is attributed to security zone issues (long lines at screening areas or delay for law enforcement activity in airport)   | _float_  | discrete   |
| 30  | _LateAircraftDelay_  | Measures the total amount of time spent on a delay that is attributed the aircraft's late arrival.   | _float_  | discrete   |


