# Data Mining on COVID-19 Data using Machine Learning
In this project, analysis of the number of cases per day will be done to observe the trend. After the initial analysis, Simple Linear Regression and Support Vector Machine models will be used to predict the number of cases. 

# Introduction
COVID-19 is an infectious disease caused by SARS-CoV-2 Virus and most of the people infected with the virus will experience mild to moderate respiratory illness and will recover without requiring any special treatment. Predicting the number of cases is crucial to help the health professionals across the globe to minimize the fatalities and help the government make better decisions in advance. The COVID-19 dataset accumulated by John Hopkin University and other notable research groups contains information related to COVID-19 confirmed cases, recoveries, and deaths around the world from 22nd January 2020.

Data mining technique such as regression will be used to predict the number of cases using the data that is collected over time. Data Mining is the process of finding anomalies and patterns within large dataset to predict outcomes. There are many ways in which Data Mining can be achieved – for example, Association, Classification, Clustering and Regression. In this project, I will focus on the predictive analysis or Regression for this research. Regression is a statistical process for estimating the relationship between dependent variables and independent variables.

# Dataset
The dataset that is used for this analysis is the COVID-19 epidemiological data majorly compiled by John Hopkin University. The data source referred to is the AWS public data lake that consists of multiple tables provided by multiple research institutions. For this analysis, I have referred to the table – ENIGMA_JHU that contains all the details about confirmed, recovered and death cases since January 22, 2020. These cases for each region are updated daily and other attributes include province/state, country/region, latitude, longitude, last updated date and time, and key. For each region, the value in an instance contains the cumulative number of covid deaths, confirmed and recovered cases from January 22, 2020.

The data is pre-cleaned and does not require much manipulation but to predict the number of cases we need to segregate the last updated attribute into date and time attributes – which will be performed in Python. The total instances in this data are 222,805, with 15 attributes with cases from over +177 unique countries and +252 regions around the world. As per the analysis till 15th March 2020, there were 167,449 confirmed cases, 6440 deaths and 76,034 recovered cases.

# Experimental Setup
