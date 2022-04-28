# Data Mining on COVID-19 Data using Machine Learning
In this project, analysis of the number of cases per day will be done to observe the trend. After the initial analysis, Simple Linear Regression and Support Vector Machine models will be used to predict the number of cases. 

# Introduction
COVID-19 is an infectious disease caused by SARS-CoV-2 Virus and most of the people infected with the virus will experience mild to moderate respiratory illness and will recover without requiring any special treatment. Predicting the number of cases is crucial to help the health professionals across the globe to minimize the fatalities and help the government make better decisions in advance. The COVID-19 dataset accumulated by John Hopkin University and other notable research groups contains information related to COVID-19 confirmed cases, recoveries, and deaths around the world from 22nd January 2020.

Data mining technique such as regression will be used to predict the number of cases using the data that is collected over time. Data Mining is the process of finding anomalies and patterns within large dataset to predict outcomes. There are many ways in which Data Mining can be achieved – for example, Association, Classification, Clustering and Regression. In this project, I will focus on the predictive analysis or Regression for this research. Regression is a statistical process for estimating the relationship between dependent variables and independent variables.

# Dataset
The dataset that is used for this analysis is the COVID-19 epidemiological data majorly compiled by John Hopkin University. The data source referred to is the AWS public data lake that consists of multiple tables provided by multiple research institutions. For this analysis, I have referred to the table – ENIGMA_JHU that contains all the details about confirmed, recovered and death cases since January 22, 2020. These cases for each region are updated daily and other attributes include province/state, country/region, latitude, longitude, last updated date and time, and key. For each region, the value in an instance contains the cumulative number of covid deaths, confirmed and recovered cases from January 22, 2020.

The data is pre-cleaned and does not require much manipulation but to predict the number of cases we need to segregate the last updated attribute into date and time attributes – which will be performed in Python. The total instances in this data are 222,805, with 15 attributes with cases from over +177 unique countries and +252 regions around the world. As per the analysis till 15th March 2020, there were 167,449 confirmed cases, 6440 deaths and 76,034 recovered cases.

# Experimental Setup
### Preprocessing
1. Split last updated attribute into date and time to identify confirmed, recovered and death cases per day for a particular region using Python. 
2. Create 3 tables for confirmed, recovered and death cases respectively for analysis using Microsoft Pivot Table.
3. Import all the 3 CSV files to Jupyter Notebook

### Analysis
1. Calculate the total number of confirmed cases, death cases and recovered cases.
2. Display all the unique countries and number of confirmed COVID cases associated to each country

As shown in the bar graph, x axis represents number of cases and y axis represents countries with the most confirmed cases. China is on the top with more than 80,000 confirmed cases and is highlighted red. Italy, Iran and other countries have moderate cases in the range of 15,000-25,000 and are highlighted in orange. Rest are the countries with less than 10,000 cases and are highlighted in yellow. This is for the period 22 January 2020 to 15 May 2020. 

3. Analysis of the number of confirmed cases from 22nd January 2020 for the next 50 days from the confirmed cases table.  

As shown in the Trend Plot, X-axis represents days and Y-axis represents number of cases where the cases are increasing linearly then suddenly rising after the 20-day mark. After stagnating for another 10 days, the cases start to rise exponentially till the 53rd day mark.

4. Analysis of the number of deaths caused by COVID since 22nd January 2022.

As per the trend plotted using matplotlib library, the trend follows the trend of confirmed cases where after increasing linearly and stagnating, the deaths seem to increase exponentially.

5. Analysis of the number of cases with respect to recovered and death cases since 22nd January 2020. 

Even though there is a separate graph for the number of deaths, the aim of this graph is to include the total deaths and recovered cases to show the extent of recoveries in comparison to deaths. This gives us hope that the war with COVID is conquerable if enough precautionary measures are considered. The recoveries were slow initially, but linearly increased over time.

### Prediction

1. Linear Regression

Linear Regression is a linear model – i.e., that assumes a linear relationship between the input and the output variable. In this case, the input variable is date, and the output variable is number of cases, therefore, with this relation, the number of cases can be predicted using days. Using simple linear regression between input and output, which is date and number of cases, a predictive model can be built. First step is to import Linear Regression from SKLEARN linear model library, then next step is to fit X train and Y train confirmed cases to this model. Predict function is used where days is an input variable to predict the number of cases. The following graph is plotted for the next 10 days using matplotlib:

As seen from the graph, even though, the graph follows linear relationship, but after the 45th day mark, cases suddenly start to increase breaking the linear relationship. Although, the model fits perfectly for the initial 20 days, and for the next 10 days with error tolerance, a polynomial or exponential model will better fit this data. Therefore, to better fit the graph, it is important to take a polynomial or exponential model such as SVM, to reflect the increase in cases. 

2. Support Vector Machine

SVM are a set of supervised learning methods used for regression and classification problems. The model is majorly implemented for classification problems, but in this single output data, the SVM model can be used as regression model to predict the number of cases if the number of days is altered.
There are different attributes and variables that can be adjusted in this model that can result in the prediction of better results, but for this analysis, a simple SVM with polynomial function will be used. 

This model has 4 major parameters which are the following:
- Kernel: Stands for the type of regression. Can be linear, polynomial, rbf, sigmoid and more.
- C: Stands for the miscalculation of training example against the simplicity of the decision surface. Meaning if C is low, the decision surface is smooth   and if C is high, model aims at predicting training examples correctly.
- Gama: This parameter determines how much influence a single training example has. If Gama is large, other examples are affected.
- Epsilon: It is the margin of tolerance where no penalty is given to errors. The samples are penalized when the predictions are wrong. If Epsilon is         large, there will be large error tolerance.

The best parameters are calculated using the best parameter function and suing it on the training data which comes to be as C =10, Epsilon = 1, Gama = 0.01 and Kernel = ‘Poly’.

As shown in the figure, SVM model fits better than the linear model as the number of cases suddenly take an exponential increase after the 47th day. Although, this might produce high error percentage in the later days of prediction.


