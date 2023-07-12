## Saudi Arabia Real Estate- SDA Capstone Project


The Kingdom's Vision 2030 is one of the major projects that will have a significant impact on all aspects of life in Saudi Arabia, and in particular economically. One of the important economic areas in which the vision will have a clear impact is the real estate sector. Whoever looks at the vision document clearly sees its direct and indirect impact on the real estate sector. The mega projects NEOM, Qiddiya, and The Line will increase the real estate area in the Kingdom and thus increase the area of housing, work, and jobs. The accurate forecast of future property prices is particularly important. As real estate prices reflect the economic level of countries. Developing a house-price forecast model could significantly assist in predicting future real estate prices and setting regulations. 

     In this project, we are forecasting Saudi real estate prices. The dataset is from Kaggle. And it was collected and scrapped from Aqar website, which is a specialized application for Saudi real estate, That shows you the properties available around you. 
     This statistical analysis aims to help us understand the relationship between house features and how these variables are used to predict house prices. The dataset has some information for four cities which they are: Riyadh the Capital city of Saudi Arabia and the biggest city. And Jeddah is the second biggest city. It also has Dammam and Khobar and they are relatively small cities.


     
##### Columns Definition:
- city: the city where the house is located in Saudi Arabia
- district: a district where the house is located in that city
- front: What is the house front is north, west .. etc
- size: size in m^2
- property-age: property age for the house 
- bedrooms: number of bedrooms 
- bathrooms: number of bathrooms
- living-rooms: number of living-rooms 
- kitchen: show whether the house has a kitchen or not 
- garage: show whether the house has a garage or not 
- driver-room: show whether the house has a driver-room or not
- maid-room: show whether the house has a maid_room or not
- furnished: show whether the house is furnished or not
- ac: show whether the house has an ac or not
- roof: show whether the house has a space for a roof on top or not
- pool: show whether the house has a pool or not
- front-yard: show whether the house has a front yard or not
- basement: show whether the house has a basement or not
- duplex: show whether the house is a duplex or not
- stairs: show whether the house has stairs or not
- elevator: show whether the house has an elevator or not
- fireplace: show whether the house has a fireplace or not
- price: show the price of the house in Saudi Riyal. 
- details: shows any additional details from the house owner about the house.

#### Data Exploration

![1](https://user-images.githubusercontent.com/105590616/188983031-573f239b-249c-45b0-8c94-7b31133f680f.png)

The figure displays the price ranges in the four cities. For instance, in Riyadh, we observe a normal distribution of prices with a median of 80k SAR, where 25% of prices are at 50,000 SAR, and approximately 75% are at 100k SAR. Conversely, Jeddah has higher prices than Riyadh. However, in Dammam and Khobar, we observe a lower price range.


![2](https://user-images.githubusercontent.com/105590616/188985393-8634750e-79ac-494d-9f95-7004bdc73f53.png)

The figure indicates that a property with a front-facing North East or with access to four streets has the highest price range. Therefore, we can conclude that the frontage of a property has an impact on its price.

![3](https://user-images.githubusercontent.com/105590616/188985525-4d91743a-e478-4d07-bfa2-46adc3fa66c7.png)

The figure shows that property prices can vary based on the age of the property, with newer properties having a higher price.


![4](https://user-images.githubusercontent.com/105590616/188985689-f3331ca9-057d-4860-9223-5656054e32b7.png)

The figure indicates a positive correlation between property size and prices in Saudi Riyal for each city.


![image](https://user-images.githubusercontent.com/105590616/188985141-9d904b42-46aa-45c5-b6e7-b7eb72820a44.png)

The figure illustrates the average property prices per city, revealing that Jeddah has the highest price rate, followed by Riyadh and Khobar.
On the other hand, Dammam has the lowest average property prices among the four cities.

#### Implementation
We implemented algorithms based on linear regression and regression trees. However, the dataset contained some outliers that may have resulted from human error, such as properties with a size of only 1 m2, or natural price deviations where a house costs 1,700,000 SAR. Although removing outliers is generally not recommended, we decided to remove them as they added noise to our models.

The models we used were linear regression, logistic regression, K-nearest neighbor regressor, Random Forest regressor, Decision Tree regressor, and Support Vector Regressor. We took two approaches to selecting our features: one with all features and the other with a subset of features. As a result, the Random Forest model with all features had the highest R-squared values in four out of seven models. We then optimized two of them using a grid search.

We obtained little improvement in the Random Forest model. However, when we changed the algorithm to be tree-based in XGBoost, we were able to achieve a much higher R-squared score, from 0.37 (in the linear base learner) to 0.70 (in the decision base learner).

What can be improved?
  - We could include features indicating whether the property is near services, entertainment centers, malls, educational institutions, restaurants, and cafes, as they may enhance our results.
