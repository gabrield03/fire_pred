### Author: Gabriel Larot
### Last Updated: September 8, 2024

# **Fire Cost Prediction using ML**

## This project aims to estimate the dollar loss caused by a fire. In this project, I implement several machine learning algorithms to identify the best predictor based on various attributes (e.g., response time, location, number of casualties, etc.)

### We start off with the simplest, most basic predictor, a linear regression model. There is little to no data cleaning. 
- The objective is to get a base score to compare against more complicated algorithms as well as feature engineering, scaling, and other preprocessing methodologies.
- I added a response_time attribute which was the difference, in seconds, between the alarm time and the arrival time.
  - Future implementations will use more complicated methods to extract useful features.

### Predictor two - implemented a few other algorithms
- Looked at categorical features to see what can be one-hot encoded
- Scaled the data after one-hot encoding
- Implemented the linear regression model from (file) predictor one
    - Nearly the same results
- Implemented Support Vector Regressor, Gradient Boosting Regressor, and Gaussian Naive Bayes
    - Results were not much better from predictor one
 
### Predictor three - removing huge outliers from the target variable
- Imported pred one and two
- Implemented a random forest classifier to check feature importance from combined categorical (one-hot encoded) and numerical attributes
    - Kept the most important features (95% of cumulative importance)
- Implemented SVR - results much better (off by ~8000) which is still undesirable
    - Used grid search CV to find the best parameters
- Finally, looked at origin - was ignored previously
    - I was curious about the impact origin had on est_loss. Did not know what to do with it because there are so many unique values (still figuring it out)
    - Investigated the most correlated features. "Under investigation" had the highest correlation.
    - SVR with only the origin feature out of curiousity. It was similar to predictor two.

### Predictor four - neural network
- Full ML implementation incorporating knowledge gained from files 1 - 3.
- Working on a custom transformer to add extra attributes
- Create a pipeline for easier and smoother future testing and implementations
- Still in progress
