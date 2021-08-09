# King County Linear Regression Analysis

By Mohamed Hassan

## Objective:

As people are increasingly buying homes during the pandemic, this project will give a breakdown of what homeowners and prospective buyers should prioritize when deciding what features of a home they should focus on in order to increase the price of their homes in King County, Washington.

## Data Source and Details:

The data used in this project was derived by Kaggle, with a total of 21,597 homes between 2014-2015. The features of the home include: id, date, price, bedrooms, bathrooms, square footage of the home, square footage of the lot, floors, waterfront, view, grade, square footage of a home apart from the basement, square footage of the basement, year built, year renovated, zipcode, latitude,	longitude, the square footage of interior housing living space for the nearest 15 neighbors, and the square footage of the land lots of the nearest 15 neighbors.

## Initial Statistical Analysis: EDA

Most of the features of this dataset did not having missing and/or NaN values. For waterfront and view, I filled in all the NaN values with the median of that respective feature. For year renovated, I filled in any missing values with the most frequent year in that column. In the square foot basement column, I removed a character that was in one of the values and changed the datatype. Id and date were dropped because they are not physical features of a home.

## Initial Statistical Model:

![image](https://user-images.githubusercontent.com/77416319/128756741-6a7daf6e-7d7c-4d44-a008-6e984fb94fc6.png)

![image](https://user-images.githubusercontent.com/77416319/128756790-5b27056d-4e2e-4c55-b342-5340bb060669.png)

In the above models, there is low predictive power of housing prices after 2-3 million dollars. 

## Initial Model Summary:

R-square: 0.700

Number of P-values > 0.05: 0

Train RMSE: 202576

Test RMSE: 198126

Based on the results of the initial model, we can say 70% of the variation in price can be explained by the variables in the dataset. While the Train RMSE and Test RMSE are high, there isn't a big difference, which indicates that there isn't overfitting.

# Subsequent Model: 

After my initial model, I wanted to remove outliers that may have affected the distribution of data. I used the Z-Score formula to remove outliers in the dataset, so that any Z-score less than 3 were dropped. 

![image](https://user-images.githubusercontent.com/77416319/128773289-7ebaa887-c065-452a-a946-b25f7c4dc7dd.png)

![image](https://user-images.githubusercontent.com/77416319/128773331-2413535c-1bd8-47d5-a8cc-33d3c54caf20.png)

The removal of outliers from the dataset had a significant affect on the model.  
