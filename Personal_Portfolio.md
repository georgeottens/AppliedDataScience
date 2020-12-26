# Knock-Out Criteria:
1. The contents of your personal portfolio reflect your contribution to the project, your abilities and what you have learned.
2. Portfolio consists of materials that you either realized individually, or in case of a group effort, a clear statement of what your contribution is in this group effort.
3. The (digital) portfolio is written in a very easily accessible way
4. The main document is a reader's guide (index) that shortly introduces your contributions and links to pages where the contributions are described in detail
5. Every contribution should be accessible from the reader's guide in a single click
6. Consists of links to the Python Notebooks or other evidence material about your contribution on the project that you have finished yourself

# Intro:
This is my Personal Portfolio after following the minor Applied Data Science at the The Hague University. It will consist of different chapters on my work, my group work and various assessments explained.
This Minor consists of six different projects which are related to real life data problems.
The timespan of the projects were from September 2020 to January 2021.
Every group has its own project-owner; the person who works at the concerned company.
The group I was in was called the Parcel group, which consisted of five other students, all from different kinds of studies and nearby cities.
Our project-owner is called Tim Ottens and he works at PostNL, the largest parcel-delivery company in The Netherlands.

# CONTENTS:

## DataCamp-Courses
1. [Introduction to Python](https://github.com/georgeottens/AppliedDataScience/blob/main/DataCamp/certificate%20Introduction%20to%20Python.pdf)
2. [Python Data Science Toolbox (Part 1)](https://github.com/georgeottens/AppliedDataScience/blob/main/DataCamp/certificate%20Python%20Data%20Science%20Toolbox%20(Part%201).pdf)
3. [Intermediate Python](https://github.com/georgeottens/AppliedDataScience/blob/main/DataCamp/certificate%20Intermediate%20Python.pdf)
4. [Python Data Science Toolbox (Part 2)](https://github.com/georgeottens/AppliedDataScience/blob/main/DataCamp/certificate%20Python%20Data%20Science%20Toolbox%20(Part%202).pdf)
5. [pandas Foundations](https://github.com/georgeottens/AppliedDataScience/blob/main/DataCamp/certificate%20pandas%20Foundations.pdf)
6. [Introduction to Data Visualization in Python](https://github.com/georgeottens/AppliedDataScience/blob/main/DataCamp/certificate%20Introduction%20to%20Data%20Visualization%20in%20Python.pdf)
7. [Manipulating DataFrames with pandas](https://github.com/georgeottens/AppliedDataScience/blob/main/DataCamp/certificate%20Manipulating%20DataFrames%20with%20pandas.pdf)
8. [Data Types for Data Science in Python](https://github.com/georgeottens/AppliedDataScience/blob/main/DataCamp/certificate%20Data%20Types%20for%20Data%20Science%20in%20Python.pdf)
9. [Cleaning Data in Python](https://github.com/georgeottens/AppliedDataScience/blob/main/DataCamp/certificate%20Cleaning%20Data%20in%20Python.pdf)
10. [Preprocessing for Machine Learning in Python](https://github.com/georgeottens/AppliedDataScience/blob/main/DataCamp/certificate%20Preprocessing%20for%20Machine%20Learning%20in%20Python.pdf)



## Reflection and Evaluation
1. [Reflection on own contribution to the project](https://github.com/georgeottens/AppliedDataScience/blob/main/Reflection-and-Evaluation/Reflection%20and%20Evaluation1.md)

2. [Reflection on own learning objectives](https://github.com/georgeottens/AppliedDataScience/blob/main/Reflection-and-Evaluation/Reflection%20and%20Evaluation2.md)

3. [Evaluation on the group project as a whole](https://github.com/georgeottens/AppliedDataScience/blob/main/Reflection-and-Evaluation/Reflection%20and%20Evaluation3.md)


## Research Project
### 1. Task Definition
Clearly described context (reason and problem definition) and research questions that are reasonable given context

PostNL is the biggest parceldelivery company in The Netherlands.
With customers all around the world the number of packages that need to be processed can go to over a million packages per day.
This project will only focus on PostNLs dutch customers.
With a high number of customers it is difficult to predict the number of parcels in a fashionable manner.
The company needs sufficient employees and trucks to process and deliver all these packages on time.
A sudden rise in number of packages can result in packages not being delivered on time, because of insufficient process-applications like trucks and employees.
Because of this problem this project has come to life.

*How can PostNL apply machine learning models, to predict the number of packages that need to be processed the next day?*
- What are the most common machine learning models for predicting time series?
- What are the most applicable models for the given data?
- What data can be used to improve the prediction?
- How reliable are the predictions of previous models?

### 2. Evaluation
Given several clear and motivated directions for future work

When this project is completed, there is a specific kind of model which will predict the number of parcels for a certain amount of time.
The accuracy of the model is yet to be defined.

Future work might find a different kind of predictive model, which will predict the number of parcels even better.
This can be an excisting model, but ofcourse also a newly formed model.

The goal however, will not change; predicting a number of packages that need to be processed.
I explicitly leave out saying the prediction for the next day, because the prediction can also be formed for a larger timescale, for instance a week or a month.

The steps to achieving this prediction will not change.
First theres the literature study, after that the coding itself, and ofcourse last but not least, the evaluation.

### 3. Conclusions
Discussed results, illustrated by examples(qualitative analysis), answers original research questions based on findings in study, tested outcomes for statistical significance

Some relatively simple models were tested in the making of these predictions.
Starting of with a simple [Auto Regressive(AR) model](https://github.com/georgeottens/AppliedDataScience/blob/main/Python-Graphs/AR%20model.png), where data of three months was used:
`train_data = ['2019-01-01':'2019-03-25']
test_data = ['2019-03-26':'2019-04-01']`
To see how well the model was able to predict the `test_data`.

As you can see in the AR model, it did pretty well on predicting the `test_data`, because the predicting followed the real number of processed packages fairly well. But because this model was just the start of all the models, the next models were being formed.

After using the AR model, the model was expanded with the Moving Average (ARMA), Integrated Moving Average (ARIMA) and finally, the Seasonal ARIMA model (SARIMA).

With the [ARMA model](https://github.com/georgeottens/AppliedDataScience/blob/main/Python-Graphs/ARMA%20model.png), the chosen training data was `['2016-01-01':'2019-09-01']` while the test data was `['2019-09-01':'2019-10-01']`,
so the model has 3 years and 8 months of training data, with 1 month as test data.

The model has `RMSE = 271` and `R^2 = 0.73`. The smaller the RMSE and the closer R^2 gets to 1, the better the model. A perfect model would have an RMSE of 0 and an R^2 of 1.
As seen in the ARMA model it kind of follows the same sort of line as the real number of packages, but it is higher in number. This could be because of the model not having an integrated moving average.



### 4. Planning
Planned research project in a good, agile and efficient way


## Predictive Analytics
### 1. Selecting a Model
Supported model selection with references from literature

While searching for applicable models, it was necessary to analyse the given data first to see what type of data it was.
The data turned out to be timeseries, so the models needed to be timeserie-models.
After finding [a list](https://machinelearningmastery.com/time-series-forecasting-methods-in-python-cheat-sheet/) of timeserie-models, a selection of models was made to be applied to our own data. This is were the AR, ARMA, ARIMA and SARIMA models came from.


### 2. Configuring a Model
Explains why configuration is reasonable (for instance using relevant literature)




### 3. Training a Model
Taking appropriate countermeasures to prevent under- and overfitting and tunes hyperparameters




### 4. Evaluating a Model
Comparing several models and additionally explains the differences between models




### 5. Visualizing the outcome of a model (explanatory)
Visualizing results both quantatively in a plot and where applicable qualitatively using examples




## Domain Knowledge
### 1. Introduction of the subject field
written a good and complete introduction of subject field

This project consist of applying certain coding/models to excisting data, to predict unknown data in a later stadium.
Some skill of coding and understanding the basics of Python are necessary to achieve results.



### 2. Literature Research
Found enough relevant literature and all in-text literature references and bibliography are present


### 3. Explanation of Terminology, Jargon and Definitions
Explained all important and all relevent terminology, jargon and definitions

All the necessary explanations of important and relevent terminology, jargon and definitions to get a better understanding of the project, can be found [here](https://github.com/georgeottens/AppliedDataScience/blob/main/Domain_Knowledge/3._Explanation_of_Terminology_Jargon_and_Definitions.md).

## Data Preprocessing
### 1. Data Exploration
Properly examined and visualized data, distributions, outliers, correlations and using analysis to give directions for an ealry hypothesis


### 2. Data Cleansing
Cleansed data in a good and sufficient way


### 3. Data preparation
Prepared data in an appropriate way, where necessary transforming data, removing outliers, filling in missing values etc.


### 4. Data visualization
Correctly visualized data in support of decisions made for learning model


## Communication
### 1. Presentations
Prepared or gave more than two (internal/external) solid presentations

These are PowerPoints given by me:
1. [Powerpoint week 6 Monday](https://github.com/georgeottens/AppliedDataScience/blob/main/Presentations/ppt_week_6.pptx)
2. [Powerpoint week 12 Friday](https://github.com/georgeottens/AppliedDataScience/blob/main/Presentations/ppt_week_12_vrijdag.pptx)
3. At the 21st of January, our whole group will give a presentation for PostNL itself, to explain our reasonings and findings of the project.

### 2. Writing Paper
Made a lot of effort on writing the paper


## Link to Python Notebooks


## List the tickets from the Scrum backlog that you have worked on, linked to deliverables, own experiments, etc.


## Add any other assignment you feel is evidence of your abilities
