# New-York-Taxi-Analysis
#### Datasets are yellow and green taxis records from January to June of 2020, derived from NYC Taxi & Limousine Commission. 
(Link: https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page)

## Tasks: 

### Visualization
1. Bokeh and shapefile libraries are used to generate geospatial visualizations.
2. Several attributes are analyzed pairly
    1. Relationship between pickup location and dropoff location: most passengers would like to travel for short distance. Through the distribution of travel distance, we know most trips are below 20 miles.
    2. Relationship between payment type and dropoff location: people living in the outer borough prefer cash payment, while people living in Mahatten prefer card payment. 
    3. Relationship between tip fraction (ratio of tips to total amount) and dropoff location: no obvoius distribution found. In other word, passengers are likely to pay a fixed-rate tips. 

### Machine Learning Modeling (Binary classification: is it a tip-given ride?)
1. Preprocess: instances in 0.95 quantile are remained (remove outliers). Trip distance, passenger number, subcharges, pickup and dropoff locations are selected as our attribtues, and "is tipped" is the label. 
2. Modeling: 2 classification methods are implemented, logistic regression (linear model) and random forest (non-linear model). 
3. Evaluation: regular evaluation applied (i.e. normalized confusion matrix, ROC-AUC curve and learning curve), where the conclusion is that random forest is outpreformed than logistic regression. 

## Consolidations:
1. Do pairwise correlation before selecting attributes, avoiding effect of correlations
2. Apply grid search or randomized search to find out best hyperparameter sets, boosting accuracy.
3. Though modeling is time-consuming with all attributes, feature selection (i.e. select k best) could also be applied to boost time effectiveness. 
4. Two raw models both failed to predict FP in confusion matrices, which is still a unknown answer.
