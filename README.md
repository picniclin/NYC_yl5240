# NYC_yl5240
NYC census data 1990-2010
dataset: geolytics_NYC_census_1990-2010.csv
2168 × 146： 146 variables, 2168 observations


1. Data source 
data source: Geolytics: Neighborhood Change Database (NACD)
(Link: http://demographics.geolytics.com/ncdb2010/default.aspx
introduction: http://guides.library.cornell.edu/c.php?g=31197&p=199283)

The best advantage of this database is that we could select ‘All years in 2010 boundaries’ and not need to be troubled by the tract change.
This selection allows us to compare data for various years within the exact same boundary definitions. The data for years  are recalculated and normalized, and the report uses the 2010 tract ID.  We can do actual apples-to-apples comparisons of historic data in 2010 tract definitions.
Before normalized, the observations of 1990, 2000 and 2010 are respectively 2216, 2217 and 2168.

2. Area and Geography
All the five counties of NYC are considered, and geography is for census tract level
36005 Bronx
36047 Kings
36061 New York
36081 Queens
36085 Richmond

3. Year selection
We focus on 1990-2010.
Decennial Census data is the first choice.
But starting in 2010, the Census stopped using the long form survey, and no longer reports the latest detailed demographic and socioeconomic data, including the data we need: income level and distribution, house value and rent. 
So we use the American Community Survey(ACS) 2006-2010 instead for this part of data.

4. Variable selection
We select 146 variables in total, 8 Geographical Variables and  138 Census Variables, for Census 1990, 2000, 2010 and ACS2006-2010.
The data of Census and ACS2006-2010 combined could be regarded as the data of 2010.

4.1 Geographical Variables
1) census tract code
2) zipcode
3) latitude and longitude
8 Geographical Variables:
* AREAKEY: Census Tract Identifier
* STATE: State
* STUSAB: State Abbreviation
* INTPTLAT: Internal Point(latitude)
* INTPTLON: Internal Point(longitude)
* ZCTA5: Zip Code Tabulation Area(5-digit)
* TCH90_10: Tract Change Code 1990-2010
* TCH00_10: Tract Change Code 2000-2010

4.2 Census Variables
1) total population 
2) poverty status: total poverty population AND prop. of poverty 
3) income
median/average family/household incomes
income distribution:  families/household with different income
* including 14-16 income level groups: 10000, 15000, 20000, 25000, 30000, 35000, 40000, (45000), 50000, 60000, 75000, 100000, 125000, 150000, (200000)
4) housing burden:
* median value of spec. owner occ. housing units
* median gross rent of spec. renter occ. housing units paying cash rent
* median selected mo. owner cost for spec. owner-coo. housing units with or without a mortgage
5) housing units
* vacant / owner occupied/ renter occupied housing units and persons in them

138 Census Variables:
1990：34 census variables
* 1 population + 2 poverty + 18 income + 4 housing burden + 9 housing units
2000: 52 census variables
* 1 population + 2 poverty + 36 income + 4 housing burden + 9 housing units
2010: 10 census variables
* 1 population + 9 housing units
ACS2006-2010:  42 census variables
* 2 poverty + 36 income + 4 housing burden 


Table. the column names of Census 1990/Census 2000/Census 2010/ACS 2006-2010
Variables
type
number
1990 
2000
2010
ACS 2006-2010
total population 
population
1/1/1/0
TRCTPOP9
TRCTPOP0
TRCTPOP1
(TRCTPOP1A)
Total persons below the poverty level,
Prop. of total persons below the poverty level
poverty 
2/2/0/2
POVRAT9N, POVRAT9
POVRAT0N, POVRAT0
-
POVRAT1AN, POVRAT1A
median family income，
average family income
income
2/2/0/2
MDFAMY9, 
FAVINC9
MDFAMY0
FAVINC0
-
MDFAMY1A
FAVINC1A
families with income : 

10000, 
15000, 
20000, 
25000, 
30000, 
35000, 
40000, 
45000,
50000, 
60000, 
75000, 
100000, 
125000, 
150000,
200000
income distribution
14/16/0/16
(14 groups:)

FALTY109, 
FALT159, 
FALT209, 
FALT259, 
FALT309, 
FALT359, 
FALT409,
 
FALT499, 
FALT609A, 
FALT759A, 
FALT1009, 
FALT1259, 
FALT1509, 
FALTMXB9
(16 groups:)

FAY0100,
FAY0150,
FAY0200,
FAY0250,
FAY0300,
FAY0350,
FAY0400,
FAY0450,
FAY0500,
FAY0600,
FAY0750,
FAY01000,
FAY01250,
FAY01500,
FAY02000,
FAY0M200
-
(16 groups:)

FAY0101A,
FAY0151A,
FAY0201A,
FAY0251A,
FAY0301A,
FAY0351A,
FAY0401A,
FAY0451A,
FAY0501A,
FAY0601A,
FAY0751A,
FAY01001A,
FAY01251A,
FAY01501A,
FAY02001A,
FAY0M201A
median HH income,
average HH income
income
2/2/0/2
MDHHY9,
AVHHIN9
MDHHY0,
AVHHIN0
-
MDHHY1A,
AVHHIN1A
households with income : 

10000, 
15000, 
20000, 
25000, 
30000, 
35000, 
40000, 
45000,
50000, 
60000, 
75000, 
100000, 
125000, 
150000,
200000
income distribution
0/16/0/16
NULL
(16 groups:)

THY0100,
THY0150,
THY0200,
THY0250,
THY0300,
THY0350,
THY0400,
THY0450,
THY0500,
THY0600,
THY0750,
THY01000,
THY01250,
THY01500,
THY02000,
THY0M200
-
(16 groups:)

THY0101A,
THY0151A,
THY0201A,
THY0251A,
THY0301A,
THY0351A,
THY0401A,
THY0451A,
THY0501A,
THY0601A,
THY0751A,
THY01001A,
THY01251A,
THY01501A,
THY02001A,
THY0M201A
median value of spec. owner occ. housing units
housing burden
1/1/0/1
MDVALHS9
MDVALHS0
-
MDVALHS1A
median gross rent of spec. renter occ. housing units paying cash rent
housing burden
1/1/0/1
MDGRENT9
MDGRENT0
-
MDGRENT1A
median selected mo. owner cost for spec. owner-coo. housing units with a mortgage;
without a mortgage
housing burden
2/2/0/2
MCSMORT9,
MCSNMOR9
MCSMORT0,
MCSNMOR0
-
MCSMORT1A,
MCSNMOR1A
Total occupied housing units,
Total vacant housing units,
Total renter-occ. housing units,
Total owner-occ. housing units,
Total spec. renter-occ. housing units,
Total spec. owner-occ. housing units,
Persons in owner-occ. housing units,
Persons in occupied rental units
housing units
9/9/9/0
OCCHU9,
VACHU9,
RNTOCC9,
OWNOCC9,
SPRNTOC9,
SPOWNOC9,
PRSOCU9,
PRSOWNU9,
PRSRNTU9
OCCHU0,
VACHU0,
RNTOCC0,
OWNOCC0,
SPRNTOC0,
SPOWNOC0,
PRSOCU0,
PRSOWNU0,
PRSRNTU0
OCCHU1,
VACHU1,
RNTOCC1,
OWNOCC1,
SPRNTOC1,
SPOWNOC1,
PRSOCU1,
PRSOWNU1,
PRSRNTU1
（OCCHU1A,
VACHU1A,
RNTOCC1A,
OWNOCC1A,
SPRNTOC1A,
SPOWNOC1A,
PRSOCU1A,
PRSOWNU1A,
PRSRNTU1A）

