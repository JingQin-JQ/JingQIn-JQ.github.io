---
layout: post
title: Collect Data
tags: 
-Learn from Kaggle project
---
Get basic information from data


In the Kaggle, a large part of the problems are prediction related, Here most examples are from :
Give me some credit 
<https://www.kaggle.com/c/GiveMeSomeCredit>
and 
New York taxi duration.
<https://www.kaggle.com/c/nyc-taxi-trip-duration>

Data is usually provided in CSV format, normally I use pandas do deal with it,  so first step always is :

``` python
import pandas as pd

df_train = pd.read_csv('../New York City Taxi Trip Duration/train.csv')
df_test = pd.read_csv('../New York City Taxi Trip Duration/test.csv')

combine = [df_train, df_test]
df_train.head()
```

### Index

We can set index in pandas and get data from dataframe as we needed.

``` python
df_try = df_train.set_index('id')
df_try.head()
```
#### loc and iloc

Both loc and iloc can slice data

loc works on labels in the index.

iloc works on the positions in the index (so it only takes integers).

work as:

``` python
df_try.iloc[[3,5,7]]
df_try.loc[:'id3858529']
```
### Conditional selection of required data
We can choose data as we needed, bu using coditions, such as:

```
df_train['vendor_id']==2
```
this will created a pandas series of boolean about if sample can fit in this conditions.

Then we can use this series to select data we need, even columns we would like to show.

```python 
df_train[(df_train['vendor_id']== 2)][['pickup_longitude','pickup_latitude']]
```
### Group by
Group by need to followed by a reduce like function: such as mean, sum, size or describe.

``` python 
df_train.groupby(df_train['passenger_count'])['trip_duration'].describe()
df_train['trip_duration'].groupby(df_train['passenger_count']).mean()
```
## Understand Data
columns: gives all names of columns

shape: gives number of samples and number of columns

dtypes: gives types of data from diffrent columns

info(): gives information of all data,as below:

```
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 1458644 entries, 0 to 1458643
Data columns (total 11 columns):
id                    1458644 non-null object
vendor_id             1458644 non-null int64
pickup_datetime       1458644 non-null object
dropoff_datetime      1458644 non-null object
passenger_count       1458644 non-null int64
pickup_longitude      1458644 non-null float64
pickup_latitude       1458644 non-null float64
dropoff_longitude     1458644 non-null float64
dropoff_latitude      1458644 non-null float64
store_and_fwd_flag    1458644 non-null object
trip_duration         1458644 non-null int64
dtypes: float64(4), int64(3), object(4)
memory usage: 122.4+ MB
```
describe(): gives count, mean, std, min, 25%, 50%, 75%, max of all data in diffrent columns.

	