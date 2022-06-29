# WaterAnalytics
Predicting water levels for different water bodies

<img src='https://user-images.githubusercontent.com/77097236/176115195-c28c5ffa-0c2c-4111-8728-0f46bfbb3466.jpg' width='400' height='275'>

## Table of Contents
* [Introduction](#introduction)
* [EDA](#exploratory-data-analysis)
* [Code Documentation](#code-documentation)

## Introduction
This project was done as part of the **_CIVENG 203N Surface Water Hydrology_** course I took during my exchange in Berkeley. We had to make use of machine learning techniques to create a positive impact on environmental conservation, specifically in the field of water hydrology. I decided to work on using **_time-series analysis to predict water levels for unique waterbodies_** using past data.
My **_initial hypothesis_** was that **_LSTM-based neural networks would perform the best_** because of its ongoing popularity for sequential data prediction.

## Exploratory Data Analysis
### 2.1) Date-Time Manipulation
As we have the data for many different kinds of waterbodies, we will start off by analysing the dataset for Aquifer Petrignano. For time-series analysis, our date column has to be converted to **_datetime format_** and we will also sort our dataset in **_chronological order_** for input into our model later on.

### 2.2) Removing Unimportant Features
Firstly, we will create a time-plot for each of our existing features to look for correlation.
<p align="left">
  <img src='https://user-images.githubusercontent.com/77097236/176351087-8201d80e-26f7-4fbd-82c7-88894d895ab9.png' width='250' height='180'>
  <img src='https://user-images.githubusercontent.com/77097236/176351097-0423b1b7-1718-43a3-ada0-f2fc5e84107e.png' width='250' height='180'>
  <img src='https://user-images.githubusercontent.com/77097236/176351108-0ea70059-76fb-4104-b34d-c3b9196afccc.png' width='250' height='180'>
  <img src='https://user-images.githubusercontent.com/77097236/176351110-19e7d298-8485-42e7-a5f9-32c6cf7aab48.png' width='250' height='180'>
  <img src='https://user-images.githubusercontent.com/77097236/176351115-03e8dda2-c0cc-4976-b7aa-8825820bb41f.png' width='250' height='180'>
  <img src='https://user-images.githubusercontent.com/77097236/176351120-be627a3d-3509-437f-936c-b334f52a1581.png' width='250' height='180'>
  <img src='https://user-images.githubusercontent.com/77097236/176351125-a25a5ba8-cb9a-462a-a027-84d71560eb21.png' width='250' height='180'>
</p>

From the plots, we can see that depth_p24 and depth_p25 are similar, as well as temp_umbra and temp_petri. Hence, we will only keep depth_p25 as the target variable and temp_petri as the feature variable. Furthermore, as we can see from the depth and rainfall plots, we have a correlation where a higher rainfall results in a deeper water body. 

As seen from the plots above, the target variable (Depth to Groundwater) contains data since 2006, but the feature variables mostly only contain data from 2009 onwards, hence we will drop all data before 2009 to remove these NaNs that would affect our model performance negatively.

Next, we will plot the target variable (Depth) against each of the feature variables to look for any inherent relationship between them.
<p align="left">
  <img src='https://user-images.githubusercontent.com/77097236/176352275-0e71bd67-aafd-4981-bdeb-0453a84c2282.png' width='400' height='200'>
  <img src='https://user-images.githubusercontent.com/77097236/176352282-2c3a92f7-e576-4622-aea3-94169f2bcc57.png' width='400' height='200'>
  <img src='https://user-images.githubusercontent.com/77097236/176352298-dcf0ee6e-c95a-407f-ba1a-5eb59ab573e8.png' width='400' height='200'>
  <img src='https://user-images.githubusercontent.com/77097236/176352311-49dec674-de91-475d-80de-f904e48bacda.png' width='400' height='200'>
</p>

