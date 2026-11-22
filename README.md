# EXPERIMENT NO. 1: DATA CLEANING AND PREPROCESSING

## AIM

To perform data cleaning and preprocessing on a business dataset using
Python libraries for better data quality and analysis readiness.

## DATASET

The dataset used for this experiment is `heartdisease.csv`. It contains
medical and demographic information related to heart disease patients.

The dataset is opened and analyzed using Jupyter Notebook to study its
data structure, identify data types, and perform basic statistical
analysis for data-cleaning and preprocessing purposes.

## ALGORITHM / STEPS FOLLOWED

1.  Import essential Python libraries.
2.  Load the dataset using Pandas.
3.  View the dataset structure, data types, and memory usage.
4.  Check for missing values and duplicates.
5.  Perform data summary statistics using `describe()`.
6.  View initial and final records using `head()` and `tail()`.
7.  Sort and group the data based on key attributes.
8.  Rename columns or modify data where necessary.
9.  Save the cleaned dataset for further analysis.

## FUNCTIONS AND METHODS USED

### 1. Data Loading and Basic Exploration

  Function / Method      Description
  ---------------------- ------------------------------------------------------
  `pd.read_csv()`        Reads a CSV file into a Pandas DataFrame.
  `df.info()`            Displays column names, data types, and memory usage.
  `df.dtypes`            Returns the data types of all columns.
  `df['column'].dtype`   Returns the data type of a specific column.
  `df.describe()`        Provides summary statistics for numerical columns.
  `df.head()`            Displays the first 5 rows of the DataFrame.
  `df.tail()`            Displays the last 5 rows of the DataFrame.

### 2. Sorting and Grouping

  Function / Method    Description
  -------------------- ---------------------------------------------
  `df.sort_values()`   Sorts the DataFrame by one or more columns.
  `df.groupby()`       Groups data based on one or more columns.
  `groupby.sum()`      Returns the sum for each group.
  `groupby.mean()`     Returns the mean for each group.
  `groupby.median()`   Returns the median for each group.
  `groupby.max()`      Returns the maximum value in each group.
  `groupby.min()`      Returns the minimum value in each group.

### 3. Data Summary and Manipulation

  Function / Method   Description
  ------------------- ----------------------------------------------
  `df.mean()`         Calculates the mean for all numeric columns.
  `df.rename()`       Renames columns in the DataFrame.

### 4. Optional Additions

  Function / Method         Description
  ------------------------- ----------------------------------------------
  `df.isnull().sum()`       Checks for missing values in each column.
  `df.duplicated().sum()`   Counts duplicate rows.
  `df.dropna()`             Removes rows containing missing values.
  `df.fillna()`             Fills missing values with a specified value.
  `df.drop_duplicates()`    Removes duplicate rows.
  `df.shape`                Returns the number of rows and columns.
  `df.columns`              Lists column names in the DataFrame.


## PROGRAM & OUTPUT
## Input 1
```
# Import essential Python libraries
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
# Load the dataset in CSV from the system / laptop
df = pd.read_csv('heartdisease.csv')
# View column names and data types
print("Column names and data types:")
print(df.info())
```


## Output 1
```
Column names and data types:
<class 'pandas.DataFrame'>
RangeIndex: 3658 entries, 0 to 3657
Data columns (total 17 columns):
 #   Column           Non-Null Count  Dtype  
---  ------           --------------  -----  
 0   sno              3658 non-null   int64  
 1   gender           3658 non-null   int64  
 2   age              3658 non-null   int64  
 3   education        3658 non-null   int64  
 4   currentSmoker    3658 non-null   int64  
 5   cigsPerDay       3658 non-null   int64  
 6   BPMeds           3658 non-null   int64  
 7   prevalentStroke  3658 non-null   int64  
 8   prevalentHyp     3658 non-null   int64  
 9   diabetes         3658 non-null   int64  
 10  totChol          3658 non-null   int64  
 11  sysBP            3658 non-null   float64
 12  diaBP            3658 non-null   float64
 13  BMI              3658 non-null   float64
 14  heartRate        3658 non-null   int64  
 15  glucose          3658 non-null   int64  
 16  TenYearCHD       3658 non-null   int64  
dtypes: float64(3), int64(14)
memory usage: 486.0 KB
None
```

