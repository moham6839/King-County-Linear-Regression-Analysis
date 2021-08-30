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

R-square: 70% of the variation in price can be explained by the variables in the dataset.

Number of P-values > 0.05: 0

Train RMSE: 202576

Test RMSE: 198126

Based on the results of the initial model, we can say 70% of the variation in price can be explained by the variables in the dataset. While the Train RMSE and Test RMSE are high, there isn't a big difference, which indicates that there isn't overfitting.

# 2nd Model: 

After my initial model, I wanted to remove outliers that may have affected the distribution of data. I used the Z-Score formula to remove outliers in the dataset, so that any Z-score less than 3 were dropped. 

![image](https://user-images.githubusercontent.com/77416319/128773289-7ebaa887-c065-452a-a946-b25f7c4dc7dd.png)

![image](https://user-images.githubusercontent.com/77416319/128773331-2413535c-1bd8-47d5-a8cc-33d3c54caf20.png)

The removal of outliers from the dataset had a significant effect on the model. There is higher predictive power in housng prices than the initial model and normal distribution.

## Initial Model v. 2nd Model:

![image](https://user-images.githubusercontent.com/77416319/128804516-a9900823-2e6b-433b-b5f7-c5cb31213fef.png)

![image](https://user-images.githubusercontent.com/77416319/128804527-3f4a9b67-035f-4383-8c97-9ffd2c95c097.png)

Using bedrooms as an example, removing outliers had an impact on the distribution of data.

## 2nd Model Summary:

R-square: 68% of the variation in price can be explained by the variables in the dataset. 

Number of P-values > 0.05: 2 (Waterfront and Sqft_lot)

Train RMSE: 132551

Test RMSE: 135744

## Final Model:

Features that had poor correlation coefficients with housing price, p-values greater than 0.05, and high multicollinearity with other features were removed. The remaining features were log transformed and scaled in order to reduce skewness and have similar magnitudes.

## Final Model Results:

![image](https://user-images.githubusercontent.com/77416319/128873400-9e55276d-3b0d-4253-a312-12e5e2e40528.png)

![image](https://user-images.githubusercontent.com/77416319/128873459-408dad31-5617-4337-9047-7a319adf1198.png)

While the models shown above look similar to the 2nd model, the plot on the right shows more of a straight line and therefore shows more normal distribution. There is high predictive power in housing prices in this model.

## Final Model Summary:

R-square: 61% of the variation in price can be explained by the variables in the dataset. 

Number of P-values > 0.05: 0

Train RMSE: 0.624

Test RMSE: 0.638

In the final model summary, the r-square was lower than the first and second model. However, the Train RMSE and Test RMSE was significantly lower, and they were almost equal, which indicates that there isn't overfitting. 

## Conclusion: 

Based on the models conducted, the removal of outliers had a significant effect on the predictive power of housing prices. The main feature that showed a significant impact on housing prices is the square footage of a home. The bigger the square footage of a home, the higher the value of a home.

## Next Steps: 

More reaearch should be conducted to determine how the coronavirus pandemic has effected home values, as well as how the behavior of homebuyers and homeowners have changed since 2014-2015 and subsequently since the pandemic. A possible feature of homes that may be worth exploring when evaluating home prices is the type of material homes are made of, such as wood or concrete. 

