# Chicago Vehicle Saftey: 
## Traffic Accident Injury Detection & Reduction
**Author**: Ashli Dougherty 

## Overview
A one-paragraph overview of the project, including the business problem, data, methods, results and recommendations.

*** 
## Business Problem
Last year there were 132,967 documented traffic accidents in the city of Chicago. Approximately 20% of all accidents resulted in one or more people injured for a total of 26,593 injuries. The Chicago Department of Transportation is currently working together with [Vision Zero](https://www.chicago.gov/city/en/depts/cdot/supp_info/vision-zero-chicago.html) on a plan to eliminate ALL injuries and fatalities whether your mode of transportation is your personal vehicle, public transit, cycling, or walking. 

As a partner with these two institutions I used historical crash data in order to make our city a safer place for all those who live, work, and vacation here. My approach to this problem was to build a machine learning model that would: 
1. Predict if an injury would be present at an accident site based on a variety of factors.
2. Determine which factors increase the probability of an injury being present. 

The city can then use the identified factors as a starting point for improvements that can increase citizen safety. 
***

## Data
There are three datasets on the City of Chicago's [open data website](https://data.cityofchicago.org/browse?category=Transportation). Based on the site all three data sets are meant to be used in combination with one another. Datasets are very large and were accessed locally in order to bypass Git's Large File Storage systems. All CSVs can be accessed and downloaded from the website.  

I used the following datasets: 
- [Crashes Dataset](https://data.cityofchicago.org/Transportation/Traffic-Crashes-Crashes/85ca-t3if): Crash data shows information about each traffic crash on city streets within the City of Chicago limits and under the jurisdiction of Chicago Police Department (CPD).
- [Vehicles Dataset](https://data.cityofchicago.org/Transportation/Traffic-Crashes-Vehicles/68nd-jvt3): This dataset contains information about vehicles (or units as they are identified in crash reports) involved in a traffic crash.
- [People Dataset](https://data.cityofchicago.org/Transportation/Traffic-Crashes-People/u6pd-qa9d): This data contains information about people involved in a crash and if any injuries were sustained.

Only incidents from the calendar year 2021 will be analyzed as it is the last complete year on record. The number of reports is less than 2018 and 2019 but more than 2020 which indicates that people are driving/using transportation more since the pandemic. 

***

## Modeling
After cleaning the data the following features were included in the model:
- POSTED_SPEED_LIMIT    
- DEVICE_CONDITION     
- WEATHER_CONDITION     
- LIGHTING_CONDITION   
- FIRST_CRASH_TYPE      
- TRAFFICWAY_TYPE      
- ROADWAY_SURFACE_COND  
- INJURIES_TOTAL         
- CRASH_HOUR           
- CRASH_DAY_OF_WEEK     
- CRASH_MONTH                     
- VEHICLE_TYPE          
- PERSON_TYPE          
- SEX                 
- AGE                   
- SAFETY_EQUIPMENT      
- AIRBAG_DEPLOYED      
- DRIVER_VISION    

Models used from sklearn library using default parameters.
- Dummy Classifer (baseline)
- Logistic Regression 
- Random Forests 
- Gradient Booster

**Model Comparison**
HAVE PRINT OUT OF EACH SCORE AND PLOT.

**Grid Search**
For model tuning I am going to focus on the Random Forests model. It had the highest recall score (0.32), but when dealing with predicting if an injury has occured there is a higher 'cost' for a false negative. I took this model and performed a grid search to find the optimal parameters for imputer strategy ('mean'), RandomForest criterion ('gini'), and min_samples_leaf (5).

SMOTE technique was not utilized as method is not compatable with categorical features.

***

## Evaluation
After modeling was complete I used sklearn's permutation importance function in order to determine which features were most important in predicting if an injury occurred. The top 5 returned were: 

SAFETY_EQUIPMENT
FIRST_CRASH_TYPE
DEVICE_CONDITION
TRAFFICWAY_TYPE
AGE     

***

## Conclusion 
Provide your conclusions about the work you've done, including any limitations or next steps.
Questions to consider:

What would you recommend the business do as a result of this work?
What are some reasons why your analysis might not fully solve the business problem?
What else could you do in the future to improve this project?

***

### For More Information
Please review our full analysis in our **LINK TO Jupyter Notebook** or our **LINK TO presentation**.

For any additional questions, please contact Ashli Dougherty at ashli.d.dougherty@gmail.com