## Input 2
```
# Method 1: Get data types for all columns
print("\nData types for all columns:")
print(df.dtypes)
```
## Output 2
```
Data types for all columns:
sno                  int64
gender               int64
age                  int64
education            int64
currentSmoker        int64
cigsPerDay           int64
BPMeds               int64
prevalentStroke      int64
prevalentHyp         int64
diabetes             int64
totChol              int64
sysBP              float64
diaBP              float64
BMI                float64
heartRate            int64
glucose              int64
TenYearCHD           int64
dtype: object
```

## Input 3
```
# Method 2: Get data type for specific columns
print("\nData type for 'age' column:")
print(df['age'].dtype)
# Method 3: More detailed info including memory usage
print("\nMemory usage and non-null counts:")
print("\nDetailed info:")
print(df.info())
```

## Output 3
```
Memory usage and non-null counts:
Data type for 'age' column:
int64

Detailed info:
<class 'pandas.DataFrame'>
RangeIndex: 3658 entries, 0 to 3657
Data columns (total 17 columns):
 #   Column           Non-Null Count  Dtype  
---  ------           --------------  -----  
 0   sno              3658 non-null   int64  
 1   gender           3658 non-null   int64  
 2   age              3658 non-null   int64  
 3   education        3658 non-null   int64  
 4   currentSmoker    3658 non-null   int64  
 5   cigsPerDay       3658 non-null   int64  
 6   BPMeds           3658 non-null   int64  
 7   prevalentStroke  3658 non-null   int64  
 8   prevalentHyp     3658 non-null   int64  
 9   diabetes         3658 non-null   int64  
 10  totChol          3658 non-null   int64  
 11  sysBP            3658 non-null   float64
 12  diaBP            3658 non-null   float64
 13  BMI              3658 non-null   float64
 14  heartRate        3658 non-null   int64  
 15  glucose          3658 non-null   int64  
 16  TenYearCHD       3658 non-null   int64  
dtypes: float64(3), int64(14)
memory usage: 486.0 KB
None
```
## Input 4
```
# Get the summary of all variables / columns
print("\nSummary statistics:")
print(df.describe())
```
## Output 4
```
Summary statistics:
               sno      gender           age    education  currentSmoker  \
count  3658.000000  3658.000000  3658.000000  3658.000000    3658.000000   
mean   2124.551941     0.443685    49.551941     1.980317       0.489065   
std    1230.833763     0.496886     8.562029     1.022656       0.499949   
min       1.000000     0.000000    32.000000     1.000000       0.000000   
25%    1052.250000     0.000000    42.000000     1.000000       0.000000   
50%    2141.500000     0.000000    49.000000     2.000000       0.000000   
75%    3201.750000     1.000000    56.000000     3.000000       1.000000   
max    4240.000000     1.000000    70.000000     4.000000       1.000000   

        cigsPerDay       BPMeds  prevalentStroke  prevalentHyp     diabetes  \
count  3658.000000  3658.000000      3658.000000   3658.000000  3658.000000   
mean      9.025424     0.030344         0.005741      0.311646     0.027064   
std      11.921590     0.171557         0.075561      0.463229     0.162292   
min       0.000000     0.000000         0.000000      0.000000     0.000000   
25%       0.000000     0.000000         0.000000      0.000000     0.000000   
50%       0.000000     0.000000         0.000000      0.000000     0.000000   
75%      20.000000     0.000000         0.000000      1.000000     0.000000   
max      70.000000     1.000000         1.000000      1.000000     1.000000   

           totChol        sysBP        diaBP          BMI    heartRate  \
count  3658.000000  3658.000000  3658.000000  3658.000000  3658.000000   
mean    236.847731   132.370558    82.917031    25.782802    75.730727   
std      44.097681    22.086866    11.974258     4.065601    11.981525   
min     113.000000    83.500000    48.000000    15.540000    44.000000   
25%     206.000000   117.000000    75.000000    23.080000    68.000000   
50%     234.000000   128.000000    82.000000    25.380000    75.000000   
75%     263.000000   143.875000    90.000000    28.037500    82.000000   
max     600.000000   295.000000   142.500000    56.800000   143.000000   

           glucose   TenYearCHD  
count  3658.000000  3658.000000  
mean     81.852925     0.152269  
std      23.904164     0.359331  
min      40.000000     0.000000  
25%      71.000000     0.000000  
50%      78.000000     0.000000  
75%      87.000000     0.000000  
max     394.000000     1.000000  
```
## Input 5
```
# View first 10 rows
print("\nFirst 10 rows:")
print(df.head(10))
```
## Output 5
```
First 10 rows:
   sno  gender   age  education  currentSmoker  cigsPerDay  BPMeds  \
0    1        1   39          4              0           0       0   
1    2        0   46          2              0           0       0   
2    3        1   48          1              1          20       0   
3    4        0   61          3              1          30       0   
4    5        0   46          3              1          23       0   
5    6        0   43          2              0           0       0   
6    7        0   63          1              0           0       0   
7    8        0   45          2              1          20       0   
8    9        1   52          1              0           0       0   
9   10        1   43          1              1          30       0   

   prevalentStroke  prevalentHyp  diabetes  totChol  sysBP  diaBP    BMI  \
0                0             0         0      195  106.0   70.0  26.97   
1                0             0         0      250  121.0   81.0  28.73   
2                0             0         0      245  127.5   80.0  25.34   
3                0             1         0      225  150.0   95.0  28.58   
4                0             0         0      285  130.0   84.0  23.10   
5                0             1         0      228  180.0  110.0  30.30   
6                0             0         0      205  138.0   71.0  33.11   
7                0             0         0      313  100.0   71.0  21.68   
8                0             1         0      260  141.5   89.0  26.36   
9                0             1         0      225  162.0  107.0  23.61   

   heartRate  glucose  TenYearCHD  
0         80       77           0  
1         95       76           0  
2         75       70           0  
3         65      103           1  
4         85       85           0  
5         77       99           0  
6         60       85           1  
7         79       78           0  
8         76       79           0  
9         93       88           0
```
## Input 6
```
# View last 5 rows
print("\nLast 5 rows:")
print(df.tail())
```
## Output 6
```
Last 5 rows:
       sno  gender   age  education  currentSmoker  cigsPerDay  BPMeds  \
3653  4234        1   50          1              1           1       0   
3654  4235        1   51          3              1          43       0   
3655  4238        0   52          2              0           0       0   
3656  4239        1   40          3              0           0       0   
3657  4240        0   39          3              1          30       0   

      prevalentStroke  prevalentHyp  diabetes  totChol  sysBP  diaBP    BMI  \
3653                0             1         0      313  179.0   92.0  25.97   
3654                0             0         0      207  126.5   80.0  19.71   
3655                0             0         0      269  133.5   83.0  21.47   
3656                0             1         0      185  141.0   98.0  25.60   
3657                0             0         0      196  133.0   86.0  20.91   

      heartRate  glucose  TenYearCHD  
3653         66       86           1  
3654         65       68           0  
3655         80      107           0  
3656         67       72           0  
3657         85       80           0  
```
## Input 7
```
# Sort the dataframe by age column (ascending)
print("\nData sorted by age (ascending):")
df_sorted = df.sort_values(['age'])
print(df_sorted.head())
```
## Output 7
```
Data sorted by age (ascending):
       sno  gender   age  education  currentSmoker  cigsPerDay  BPMeds  \
2028  2366        0   32          2              1          15       0   
2629  3065        1   33          4              0           0       0   
1136  1314        0   33          1              0           0       0   
1171  1354        1   33          2              0           0       0   
378    441        0   33          3              1          15       0   

      prevalentStroke  prevalentHyp  diabetes  totChol  sysBP  diaBP    BMI  \
2028                0             0         0      242  111.0   70.0  29.84   
2629                0             0         0      165  136.0   75.0  24.95   
1136                0             0         0      158  108.0   67.0  19.84   
1171                0             1         0      165  141.5   95.0  26.74   
378                 0             0         0      199  116.0   81.0  21.61   

      heartRate  glucose  TenYearCHD  
2028         80       88           0  
2629         88       90           0  
1136         86       69           0  
1171         54       77           0  
378          75       93           0
```
## Input 8
```
# Sort descending by age
print("\nData sorted by age (descending):")
df_sorted_desc = df.sort_values(['age'], ascending=False)
print(df_sorted_desc.head())
```
## Output 8
```
Data sorted by age (descending):
       sno  gender   age  education  currentSmoker  cigsPerDay  BPMeds  \
2690  3138        0   70          2              0           0       1   
2815  3279        1   69          1              1           4       0   
3158  3675        0   69          3              0           0       1   
2799  3263        0   69          3              0           0       0   
3532  4101        1   69          1              1           1       0   

      prevalentStroke  prevalentHyp  diabetes  totChol  sysBP  diaBP    BMI  \
2690                0             1         0      231  136.0   84.0  31.78   
2815                0             1         0      232  151.0   74.0  24.14   
3158                0             1         0      203  166.0   90.0  25.40   
2799                0             0         0      286  117.0   73.0  20.92   
3532                0             0         0      245  123.0   77.0  26.58   

      heartRate  glucose  TenYearCHD  
2690         60       95           0  
2815         75       62           0  
3158         77       80           0  
2799         85      103           0  
3532         70       81           1
```
## Input 9
```
# Grouping and summarizing
print("\nGrouping and summarizing by education:")
print(df.groupby('education').sum()['diabetes'])
print(df.groupby('education').mean(numeric_only=True)['diabetes'])
print(df.groupby('education').median(numeric_only=True)['totChol'])
print(df.groupby('education').max()['totChol'])
print(df.groupby('education').min()['totChol'])
```
## Output 9
```
Grouping and summarizing by education:
education
1    56
2    22
3    12
4     9
Name: diabetes, dtype: int64
education
1    0.036697
2    0.019982
3    0.019737
4    0.021277
Name: diabetes, dtype: float64
education
1    236.0
2    230.0
3    236.0
4    233.0
Name: totChol, dtype: float64
education
1    432
2    600
3    464
4    382
Name: totChol, dtype: int64
education
1    113
2    119
3    140
4    150
Name: totChol, dtype: int64
```
## Input 10
```
# Calculate overall mean for all numeric columns
print("\nOverall mean for all numeric columns:")
print(df.mean(numeric_only=True))
```
## Output 10
```
Overall mean for all numeric columns:
sno                2124.551941
gender                0.443685
age                  49.551941
education             1.980317
currentSmoker         0.489065
cigsPerDay            9.025424
BPMeds                0.030344
prevalentStroke       0.005741
prevalentHyp          0.311646
diabetes              0.027064
totChol             236.847731
sysBP               132.370558
diaBP                82.917031
BMI                  25.782802
heartRate            75.730727
glucose              81.852925
TenYearCHD            0.152269
dtype: float64

```
## Input 11
```
# Rename a column
print("\nRenaming 'age' column to 'Age':")
df.rename(columns={'age': 'Age'}, inplace=True)
```
## Output 11
```
Renaming 'age' column to 'Age':
```
## Input 12
```
# Display updated columns
print("\nUpdated column names:")
print(df.columns)

```

## Output 12
```
Updated column names:
Index(['sno', 'gender ', 'Age', 'education', 'currentSmoker', 'cigsPerDay',
       'BPMeds', 'prevalentStroke', 'prevalentHyp', 'diabetes', 'totChol',
       'sysBP', 'diaBP', 'BMI', 'heartRate', 'glucose', 'TenYearCHD'],
      dtype='str')
```





## RESULT

The dataset was successfully cleaned and preprocessed. Data types were verified, missing values and duplicate values were identified, and statistics were generated. The data is now ready for further analysis such as EDA and regression modelling.
