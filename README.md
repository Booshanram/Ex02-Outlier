 AIM: To determine the outlier detection and removal using IQR with given csv files.
 
 ALGORITHM:
 1)Start the program 
 2) Remove outliers using IQR 
 (3) After removing outliers in step 1, you get a new dataframe. 
 (4) use zscore of 3 to remove outliers. This is quite similar to IQR and you will get exact same result 
 (5) for the data set height_weight.csv find the following 6)stop the program
 
 PROGRAM: 
 import pandas as ps 
 import numpy as np 
 import seaborn as sns 
 df=ps.read_csv("bhp.csv") df
\ df.head() df.describe() 
df.info() df.isnull().sum() 
df.shape sns.boxplot(x="price_per_sqft",data=df) q1=df['price_per_sqft'].quantile(0.35) q3=df['price_per_sqft'].quantile(0.65)
print("First Quantile =",q1,"Second quantile =",q3)
IQR=q3-q1 #INTERQUARTILE RANGE 
ul =q3+0.5*IQR ll =q1-1.5*IQR 
df1=df[((df['price_per_sqft']<=l1)&(df['price_per_sqft']>u1))] 
df1 df1.shape sns.boxplot(x='price_per_sqft',data=df1) from scipy 
import stats z=np.abs(stats.zscore(df['price_per_sqft'])) 
df2=df[(z<3)] df2 print(df2.shape) 
sns.boxplot(x='price_per_sqft',data=df2)
df3=ps.read_csv('height_weight.csv') df3 
df3.head() df3.info() df3.describe() 
df3.isnull().sum() df3.shap
