# Openclassroom-projet4

## Description : 

I work in the city of Seattle. To achieve its goal of a carbon-neutral city by 2050, my team is taking a close look at the consumption and emissions of non-residential buildings.

With the data provided, I want to attempt to predict the CO2 emissions and total energy consumption of non-residential buildings for which they have not yet been measured.

## Environnement :

Three notebook.

jeu de données : https://s3.eu-west-1.amazonaws.com/course.oc-static.com/projects/Data_Scientist_P4/2016_Building_Energy_Benchmarking.csv

## Content:

#### I –  exploratory analysis.
##### 1 - Analyse
###### Removing columns with 80% null values, lines corresponding to residential buildings, Values below zero for the variables coresponding to the emissions, Values less than or equal to zero for targets.
###### Imputation of values for the ENERGYSTARscore feature by the median for each building category.
###### Matrix correlation

##### 2 - Features engineering
###### Create a column with the values giving the age of the buildings.
###### Normalization of variables.
###### And create ratios for the energy sources emitted.
###### Switch targets to logarithmic (distribution) scale.
###### Hot encoding for BuildingType, PrimaryPropertyType, Neighborhood, LargestPropertyUseType.

#### II – Choice of machine learning models.

##### 1 - Prediction for SiteEnergyUse(kBtu) target with ENERGYSTARscore.
###### Cross validation with metric MSE, MAE, R2 on models : DummyRegressor, LinearRegression, Ridge, Lasso, RandomForestRegressor, GradientBoostingRegressor.
###### By optimizing with gridsearch the two best performing models selected: RandomForestRegressor, GradientBoostingRegressor.
###### We can conclude that the best model is GradientBoostingRegressor with parameters max_depth=80, random_state=42, subsample=0.5.

##### 2 – Prediction for SiteEnergyUse(kBtu) target without ENERGYSTARscore. 
###### Cross validation with metric MSE, MAE, R2 on models : DummyRegressor, LinearRegression, Ridge, Lasso, RandomForestRegressor, GradientBoostingRegressor.
###### By optimizing with gridsearch the two best performing models selected: RandomForestRegressor, GradientBoostingRegressor.
###### We can conclude that the best model is GradientBoostingRegressor with parameters max_depth=80, random_state=42, subsample=0.5.
###### We can conclude that the ENERGYSTARscore variable has an impact on the prediction performance with a score of 0.81 with and 0.76 without.



##### 3 –  Prediction for the TotalGHGEmissions target with ENERGYSTARscore.
###### Cross validation with metric MSE, MAE, R2 on models : DummyRegressor, LinearRegression, Ridge, Lasso, RandomForestRegressor, GradientBoostingRegressor.
###### By optimizing with gridsearch the two best performing models selected: RandomForestRegressor, GradientBoostingRegressor.
###### We can conclude that the best model is GradientBoostingRegressor with parameters max_depth=80, random_state=42, subsample=0.5.

##### 4  – Prediction for TotalGHGEmissions target without ENERGYSTARscore.
###### Cross validation with metric MSE, MAE, R2 on models : DummyRegressor, LinearRegression, Ridge, Lasso, RandomForestRegressor, GradientBoostingRegressor.
###### By optimizing with gridsearch the two best performing models selected: RandomForestRegressor, GradientBoostingRegressor.
###### We can conclude that the best model is GradientBoostingRegressor with parameters max_depth=80, random_state=42, subsample=0.5.
###### we can conclude that the ENERGYSTARscore variable has an impact on the prediction performance with a score of 0,76 with and 0.67 without.
