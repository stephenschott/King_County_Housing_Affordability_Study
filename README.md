# King County, WA Housing Affordability Study
![Seattle](presentation_image_copy.png)

## Problem Statement
From 2000 to 2020, the median home value in King County, WA increased by approximately 190%. 
## Data Gathering
I gathered my data from the US Census, Zillow, and King County Trend of Housing Costs in Relation to Income.
## Methods
I gathered 19 years of data for median home value, median household income, population, and housing units available. After uploading the dataframe and minor cleaning, I checked out two multiple line graphs: one with the raw data and one that was based on each year's percent change from base year 2000. From there I moved to modeling.
## Modeling
I first created X and y variables, with X equal to median household income, population, and housing units; y was equal to median home value.  Next I created X_train, y_train, X_test, and y_test, and performed a train_test_split. I ran two different models: linear regression and random forest. I scaled the data before running the models as each variable had significantly different scales.  Then I ran a simple linear regression model and checked some scatter plots for the model predicted values vs actual values.  I also did this for each individual variable just to see what they looked like.  Next I ran the random forest model through a gridsearch, which determined the best estimator was n_estimators = 60.  
## Results
I initially had my test size set to .2, which resulted in train/test scores of .9 for my linear regression. My random forest model got train/test scores of .96 and .56, respectively.  This seemed weird, and I realized because I have such a small dataset (19 rows), my X_test was only a sample size of 3 or 4.  This is not sufficient.  So I changed my test size to .33, which is still only about 6, but it's a little better.  My linear regression model returned scores of .95 and .83, and random forest scores were .98 and .7.  This is still a bit odd, but more in line what would be considered realistic.
## Conclusion
I don’t feel terrible about a model predicting .83 accuracy, but not super great either. I think the reality is that going further back in time with the data would be very helpful; 19 rows is very limiting. I only have 6 points of data in my test set, which is better than nothing but it’s not a lot to test on. Unfortunately, collecting data was probably my most time-consuming part of this project and obtaining more was not possible with the time constraints.
The project wasn’t a bust, though. In coordination with population growth generally, the trend did show that increasing incomes coordinated more with home values. I recommended that the county continue to increase housing supply to get ahead of the demand and help reduce home values. I also recommended more research to include rental rates, and a comparison of proportion of housing units for ownership vs for rental throughout the county.
## Data Dictionary
|Feature|Type|Dataset|Description|
|----|----|----|----|
|index|int|df|numbered index of the rows|
|year|int|df|year the data is from|
|housing_units|int|df|number of housing units available to live in (single fam. houses, apartments, condos, etc)|
|med_home_val|int|df|median home value|
|population|int|df|population|
|med_income|int|df|median household income|