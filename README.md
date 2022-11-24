## Saudi Arabia Real Estate- SDA Capstone Project

The Kingdom’s Vision 2030 is one of the giant projects that will have a significant impact on all 
aspects of life in the Kingdom of Saudi Arabia, and in particular economically. One of the 
important economic areas in which the vision will have a clear impact is the real estate sector. 
Whoever looks at the vision document clearly sees its direct and indirect impact on the real estate 
sector. The mega projects NEOM, Qiddiya and The line will increase the real estate area in the 
Kingdom and thus increase the area of housing, work and jobs.
The accurate forecast of future property prices is particularly important. 
As real estate prices are reflecting the economic level of countries. Developing a house-price 
forecast model could significantly assist in predicting future real estate prices and setting 
regulations. 
  In this project we are forecasting Saudi real estate prices. The dataset is from Kaggle. And it was 
collected and scrapped from Aqar website.. which is a specialized application for Saudi real 
estate, That shows you the properties available around you. The goal of this statistical analysis is 
to help us understand the relationship between house features and how these variables are used 
to predict the house price.
The dataset has some information for four cites which they are: Riyadh the Capital city of Saudi 
Arabia and the biggest city. And Jeddah the second biggest city. It also, has Dammam and 
Khobar and they are relatively small cites.
##### Columns Definition:
- city: city where house locate in Saudi Arabia
- district: district where house locate in that city
- front: What is the house front is north, west .. etc
- size: size in m^2
- property-age: property age for the house 
- bedrooms: number of bedrooms 
- bathrooms: number of bathrooms
- living-rooms: number of living-rooms 
- kitchen: show whether the house have a kitchen or not 
- garage: show whether the house have a garage or not 
- driver-room: show whether the house have a driver-room or not
- maid-room: show whether the house have a maid_room or not
- furnished: show whether the house is furnished or not
- ac: show whether the house have a ac or not
- roof: show whether the house have a space for roof on top or not
- pool: show whether the house have a pool or not
- front-yard: show whether the house have a front-yard or not
- basement: show whether the house have a basement or not
- duplex: show whether the house is a duplex or not
- stairs: show whether the house have a stairs or not
- elevator: show whether the house have an elevator or not
- fireplace: show whether the house have a fireplace or not
- price: show the price of the house in Saudi Riyal. 
- details: shows any additional details from the house owner about the house.

#### Data Exploration

![1](https://user-images.githubusercontent.com/105590616/188983031-573f239b-249c-45b0-8c94-7b31133f680f.png)

The figure shows prices range in the 4 cites. for example, in Riyadh we can see the 
normal distribution in prices with median of 80k SAR, and 25% 50000 SAR. while 75% 
are approximately 100k SAR. In Jeddah we can see higher numbers than in Riyadh. but 
for Dammam and Khobar we see a lowest prices range.


![2](https://user-images.githubusercontent.com/105590616/188985393-8634750e-79ac-494d-9f95-7004bdc73f53.png)

The figure shows that a property with front to North East or 4 streets have the highest 
range in price. Hence, we can say that front affect property price.


![3](https://user-images.githubusercontent.com/105590616/188985525-4d91743a-e478-4d07-bfa2-46adc3fa66c7.png)

The figure shows that the price can differ based on the property age. Property with a 
small age has a higher price.


![4](https://user-images.githubusercontent.com/105590616/188985689-f3331ca9-057d-4860-9223-5656054e32b7.png)

The figure shows a positive correlation between property size and the prices in Saudi Riyal, per each city. 


![image](https://user-images.githubusercontent.com/105590616/188985141-9d904b42-46aa-45c5-b6e7-b7eb72820a44.png)

The figure shows shows the average price per city, and we can see that Jeddah has the 
highest prices rate, then Riyadh and Khobar. while Dammam comes last as the lowest 
prices.

#### Implementation
We implemented algorithms based on linear regression and regression tree. 
But first the dataset has some outliers that might be human error, for example when property 
size is only 1 m2, or the natural deviations in prices where a house reaches 1,700,000 SAR.
Removing outliers that are due to the nature of data is not a good practice of course, but in 
our case we decided to remove them as they added noise to our models.
The models we decided to use are: Linear regression, logistic regression, K-nearest 
neighbor regressor, Random Forest regressor, Decision Tree regressor, Support Vector 
Regressor.
We took two approaches for selecting our features, one with all features, while the other 
with subset of features.
As a result the random Forest model with all features has the highest R squared values in 4 models out of 7.
Hence, we went with optimizing two of them. With a grid search.
In Random forest we obtained no much of an improvement. However, in XGBoost after 
we change the algorithm to be tree based learner, we were able to obtain much higher R 
squared score from 0.37 (in linear base learner) to 0.70 (in decision base learner).
- What can be improved?
Includes more features like if the property is near services such as entertainment centers, 
commercial centers, malls, and educational institutions in addition to restaurants, and 
cafes. Features like the property neighborhood including educational facilities, health care 
services, and recreational facilities, which makes it very attractive for the population to 
live in can improve the result.
