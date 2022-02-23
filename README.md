# Country_Segmentation

* Run a script'NGO-Clustering assignment' with 'Country-data.csv' file as input

## Problem Statement:
HELP international NGO has raised fund to fight poverty, providing basic amenities to the people of
countries who are in direst need of it. Data for all countries with some essential variables is given. We need
to cluster countries best on various factors such as income, gdpp, child mortality rate to get countries
which are in need of fund.

## Analysis approach - 
#### 1. Reading and understanding data:
- First step is reading and understanding data. Data contains 167 rows and 10 columns.
- We then checked summary and basic info such as data types and null values.
- All columns except country are numerical.
#### 2. Cleaning and visualizing data:
- In data dictionary we have given that columns ‘export’, ‘import’, ‘health’ are as percentage of
‘gdpp’, so we converted them in values.
- We then checked for null values present in data but luckily there were no null values in data.
- Next we visualized data by plotting correlation heatmap between columns and we got to know that
income and gdpp is highly correlated. On other hand total fertility and child mortality is highly
correlated.
- We plotted boxplot to understand outliers in data respectively. There were outliers in almost all
columns.
#### 3. Preparing data for modelling:
- We capped outliers in all the columns by quantile method.
- We then Scaled variables in the data so as to standardize values by using StandardScaler from
Sklearn
- We also run Hopkins test and score came out to be > 0.5 so data has cluster tendency.
- 
#### 4. Model Building:
Here we have two methods to build a model
1. K-Means
- we calculated optimum number of clusters by:
o 1) Elbow curve method
o 2) Silhouette method
- We got 3 as optimum cluster number from it.
- Then using KMeans from sklearn we formed clusters of countries and assigned label to them.
2. Hierarchical clustering:
- In this method we plotted dendrograms for different methods such as single linkage, complete
linkage, average linkage. Since complete linkage method was giving better insights we chose that
method and we chose 4 as optimum clusters.
- Then using cut_tree from scipy we formed clusters of countries and assigned label to them.
- 
#### 5. Analysis and inferences:
For K-means clustering-
- We used scatter plot to see how different cluster groups are located.
- We plotted boxplot for (income, gdpp, child mortality rate) vs clusters groups to get insights which
countries/cluster group is need to target.
- We got to know following top 10 countries are in real need which belonged to cluster group 2:
1) 'Burundi'
2) 'Liberia'
3) 'Congo, Dem. Rep.'
4) 'Niger'
5) 'Sierra Leone'
6) 'Madagascar'
7) 'Mozambique'
8) 'Central African Republic'
9) 'Malawi'
10) 'Eritrea'
For Hierarchical clustering-
- Here also we plotted scatter plot to see how cluster groups are located.
Also we plotted boxplot for (income, gdpp, child mortality rate) vs clusters to get insights that
which group of clusters are in real need.
- We get to know that following countries are in real need which belongs to cluster group 0:
1) 'Burundi'
2) 'Congo, Dem. Rep.'
3) 'Niger.'
4) 'Sierra Leone'
5) 'Mozambique'
6) 'Central African Republic'
7) 'Malawi'
8) 'Togo'
9) 'Guinea-Bissau'
10) 'Afghanistan'

#### Note : As data was not that big so choosing hierarchical method is good choice to go with as it gives better results. Also in K-Means clustering initial assumption of centroids make this method little bit less relevant than hierarchical method.
