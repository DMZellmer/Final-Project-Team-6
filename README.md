![la_bg2](https://user-images.githubusercontent.com/86331828/144959894-27847826-5b2b-4863-94df-44b529753de9.jpg)



# Final Project

## Selected Topic
### World Population Data 
[Group 6 World Population Website](https://piratesuit.github.io/)

### Description of source data

- Dataset: World Population 1960-2018, 2020
  - https://www.kaggle.com/imdevskp/world-population-19602018?select=pop_worldometer_data.csv
- This dataset includes each countries population, net change, land area, migrants, fertility rate, median age, urban population and world share % as of 2020.
- This dataset includes additional csvs that include more specific data like female population percentage, population above age 65, population below age 14 and population density, all from about 1960-2017.

### Questions we hope to answer:

* What variables in this dataset are predictive of a country's net population change?
* How do these variables relate to each other with regard to population change?
* What are the most important variables in this dataset to the outcome of net population change?

## An initial list of tables and columns 

![image](https://user-images.githubusercontent.com/86337475/141880865-0ccb4eb6-6e0b-4e18-8609-79aa7099d44d.png)


## Machine Learning Models

* We will explore options of multilinear regression in training and testing our dataset.

* No live predictions will be included in the project.


## Machine Learning

Multilinear regression analysis was performed on the dataset in order to determine which features are predictive of a country's net population change. Therefore, the target feature was "% Yearly Change", assigned the variable "y" and was removed from the X_train and X_test datasets. 

![image](https://user-images.githubusercontent.com/86337475/143961140-5bb4ca36-fbd8-41d8-a7ee-19af14c63876.png)

After splitting the data into training/testing datasets, the X data was scaled. 


![image](https://user-images.githubusercontent.com/86337475/143961320-e7cd599a-97f1-4955-b0df-5c46fd149691.png)


Using Scikitlearn library, linear regression was performed on the data.

![image](https://user-images.githubusercontent.com/86337475/143961588-4851e1b7-3dd0-43f4-a961-e92ceb0913fc.png)


As you can see by the massive Mean Squared Error (MSE) value, this model was not a good choice for this dataset. 


Next, a basic neural network model was used which contained nine hidden layers and the ReLu activation function.


![image](https://user-images.githubusercontent.com/86337475/143962015-e42bf224-1be7-47f2-b826-9756066ea444.png)


This also generated a very high MSE value and so was not a good model for this dataset. 



At this point, the target values were encoded and normalized using sklearn.preprocessing.LabelEncoder()

![image](https://user-images.githubusercontent.com/86337475/143962968-ec9997f3-1498-40c2-9a58-ea5419821df4.png)



A Random Forest Regressor was then fit to the dataset and evaluated for predictive performance. 

![image](https://user-images.githubusercontent.com/86337475/143963287-0e8be864-800e-414c-aaef-c2c63bdb887c.png)


This model performed well on the dataset, with an MSE logarithmically lower than the previous models. 

## Additional Data

- From the original dataset we pulled additional migrant data to see what the percentage of the yearly change and percentage of total population was from migrants. 
- This information did not have a strong correlation with the other data.

## Summary of Results
- When analyzing the data we found the two factors that seem to affect the percentage of yearly population change were fertiliy rate and median age. 
- A higher fertility rate resulted in a higher percentage of yearly population change.
- A higher median age resulted in a lower percentage of yearly population change.
- The countries with the lowest fertility rates also had the lowest median age. 
- With the exception of fertility rate and median age, none of the other features showed a strong correlation to yearly population change percentage. 


## Other Considerations
- The Covid-19 pandemic made 2020 a unique year. 
- If we were to do further analysis we would use the trends seen in 2020 to compare to other years. Specifically looking at differences in fertility rate, median age, net change and number of migrants.
