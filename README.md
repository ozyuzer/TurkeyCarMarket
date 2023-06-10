# CS210_Project_AltiliMasa

1-Research and Findings About the Car Market in Turkey
For this project, have analyzed a dataset regarding the car market in Turkey.

Hypothesis: The price of cars in the Turkey car market is influenced by several factors such as brand, model year, vehicle type and color and predictive models can be used to predict car prices based on these factors.

Research Question: How these features affect the car prices in Turkey market?

2-Information About Data Source
We found our data from Kaggle and it is originally from a website called “Sahibinden.com”. The data contains real prices of cars in Turkey market. There are several features in this data such as Date, Brand, Type of car, Model Year and Price. In this part, we also provided some statistics about the data.

3-Data Cleaning and Preprocessing
In our data analysis, we began by employing the isnull() library to detect any missing values in our dataset. Fortunately, our investigation revealed that no data values were missing. Additionally, we conducted a thorough examination for duplicates and identified a total of 1594 duplicate columns. To ensure the accuracy of our analysis, we promptly eliminated these duplicates from the dataset.
Next, we proceeded to transform the categorical variables into a numerical format suitable for machine learning models. To achieve this, we specifically focused on the columns 'Arac Tip Grubu', 'Marka', 'Yakıt Turu', and 'Model Yıl'. To prepare these columns for encoding, we utilized the OneHotEncoder class, and through the fit() method, the encoder learned the unique categories and their respective numerical representations for each selected column. By performing this encoding, we obtained a transformed dataset that facilitated further analysis and model training.
Moreover, we leveraged the ColumnTransformer() function in our code, which allowed us to apply diverse transformations to distinct column types. In particular, we employed the StandardScaler() transformation on the numerical column 'Km'. This transformation standardizes the values, giving them a mean of 0 and a standard deviation of 1. By scaling the numerical column, we ensured its compatibility with the rest of the dataset and enhanced the accuracy of our subsequent analyses.

4-DATA ANALYSIS
In order to obtain comprehensive understanding of the data and its features, we conducted a general analysis of the dataset before interpreting the potential impact of different features, and checking for our hypotesis. So let's dig in to the visualization of the Turkey's car market data and better understand the content:
Top Color Preferences:
As the title suggests, this observation provides insigtful information about the color preferences of the car market in Turkey.
Might affect the market demand which could straightforward impact the car prices.
Visualization indicates higher demand for white-colored cars by far.
Mean Price by Model Year for Popular Brands:
This examination is conducted so we could identify if there are any trends considering the model year of the car.
Provides understanding of varying prices related to model years.
For instance, we can detect the price anomaly of Opel vehicles before 90s, and not be certain that brand new vehicles are more pricy compared to the older models.
Mean Price of Most Expensive Brands:
This analysis studies whether there is a correlation between the manufacturer and the prices for the vehicles.
Could also lead us to answers regarding the effect of brand value to the pricing of luxury brands.
Projected Price Change of BMW vehicles:
This visualization aims to observe and diagnose the potential pattern the price observations can exhibit.
It attempts to identify the price trend and predict potential price shifts by fitting a polinomial curve with historical data.
Provides insights of potential price fluctuations of BMW vehicles over time.

4.1-Interpretation

In this part, we will investigate the effects of several features to the prices of cars in Turkey:

Model Year: The visualization confirms that newer cars have higher prices. Classic cars from 1960 also have high demand, indicating their higher value. But in general, we can say that the model year directly influences the car price.
Mileage: The plot shows that as the kilometers driven increases, car prices decrease. This relationship makes sense since car performance typically decreases as mileage increases. Therefore, we can conclude that mileage is an important factor that affects the price of a car.
Fuel Type: Electric cars have the highest average price, followed by hybrid cars. The advanced technology required to produce these cars explains the price difference. Thus, fuel type is another factor that influences the car price.
Color: Mean prices for the top five most frequent colors show that black cars have a higher mean price compared to other colors. However, the mean prices of other colors are relatively close. This suggests that black may be a popular color in the market, but it is not clear if color directly affects the car price as it may be a matter of personal preference.
Brand: The graph indicates that the brand of a car directly affects its price. Brands with a high reputation and reliability tend to have higher prices. Top brands often provide advanced technology and higher-quality features, justifying their higher car prices.


5-Model Prediction by using Linear Regression

In this part, we will predict the prices of cars by using Linear Regression model which is a type of supervised learning. For the model:

Our target variable is the 'Fiyat' column, which represents the price of a vehicle. The goal is to develop a model that can accurately predict the price based on various features.
To assess the performance of our model, we split the data into training and test sets. This was accomplished using the train_test_split function from scikit-learn. We randomly assigned 80% of the data to the training set and 20% to the test set.
We considered several features to predict the car prices such as the type of the car,brand, leverage(km),the year of the model and the car type group of the model. We did not use color since it has no significant impact on car prices.
To deal with categorical columns, we employed the ColumnTransformer and OneHotEncoder from scikit-learn to handle this. Categorical columns ('Arac Tip Grubu', 'Marka', 'Yakıt Turu', 'Model Yıl', 'Arac Tip') were passed to the OneHotEncoder during the preprocessing step. This encoding converted the categorical values into numerical features using binary vectors.
To ensure proper scaling of numerical features, we used the StandardScaler from scikit-learn. This was applied to the 'Km' feature, which was included in the dataset. Scaling the features helps prevent any particular feature from dominating the learning process and ensures that all features contribute equally.
We employed the LinearRegression algorithm from scikit-learn to create our linear regression model. The r2_score of the model found as %88 which suggests that our model captures a significant portion of the price variation.
