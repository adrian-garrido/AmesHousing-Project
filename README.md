# Predicting Ames Housing Selling Prices

## Objective

Using the train dataset that contains data on properties from Ames, Iowa, create a model that can estimate the price of properties from the test dataset.

## Cleaning and EDA

Interpreted and changed the null values, by utilizing the dictionary provided. For the null values that were not mentioned in the dictionary, assumed the most common value for the column.

Changed categorical columns to numerical by putting integers representing quality instead of strings. Used 0 to represent absense of feature. For example, for Pool Quality, I assigned a 4 if it was excellent, a 3 if it was good, a 2 if it was average/typical, a 1 if it was poor, and 0 if the property did not have a pool.

For the Above Ground Living Area (GrLivArea) column, 2 outliers were deleted from the train dataset in order to achieve a better model. Utilized logarithmic transformations to deal with other outliers and to normalize distributions as well.

For the neighborhood data, a set of dummy columns was created, with binary values, that pointed to the neighborhood of each property.

I applied the logarithm to a few columns that had a substantial skew to the right, in order to normalize distributions. This also helped dealing with outliers.

## Features Selection

I used features that made logical sense to include, as well as features that had a high correlation with selling price. Overall I ended up using 66 features, including the 29 dummy variables that I got from the neighborhood data.

List of features used:

'LotFrontage', 'LotArea', 'Street', 'Alley', 'OverallQual', 'OverallCond', 'YearBuilt', 'YearRemod/Add', 'ExterCond', 'BsmtQual', 'BsmtCond', 'BsmtFinType1', 'BsmtFinSF1', 'BsmtFinType2', 'BsmtUnfSF', 'TotalBsmtSF', 'HeatingQC', 'CentralAir', '1stFlrSF', '2ndFlrSF', 'GrLivArea', 'BsmtFullBath', 'FullBath', 'HalfBath', 'KitchenAbvGr', 'TotRmsAbvGrd', 'Functional', 'Fireplaces', 'FireplaceQu', 'GarageType', 'GarageFinish', 'GarageCars', 'GarageArea', 'GarageQual', 'GarageCond', 'PavedDrive', 'WoodDeckSF', 'OpenPorchSF', 'EnclosedPorch', 'Blueste', 'BrDale', 'BrkSide', 'ClearCr', 'CollgCr', 'Crawfor', 'Edwards', 'Gilbert', 'Greens', 'GrnHill', 'IDOTRR', 'Landmrk', 'MeadowV', 'Mitchel', 'NAmes', 'NPkVill', 'NWAmes', 'NoRidge', 'NridgHt', 'OldTown', 'SWISU','Sawyer', 'SawyerW', 'Somerst', 'StoneBr', 'Timber', 'Veenker'

## Model Used

I ended up using a Lasso model, since it gave me the lowest root mean square error on Kaggle.


