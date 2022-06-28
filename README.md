# WaterAnalytics
Predicting water levels for different water bodies

<img src='https://user-images.githubusercontent.com/77097236/176115195-c28c5ffa-0c2c-4111-8728-0f46bfbb3466.jpg' width='400' height='275'>

## Table of Contents
* [Introduction](#introduction)
* [EDA](#exploratory-data-analysis)
* [Code Documentation](#code-documentation)

## Introduction
This project was done as part of the **_CIVENG 203N Surface Water Hydrology_** course I took during my exchange in Berkeley. We had to make use of machine learning techniques to create a positive impact on environmental conservation, specifically in the field of water hydrology. I decided to work on using time-series analysis to predict water levels for unique waterbodies using past data.
My initial hypothesis was that LSTM-based neural networks would perform the best because of its ongoing popularity for sequential data prediction.

## Exploratory Data Analysis
### 2.1) Date-Time Manipulation
As we have the data for many different kinds of waterbodies, we will start off by analysing the dataset for Aquifer Petrignano. For time-series analysis, our date column has to be converted to datetime format and we will also sort our dataset in chronological order for input into our model later on.

### 2.2) Removing Unimportant Features
Firstly, we will create a time-plot for each of our existing features to look for correlation.
