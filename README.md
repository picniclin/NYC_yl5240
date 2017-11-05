# NYC census data 1990-2010
## Dataset: geolytics_NYC_census_1990-2010.csv
Dataset.shape: 2168 × 146

146 variables, 2168 observations


In the variables listed in part 4, the key variables we need are **census tract code and their latitude and longitude, total population, median families incomes, families with different income level, median gross rent**.


## 1. Data source 
## Geolytics, Neighborhood Change Database (NACD)

Link: http://demographics.geolytics.com/ncdb2010/default.aspx

introduction: http://guides.library.cornell.edu/c.php?g=31197&p=199283

This dataset includes the Census data of 1970, 1980, 1990 and 2000 at the census tract level.


**The reaseon we choose this dataset is that there is a selection ‘All years in 2010 boundaries’ in it. Hence, we do not need to be troubled by the tract change in the 30 years' period.**


The data of 1990 and 2000 has been recalculated and normalized according to the 2010 tract ID. With this selection, we could do actual comparisons of historic data by the exact same tract boundary definitions for different years. (see [here](http://guides.library.cornell.edu/c.php?g=31197&p=199283) )


Before normalized, the observations of 1990, 2000 and 2010 are respectively 2216, 2217 and 2168.

## 2. Area and Geography
All the five counties of NYC are considered, and geography is considered at the census tract level.


The countyID of the five counties:
- 36005 Bronx
- 36047 Kings
- 36061 New York
- 36081 Queens
- 36085 Richmond

## 3. Year and data selection
We focus on 1990-2010. 

Decennial Census data is the first choice.


But the Census stopped using the long form survey from 2010. Since then, the detailed demographic and socioeconomic data has not been available in the census reports, including the data we need: **income level, income distribution, house value and rent**. 


So we use the **American Community Survey(ACS) 2006-2010** instead for this part of data.
The data of Census 2010 and ACS2006-2010 combined could be regarded as the data of 2010.

## 4. Variable selection
We select **146 variables in total, 8 Geographical Variables and  138 Census Variables**, for Census 1990, 2000, 2010 and ACS2006-2010.


For census variables, the last first or two characters could used to distinguish the four data source:
- 9 means Census 1990
- 0 means Census 2000
- 1 means Census 2010
- 1A means Census ACS2006-2010


The variables and their columns names are listed below.


### 4.1 Geographical Variables
**Eight Geographical Variables**:

#### 1) census tract code
Census Tract Identifier
- AREAKEY


State
- STATE


State Abbreviation
- STUSAB


Tract Change Code 1990-2010
- TCH90_10


Tract Change Code 2000-2010
- TCH00_10


#### 2) zipcode
Zip Code Tabulation Area(5-digit)
- ZCTA5


#### 3) latitude and longitude
Internal Point(latitude)
- INTPTLAT


Internal Point(longitude)
- INTPTLON




### 4.2 Census Variables
**138 Census Variables** for four data source are included.

- **Census 1990(34)** : 1 population + 2 poverty + 4 median income + 14 families income level groups + 4 housing burden(including median rent) + 9 housing units

- **Census 2000(52)** : 1 population + 2 poverty + 4 median income + 16 families income level groups + 16 households income level groups + 4 housing burden(including median rent) + 9 housing units

- **Census 2010(10)** :1 population + 9 housing units

- **ACS2006-2010(42)** : 2 poverty + 4 median income + 16 families income level groups + 16 households income level groups + 4 housing burden(including median rent)


In 1990 data, there is no data about households with different incomes.
In 2010 data, due to the change of census data report mentioned above, we combine the variables of Census 2000 and ACS2006-2010 together as the 2010 variables.



#### 1) total population 
- TRCTPOP9, TRCTPOP0, TRCTPOP1

#### 2) poverty
Total persons below the poverty level
- POVRAT9N, POVRAT0N, POVRAT1AN

Prop. of total persons below the poverty level
- POVRAT9, POVRAT0, POVRAT1A


#### 3) median income
Median familiy inc.
- MDFAMY9, MDFAMY0, MDFAMY1A

Average inc. per family
- FAVINC9, FAVINC0, FAVINC1A

Median HH. inc.
- MDHHY9,MDHHY0, MDHHY1A

Average HH. inc.
- AVHHIN9, AVHHIN0, AVHHIN1A


#### 4) income-level groups

Since 2000, 16 income-level groups has been divided. 


There are differences in 1990 data. 


First, it **lack of $45,000-inc.-division and $200,000-inc.-division**, so we select 14 income-level groups for 1990 data, which means $40,00-49,999 in 1990 corresponding to $40,000-44,999 + $45,000-49,999 in 2000 and 2010, $150,000+ in 1990 corresponding to $150,000-199,999 + $200,000+ in 2000 and 2010. 


Second, there are no households income distribution data in 1990.


**Thus, if we want to compare thirty years' data together, we have to do comparision of families income and based on 14 income-level groups selected in 1990 data.**


##### 4.1)1990 families income(14 groups)

Families with less than $10000  inc., 

$10000-14999 inc., 

$15000-19999 inc., 

$20000-24999 inc.,

$25000-29999 inc.,

$30000-34999 inc.,

$35000-39999 inc.,

$40000-49999 inc.,

$50000-59999 inc.,

$60000-74999 inc.,

$75000-99999 inc.,

$100000-124999 inc.,

$125000-149999 inc.,

$150000+ inc.

- FALTY109, FALT159, FALT209, FALT259, FALT309, FALT359, FALT409, FALT499, FALT609A, FALT759A, FALT1009, FALT1259, FALT1509, FALTMXB9


##### 4.2)2000 families/households income(16 groups + 16 groups): 

Families/Households with less than $10000  inc., 

$10000-14999 inc., 

$15000-19999 inc., 

$20000-24999 inc.,

$25000-29999 inc.,

$30000-34999 inc.,

$35000-39999 inc.,

$40000-44999 inc.,

$45000-49999 inc.,

$50000-59999 inc.,

$60000-74999 inc.,

$75000-99999 inc.,

$100000-124999 inc.,

$125000-149999 inc.,

$150000-199999 inc.,

$200000+ inc.

*families income*
- FAY0100,FAY0150,FAY0200,FAY0250,FAY0300,FAY0350,FAY0400,FAY0450,FAY0500,FAY0600,FAY0750,FAY01000,FAY01250,FAY01500,FAY02000,FAY0M200

*households income*
- THY0100,THY0150,THY0200,THY0250,THY0300,THY0350,THY0400,THY0450,THY0500,THY0600,THY0750,THY01000,THY01250,THY01500,THY02000,THY0M200


##### 4.3)2010 families/households income(16 groups + 16 groups): 

Families/Households with less than $10000  inc., 

$10000-14999 inc., 

$15000-19999 inc., 

$20000-24999 inc.,

$25000-29999 inc.,

$30000-34999 inc.,

$35000-39999 inc.,

$40000-44999 inc.,

$45000-49999 inc.,

$50000-59999 inc.,

$60000-74999 inc.,

$75000-99999 inc.,

$100000-124999 inc.,

$125000-149999 inc.,

$150000-199999 inc.,

$200000+ inc.



*families income*
- FAY0101A,FAY0151A,FAY0201A,FAY0251A,FAY0301A,FAY0351A,FAY0401A,FAY0451A,FAY0501A,FAY0601A,FAY0751A,FAY01001A,FAY01251A,FAY01501A,FAY02001A,FAY0M201A

*households income*
- THY0101A,THY0151A,THY0201A,THY0251A,THY0301A,THY0351A,THY0401A,THY0451A,THY0501A,THY0601A,THY0751A,THY01001A,THY01251A,THY01501A,THY02001A,THY0M201A



#### 5) housing burden:
Median gross rent of spec. renter occ. housing units paying cash rent
- MDGRENT9, MDGRENT0, MDGRENT1A 

Median value of spec. owner occ. housing units
- MDVALHS9, MDVALHS0, MDVALHS1A 



Median selected mo. owner cost for spec. owner-coo. housing units with a mortgage
- MCSMORT9, MCSMORT0, MCSMORT1A

Median selected mo. owner cost for spec. owner-coo. housing units with a mortgage
MCSNMOR9, MCSNMOR0, MCSNMOR1A



#### 6) housing units
vacant/ owner occupied/ renter occupied housing units and persons in them


Total occupied housing units
- OCCHU9, OCCHU0, OCCHU1



Total vacant housing units
- VACHU9, VACHU0, VACHU1



Total renter-occ. housing units
- RNTOCC9, RNTOCC0, RNTOCC1



Total owner-occ. housing units
- OWNOCC9, OWNOCC0, OWNOCC1



Total spec. renter-occ. housing units
- SPRNTOC9, SPRNTOC0, SPRNTOC1


Total spec. owner-occ. housing units
- SPOWNOC9, SPOWNOC0, SPOWNOC1



Persons in occupied housing units
- PRSOCU9, PRSOCU0, PRSOCU1



Persons in owner-occ. housing units
- PRSOWNU9, PRSOWNU0, PRSOCU1



Persons in occupied rental units
- PRSRNTU9, PRSRNTU0, PRSRNTU1





