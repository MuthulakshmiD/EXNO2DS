# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT:
Name:Muthulakshmi D
Reg: 212223040122

# Coding:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
# Output:

![image](https://github.com/user-attachments/assets/bb937929-b7a4-4c87-8e80-ce5bc4bafab5)


# Coding:
```
df.info()
```
# Output:

![image](https://github.com/user-attachments/assets/9c239dcb-fc73-494a-8569-1379592b48f5)


# Coding:
```
df.shape
```
# Output:

![image](https://github.com/user-attachments/assets/9422050f-fb50-4b02-a2a5-4c82b469abde)


# Coding:
```
df.set_index("PassengerId",inplace=True)
df.describe()
```
# Output:

![image](https://github.com/user-attachments/assets/a5db78e3-0201-4178-a821-a59959bcfb5c)


# Coding:
```
df.nunique()
```
# Output:

![image](https://github.com/user-attachments/assets/0a639fbd-02f9-43eb-91ed-321946d4c7b0)


# Coding:
```
df["Survived"].value_counts()
```
# Output:

![image](https://github.com/user-attachments/assets/967862c0-eae6-418f-9051-0dd7792d43b3)


# Coding:
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
 # Output:
 
![image](https://github.com/user-attachments/assets/19a617f8-4330-470a-88ff-d37389e9f03a)


# Coding:
```
sns.countplot(data=df,x="Survived")
```
# Output:

![image](https://github.com/user-attachments/assets/f4c34a85-d332-4174-bccf-fe084ca505a1)


# Coding:
```
df
```
# Output:

![image](https://github.com/user-attachments/assets/1d188a80-63fc-4e4c-9c62-96716c013a7f)


# Coding:
```
df.Pclass.unique()
```
# Output:

![image](https://github.com/user-attachments/assets/38e64d30-4caf-426a-b388-91fc1e34c5c9)



# Coding:
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
# Output:

![image](https://github.com/user-attachments/assets/10a982df-3330-4199-a766-cd246ec19d04)


# Coding:
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
# Output:

![image](https://github.com/user-attachments/assets/49dd3805-bb49-40d7-bdc3-39286f1be4d3)


# Coding:
```
sns.catplot(x='Survived',hue="Gender",data=df,kind='count')
```
# Output:

![image](https://github.com/user-attachments/assets/c7a7ce5f-7473-4175-a778-974ff37d6b8e)


# Coding:
```
df.boxplot(column="Age",by="Survived")
```
# Output:

![image](https://github.com/user-attachments/assets/881404f0-b3b6-421c-bce8-d6e7ef744ec5)


# Coding:
```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
# Output:

![image](https://github.com/user-attachments/assets/867d0233-b000-47c9-bb5b-8d8c9a0c623c)


# Coding:
```
sns.jointplot(x="Age",y="Fare",data=df)
```
# Output:

![image](https://github.com/user-attachments/assets/46d1f9a3-607f-4d1a-b462-0eef592018bd)


# Coding:
```
fig,ax1=plt.subplots(figsize=(8,5))
sns.boxplot(ax=ax1,x="Pclass",y="Age",hue="Gender",data=df)
```
# Output:

![image](https://github.com/user-attachments/assets/5ea12586-3889-4c3e-a633-9c7d0f67bb69)


# Coding:
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
# Output:

![image](https://github.com/user-attachments/assets/0836a775-aa60-456d-931f-03759c2f932d)


# Coding:
```
numerical_df = df.select_dtypes(include=['number'])
corr = numerical_df.corr()
sns.heatmap(corr, annot=True)
```
# Output:

![image](https://github.com/user-attachments/assets/ac4d6a04-0b41-409b-8136-1d550dad912b)


# Coding:
```
sns.pairplot(df)
```
# Output:

![image](https://github.com/user-attachments/assets/e28bc198-b795-494d-b406-1dfca8f89472)



# RESULT
        Thus, the Exploratory Data Analysis on the given data set has been performed successfully.
