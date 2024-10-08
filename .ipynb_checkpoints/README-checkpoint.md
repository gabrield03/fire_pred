# **Fire Cost Prediction using ML**

## This project aims to estimate the dollar loss caused by a fire. In this project, I implement several machine learning algorithms to identify the best predictor based on various attributes (e.g., response time, location, number of casualties, etc.)

### We start off with the simplest, most basic predictor, a linear regression model. There is little to no data cleaning. 
- The objective is to get a base score to compare against more complicated algorithms as well as feature engineering, scaling, and other preprocessing methodologies.
- I added a response_time attribute which was the difference, in seconds, between the alarm time and the arrival time.
  - Future implementations will use more complicated methods to extract useful features.
