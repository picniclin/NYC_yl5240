The clean process could be found on [civic_clean&descripitive_Yuwei.ipynb](https://github.com/picniclin/NYC_yl5240/blob/master/civic_data_clean_Yuwei_1128.ipynb)

Data set instructions:
## 1. raw dataset
[geolytics_nyc_census_1990_2010.csv](https://github.com/picniclin/NYC_yl5240/blob/master/data/geolytics_nyc_census_1990_2010.csv) : the dataset exported from Geolytics: Neighborhood Change Database ([NACD](http://demographics.geolytics.com/ncdb2010/default.aspx)).
It has 2168 rows, meaning 2168 tracts.

## 2. clean dataset
[civic_census.csv](https://github.com/picniclin/NYC_yl5240/blob/master/data/civic_census.csv):  **2077 rows, having dropped rows with 0 values of income, rent, and entropy index in the 2168 tracts**.
clean version of geolytics_nyc_census_1990_2010.csv

It has the variales below for each census tract in NYC in 1990, 2000, 2010, as well as change rate between 1990-2000, 2000-2010, and 1990-2010 :
- median family income income, and 
- median rent
- ratio of rent to income
- entropy index
- rent units, meaning renter-occupied units

## 3. Normalized and no-outliers dataset

- normized dataset: [civic_census_normed.csv](https://github.com/picniclin/NYC_yl5240/blob/master/data/civic_census_normed.csv), 2077rows
def normalize(x):
    norm = (x - x.min())/(x.max() - x.min())
    return norm

- no-outliers dataset: [civic_census_dropoutliers.csv](https://github.com/picniclin/NYC_yl5240/blob/master/data/civic_census_dropoutliers.csv), 1770rows
def outlier(x):
    outlier = np.mean(x) + 3 * np.std(x)
    return outlier

- normized and no-outliers dataset: [civic_census_normed_dropoutliers.csv](https://github.com/picniclin/NYC_yl5240/blob/master/data/civic_census_normed_dropoutliers.csv), 1770rows



![change](https://github.com/picniclin/NYC_yl5240/blob/master/data/change1990-2010.png)
![change2](https://github.com/picniclin/NYC_yl5240/blob/master/data/change1990-2010_2.png)



