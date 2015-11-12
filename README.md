# Oliver Arnold Bathing Water Quality API
## Data Representation and Querying Project 2015
### Oliver Arnold

## Introduction
This API project includes all the documentation and design for the "Bathing Water Quality" dataset from the Fingal County Council, found [here](https://data.gov.ie/dataset/bathing-water-quality).

## About the data
This dataset was received in Comma Separated Values (CSV) format, and was downloaded from [*Bathing Water Quality*](http://data.fingal.ie/datasets/csv/BathingWaterQuality2013.csv).
The dataset describes the results of studies taken of water found at various beaches, and it's quality to bathe in.
100mls were taken from each location, and brought to a lab. The samples were tested for E-Coli and Enterococci.
The CSV file contains 97 rows, the first row is however, a header row, detailing which information falls
into the each column of the dataset.

The header and a sample first few rows look like this:
```
Beach,Date,E_Coli,Enterococci
Balbriggan,22/05/2013,63,9
Donabate,22/05/2013,10,1
Howth - Claremont,22/05/2013,10,1

```
There are four values on each line, which are as follows:

Type  | Description 
------------- | -------------
**Beach** |  The beach location that the water was tested.
**Date**  | The date that the water was tested.
**E-Coli**  | The Amount of E-Coli that was found in the 100ml sample of water taken.
**Enterococci**  | The Amount of Enterococci that was found in the 100ml sample of water taken.


## List of E-Coli at a given beach
To list the amount of E-Coli at a given beach using the GET method at the following URL:
*http://beachSafetyAPI/[Beach]/eColi*
where you replace [beach] with the requested beach.
As an example, this URL:
*http://beachSafetyAPI/Skerries/eColi*
will return a number which represents the amount of E-Coli found in the tested sample
The data will be returned in JSON format, with the following properties for each selected Beach:
    - *Beach*: The requested Beach
    - *E-Coli*: the Amount of the E-Coli found in the tested sample.
    
An example of a response would be:

```
JSON:
[
  {
    "Beach":"Balbriggan",
    "E_Coli":63,
  }
]
```
