# Capstone-Project-
DSI19

## Section 1: Problem statement

### Part 1.1: The context of the problem

W
### Part 1.2: The goal of this project



### Part 1.3: Evaluation metrics



## Section 2: Notebooks in this project


## Section 3: Datasets and data dictionaries



|**Index**|**Feature Name**|**Description**|
|---|---|---|
|1|Station|The station that measured that row of data|
|2|Date|Date in DD/M/YYYY|
|---|---|---|
|3|Tmax|Max temperature in Fahrenheit|
|4|Tmin|Minimum temperature in Fahrenheit|
|5|Tavg|Average temperature in Fahrenheit|
|6|Depart|Departure from normal temperature. This is not recorded by station 2|
|7|DewPoint|Average dew point|
|8|WetBulb|Average wet bulb|
|---|---|---|
|---|---|Degree Days: Base of 65 F|
|9|Heat|Heating (Season begins with July), quantifies the demand for energy needed to heat a building|
|10|Cool|Cooling (Seasson begins with January), quantifies demand for air conditioning.|
|11|Sunrise|Calculated sunrise|
|12|Sunset|Calculated sunset|
|---|---|---|
|13|CodeSum|Code of weather phenomena, such as Haze (HZ) or Mist (BR)|
|14|Depth|Depth of snow/ice on ground|
|15|Water1|Depth of water on ground|
|16|SnowFall|Snowfall in inches|
|17|PrecipTotal|Total amount of rainfall (precipitation)|
|---|---|---|
|18|StnPressure|Average station pressure|
|19|SeaLevel|Average sea level pressure|
|---|---|---|
|20|ResultSpeed|Resultant wind speed in miles per hour|
|21|ResultDir|Resultant wind direction in tens of degrees (whole degrees)|
|22|AvgSpeed|Average wind speed in miles per hour|




|Index|Feature Name|Description|
|---|---|---|
|1|Id|The id of the record|
|2|Date|Date that the WNV test is performed|
|3|Address|Approximate address of the location of the trap. This isused to send to the GeoCoder|
|4|Species|The speices of mosquitos|
|5|Block|Block number of address|
|---|---|---|
|6|Street|Street name|
|7|Trap|Id of the trap|
|8|AddressNumberAndStreet|Approximate address returned from GeoCoder|
|9|Latitude|The Latitude returned from Geocoder|
|10|Longitude|The Longitude returned from Geocoder|
|---|---|---|
|11|AddressAccuracy|Accuracy returned from GeoCoder|
|12|NumMosquitos|Number of mosquitoes caught in that trap|
|13|WnvPresent|Whether WNV was present in these mosquitos. 1 means WNV is present, and 0 means not present. **This is the label**|



## Section 4: Production Model and Analysis

### Part 4.1: The final production model

The final production model was an Adaboost model. The model had achieved a score of 73% on the training set and 72% on the test set, meaning that it had some bias, but quite a low variance. This means that it generalised well. This is compared to some other models we tested, including: 

- Logistic Regression
- K-Nearest neighbors
- Random Forest
- Support Vector Machine
- Adaboost (final production model)

The other models obtained really high training scores of more than 90%, but scored around 60-70% on the test set. This means that these models had low bias, but really high variance. This is one reason why we chose the higher biased Adaboost model, because of the generalisability.

