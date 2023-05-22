# Openclassroom-projet4

## Description : 

I work in the city of Seattle. To achieve its goal of a carbon-neutral city by 2050, my team is taking a close look at the consumption and emissions of non-residential buildings.

With the data provided, I want to attempt to predict the CO2 emissions and total energy consumption of non-residential buildings for which they have not yet been measured.

## Environnement :

Three notebook.

jeu de données : https://s3.eu-west-1.amazonaws.com/course.oc-static.com/projects/Data_Scientist_P4/2016_Building_Energy_Benchmarking.csv

## Content:

#### I –  analyse exploratoire.
###### 1 - Analyse
des colonnes avec 80% de valeurs nulles .
les lignes corespondants a des immeubles residentiels.
Des valeurs en dessous de zero pour les variables : Electricity(kBtu), SteamUse(kBtu), NaturalGas(kBtu) .
Des valeurs en dessous ou égal à zero pour les targets 
Imputation des valeurs pour le feature ENERGYSTARscore par la mediane pour chaque catégorie de batiments.
matrix corr

###### 2 - Features engineering
Create a column with the values giving the age of the buildings.
#
Normalization of variables.
#
And create ratios for the energy sources emitted.
#
Switch targets to logarithmic (distribution) scale.
#
Hot encoding for BuildingType, PrimaryPropertyType, Neighborhood, LargestPropertyUseType.

#### II – Choix du modèles de machine learning.

###### 2 – Prédiction pour la target SiteEnergyUse(kBtu) avec ENERGYSTARscore.
Cross validation with metric MSE, MAE, R2 on models : DummyRegressor, LinearRegression, Ridge, Lasso, RandomForestRegressor, GradientBoostingRegressor.
#
By optimizing with gridsearch the two best performing models selected: RandomForestRegressor, GradientBoostingRegressor.
we can conclude that the best model is GradientBoostingRegressor with parameters max_depth=80, random_state=42, subsample=0.5.

###### 3 – Prédiction pour la target SiteEnergyUse(kBtu) sans ENERGYSTARscore. 

###### 4 –  Prédiction pour la target TotalGHGEmissions avec ENERGYSTARscore.
###### 5  – Prédiction pour la target TotalGHGEmissions sans ENERGYSTARscore. 
