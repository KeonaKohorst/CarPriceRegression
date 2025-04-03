# Car Price Regression

## Requirements
The model should be able to predict the price of a used car. It should generalize to new data, meaning it should predict the price of a used car that it has not seen before.

## Deliverables
The project should be completed in two parts:

Each student is required to submit a Jupyter Notebook that contains all the code used for the project, along with an exported HTML document to Moodle.
A prediction file should be submitted to the Kaggle competition. (You can submit your predictions 5 times a day before the deadline, and a small proportion of the submission is used for a real-time leaderboard.)
Grading
The assignment will be graded based on the following criteria:

The accuracy of the model
The ability of the model to generalize to new data
The clarity of the documentation for the model
The owners of the best 3 models will receive a bonus to their overall course grade: 5%, 2%, and 1% based on their position.

## Timeline
The competition closes on April 8. Late submissions are not accepted.

## Data Description
Price: Dependent variable
Year: Year the car was produced
Mileage: Kilometers driven by the car
City: City where the car was sold
State: State where the car was sold
Id: A unique identifier for the used car
Make: Manufacturer of the car
Model: The model (name) of the car

## Evaluation
The performance of the submission is measured using Mean Squared Error (MSE).

## Prediction file
Should be CSV with ID column and predicted price column

# Results Discussion
In this analysis, I trained a Random Forest Regressor to predict car prices based on features such as Year, Mileage, Make, Make mean price, Model mean price, State mean price and City mean price. The model's performance was evaluated using Root Mean Squared Error (RMSE) and R-squared.

## Model Performance
RMSE of 3955: This means that, on average, the model’s predictions are off by 3955 dollars from the actual car prices. Considering the average car price in the dataset is around 21,458 dollars, this RMSE indicates that the model captures the overall trends in the data, though there is still a reasonable amount of error in the predictions.

R-squared of 0.91: The model explains about 91% of the variance in car price. This is a strong result, showing that the model fits the data well and can identify the most important relationships between the features and the target variable.

## Statistical Analysis of the Data
The statistics show a significant spread in the data, with car prices ranging from as low as 1,500 to as high as 499,500. The mileage also varies widely, with cars ranging from low mileage vehicles (e.g., 5 miles) to those with extraordinarily high mileage (up to 2.8 million miles), which could be considered outliers. The Year variable shows that most cars are relatively recent, with an average age of 12 years.

I found success from removing outliers in the training data results, however once put into Kaggle the RMSE was significantly worse so I ultimately decided it was best to keep the outliers.

## Kaggle Results
On Kaggle, my model achieved a lower RMSE of 2772 on 10% of the test data, which is an improvement over the RMSE obtained in this notebook. This suggests that the test set used on Kaggle may contain simpler or less variable data compared to the dataset in this notebook, potentially leading to a better performance. Since the Kaggle performance is based on a smaller subset, it’s possible that the RMSE will increase when the model is tested on the complete dataset. I hope the RMSE will not exceed the RMSE observed here.

## Model Analysis and Conclusion
The Random Forest Regressor has demonstrated good generalization capabilities, as reflected by the high R-squared score (0.91) and the reasonable RMSE in both the train and test data in this notebook. It handles non-linear relationships well, capturing important patterns such as the inverse relationship between mileage and price. The model shows promise for predicting car prices accurately, but there is still room for improvement.

Given the wide variation in the dataset (particularly in car prices and mileages), the model has learned to deal with such complexity. However, further hyperparameter tuning and optimization could lead to improved performance. Additionally, the model’s performance on the full Kaggle test set will provide a clearer indication of its accuracy.
