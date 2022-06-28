# Impact-of-Covid-19-Pandemic-on-Criminal-Activities

# SPL-Group-6
This project is a part of the Survey of Programming Languages (ITCS - 5102) course from the University of North Carolina at Charlotte.

## Team Members
* Sumati Bele
* Rucha Visal
* Dhvani Patel

## Project Introduction
The objective of this project is to find the correlation between criminal activities ( example: homicide, weapon violations) and, financial crisis (2007-2008) and COVID-19 pandemic and create a model to further predict the trends in criminal activities if such a disaster might ever occur in future. The dataset comprises incidents reported in the City of Chicago from 2001 to the present. CRISP-DM methodology will be used to conduct this study that consists of a problem and data understanding, data preparation, modeling, evaluation, and deployment phases. Our aim is to uncover rules for quantifying relationships between attributes (example: public peace violation during both the events).

## Data Resource
[Link for the dataset](https://data.cityofchicago.org/Public-Safety/Crimes-2001-to-Present/ijzp-q8t2/data)

This dataset reflects reported incidents of crime that occurred in the City of Chicago from 2001 to the present. This dataset gets updated on a weekly basis. Data is extracted from the Chicago Police Department's CLEAR (Citizen Law Enforcement Analysis and Reporting) system.

It consists of the following attributes:

|Column Name      | Description   |                                                                                        Type   |
|-----------------|-------------- |---------------------------------------------------------------------------------------------- |
|Arrest           | Boolean value indicating whether the criminal was arrested or not.                                  | Boolean |
|Primary Type     | The primary description of the IUCR code.                                                           | Text    |
|Description      | The secondary description of the IUCR code, a subcategory of the primary description.               | Text    | 
|Date             | Date when the incident occured.                                                                     | Date    | 

## Objectives of performing Exploratory Data Analysis on any data

EDA helps us to identify faulty points in the data which can then be used to remove them and clean the data. It also helps us to find relationships between the variables which gives us a wider perspective on the data and also analyze the relationship between the variables.

## Cross Industry Standard Process for Data Mining

This methodology consists of descriptions of typical phases of the project, the task involved with each phase, and an explanation of the relationship between the tasks. 

## CRISP-DM Process

Steps involved in the process:
* Business Understanding stage
* Data Understanding stage
* Data preparation stage
* Modeling stage
* Evaluation stage
* Deployment stage

## Business Understanding Stage

There are different types of crimes, some of which have a clear link to pandemic and recession, while others do not. It is crucial to think about the plausible directions of causality. Chicago has higher crime rates than any other city. There is an overall declining trend in the number of crimes that occurred between 2001 and 2021. Although, certain types of crimes show an upward trend when disasters such as a recession or pandemic occur.

## Data Understanding Stage / Exploratory Data Analysis

The dataset comprises 7427119 observations and 22 features with int, float, bool and object type values.

**Assault Crimes**

For the Assault, Crime data (AsCrime Group), we can observe a declining trend throughout. Observing the specific time period of the Economic recession from 2007 and the Covid-19 pandemic in 2020, we can figure out that the assault crime type overall has a declining trend for both the Recession and the Covid periods respectively. The decline in the count has been shallow during the recession but has a very rapid decrease during the covid period.

**Weapons Violations**

For the weapon violations based Group of crimes, we can observe a good decline from 2007 with a sharp rise after 2008. This period during the recession created severe financial stress amongst people which led to a sharp increase in mugging or violence using guns. These crime rates went up drastically during the Covid period as well possibly due to lockdown and its related psychological impacts on people. The covid-19 period created financial stress in people. Observing specific time period of economic recession from 2007 and the Covid-19 pandemic in 2020, we can figure out that this crime type overall has an increasing trend during both the Recession and the Covid-19 period.

**Burglary and Robbery Crimes**

For the Burglary and Robbery Crime data (BugRob Group), we can observe a slight increase from 2007 with a slight dip in 2008 followed by a steady increase again in the later years. These crime rates went down drastically during the Covid period possibly due to lockdowns since people were mandated to stay at their homes. Observing the specific time period of Economic recession from 2007 and the Covid-19 pandemic in 2020, we can figure out that this crime type overall has an increasing trend for during the Recession and a declining trend during the Covid period.

**Theft Crimes**

For the Theft, the Crime data (ThefM Group), which also includes 'Motor Vehicle Thefts', we can observe a slight decrease from 2007 to 2008 followed by a sharp increase again in 2009. These crime rates went down drastically during the Covid period possibly due to lockdown since the presence of people at home made it difficult to proceed with such criminal activities. Observing the specific time period of economic recession from 2007 and the Covid-19 pandemic in 2020, we can figure out that this crime type overall has an increasing trend for during the Recession and a declining trend during the Covid period.

**Gambling and Narcotics crimes**

For the GamNar Group of crimes, consisting of gambling and narcotic crimes, we can observe a steady decrease from 2007 with a sharp decline from 2008 possibly due to heavy financial crunch and social unrest. These crime rates went down drastically during the Covid period as well due to lockdown and strict norms by the civic authorities implemented to restrict the movement of people in the open. Observing the specific time period of economic recession from 2007 and the Covid-19 pandemic in 2020, we can figure out that this crime type overall has a declining trend for both the Recession and the Covid-19 period.

**Public Peace Violations**

For the PubViolation Group of crimes, consisting of crimes creating social unrest, we can observe an increase from 2007 with a slightly negligible decline in 2008 followed by an increase from 2009 possibly due to heavy resistance and protests from people impacted by the disaster. These crime rates went down drastically during the Covid period as well due to lockdown and severe punishments for anyone breaking the lockdown rules. Observing specific time period of economic recession from 2007 and the Covid-19 pandemic in 2020, we can figure out that this crime type overall has an increasing trend during the Recession and a declining trend during the Covid-19 period.

**Homicide crimes**

For the Homicide Group of crimes, we can observe a good increase from 2007 with a slight slight decline in 2008 followed by an increase from 2009. This period during the recession created severe psychological stress amongst people which led to a sharp increase in murders. These crime rates went up drastically during the Covid period as well possibly due to lockdown and its related psychological impacts on people. The covid-19 period also destroyed a lot of businesses and jobs which forced many to choose criminal paths. Observing specific time period of economic recession from 2007 and the Covid-19 pandemic in 2020, we can figure out that this crime type overall has an increasing trend during both the Recession and the Covid-19 period.

## Data Preparation Stage
1. Importing Crimes dataset into Jupyter notebook.
2. Understanding the information provided in the dataset and looking for types of columns, number of unique values in each column and missing values.
3. Converted datatype of ‘Date’ column to DATETIME from OBJECT type.
4. Check for NULL values in the data frame. No null values observed.
5. Drop the features which are not necessary.
6. Check for a unique ‘Primary type’ having a count of 36.
7. Merged the similar crimes into a generalized type for easy processing.
8. Plotted the various trends observed with respect to thefts, assaults, weapon violations, homicide, gambling and narcotics, and burglary and robbery crimes against date to further predict the future trends.

## Modeling Stage
We have used LSTM based deep learning technique to make time series predictions. For this project, we are considering the top two districts with the highest crime and predicting the each crime for a period of one year. For the recession period, we have considered data from 2007-2008 for training and prediciting the crime for the 2009 year. For prediciton based on the pandemic, we are considering data from 2019-2020 for training and data till Nov 2021 for prediciton. It is an important to step because that's how we can make appropriate resource allocation decisions.

## Facebook Prophet
Prophet is a method for forecasting time series data that uses an additive model to accommodate non-linear trends with annual, weekly, and daily seasonality, as well as holiday impacts. It works well with time series that have substantial seasonal impacts and historical data from several seasons. Prophet is resistant to missing data and trend alterations, and it generally handles outliers well. As a part of an experiment, we used a Facebook prophet to perform time series forecasting for the criminal data of years 2019,2020, and 2021 ( Covid impacted years) and generated future data for 2 consecutive years. We plotted the forecasted data and studied the same.

## Evaluation Stage
We have used the following metric to evaluate the model- RMSE: The RMSE for training and test sets should be very similar if you have built a good model. If the RMSE for the test set is much higher than that of the training set, it is likely that you've badly overfitted the data, i.e. you've created a model that tests well in a sample, but has little predictive value when tested out of sample.Our basedline evaluation metric for Long Short-Term Memory (LSTM) model was around Root Mean Squared 130.10.\
For rececssion period the following are the results:\
For District 1 (considering all 7 types of crimes) we achieved an RMSE score of : 31.135\
For District 2 (considering all 7 types of crimes) we achieved RMSE score of : 36.863

For a pandemic period the RMSE score is:\
For District 1 (considering all 7 types of crimes) we achieved an RMSE score of : 33.746\
For District 2 (considering all 7 types of crimes) we achieved RMSE score of : 23.282

## Conclusion
For this project, we have done several visualizations to dig deeper into the dataset to find various correlations between the features and the target variable. The unique thing about our data is that it doesn’t contain any NULL values. The columns chosen for processing have no null values. Hence there is no need for imputation or handling of null values. We used the Date feature to derive other attributes like ‘day’ of the activity, ‘month’ of the activity and to see a few graphs related to them. We removed rows where the year in ‘Date’ does not match the year in the ‘Year’ column also, we removed duplicates based on ID, Case Number pair. We used Root Mean Square Error(RMSE) as an error measure.

## Future Work
 We plan to further study how the prediction of some future events can be devised based on historical data. We plan to dig further into ‘Demand Forecasting’ and how we can use association rules to make the model sensitive to various scenarios. We will further explore advanced implementations on criminal datasets to make our project robust and generate efficient predictions of not only counts of activities but also location.
