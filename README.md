# Openclassroom-projet4

## Description : 

I work in the city of Seattle. To achieve its goal of a carbon-neutral city by 2050, my team is taking a close look at the consumption and emissions of non-residential buildings.

With the data provided, I want to attempt to predict the CO2 emissions and total energy consumption of non-residential buildings for which they have not yet been measured.

## Environnement :

Three notebook.

jeu de données : https://s3.eu-west-1.amazonaws.com/course.oc-static.com/projects/Data_Scientist_P4/2016_Building_Energy_Benchmarking.csv

## Content:

#### I –  analyse exploratoire.
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

#### II – Choix du modèles de machine learning.

##### 1 - Prédiction pour la target SiteEnergyUse(kBtu) avec ENERGYSTARscore.
###### Cross validation with metric MSE, MAE, R2 on models : DummyRegressor, LinearRegression, Ridge, Lasso, RandomForestRegressor, GradientBoostingRegressor.
###### By optimizing with gridsearch the two best performing models selected: RandomForestRegressor, GradientBoostingRegressor.
###### we can conclude that the best model is GradientBoostingRegressor with parameters max_depth=80, random_state=42, subsample=0.5.

###### 2 – Prédiction pour la target SiteEnergyUse(kBtu) sans ENERGYSTARscore. 

###### 3 –  Prédiction pour la target TotalGHGEmissions avec ENERGYSTARscore.
###### 4  – Prédiction pour la target TotalGHGEmissions sans ENERGYSTARscore. 
