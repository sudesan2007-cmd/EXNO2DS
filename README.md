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

## CODING AND OUTPUT
  ```
import pandas as pd
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![Screenshot 2024-09-19 082445](https://github.com/user-attachments/assets/8861e70c-b854-4f78-b924-24078d6563a0)
```
df.isna().sum()
```
![Screenshot 2024-09-19 082541](https://github.com/user-attachments/assets/5e6db278-0e1f-4381-ae76-33c62d1a6f0e)
```
df.dropna(inplace=True)
df
```
![Screenshot 2024-09-19 082633](https://github.com/user-attachments/assets/9626f521-7ed3-4277-83a1-b01af60c9f4c)
```
df.info()
```
![Screenshot 2024-09-19 082715](https://github.com/user-attachments/assets/05099858-725f-456e-9fa7-63eacb5eb9de)
```
df.shape
```
![Screenshot 2024-09-19 082814](https://github.com/user-attachments/assets/d4a48c57-638e-416e-9084-b1d7e5509b2b)
```
df.set_index("PassengerId",inplace=True)
```
```
df.describe()
```
![Screenshot 2024-09-19 082911](https://github.com/user-attachments/assets/43618fdc-6a8a-403d-828a-7543199e08e4)
```
df.nunique()
```
![Screenshot 2024-09-19 083311](https://github.com/user-attachments/assets/b0a60d17-bae8-45e9-8905-9193de5909e4)
```
df["Survived"].value_counts()
```
![Screenshot 2024-09-19 083409](https://github.com/user-attachments/assets/cf42da36-40de-47e6-8475-c98d992413d5)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![Screenshot 2024-09-19 083529](https://github.com/user-attachments/assets/ea3c3f28-7c76-4839-b16d-97d992bfe28a)
```
import matplotlib.pyplot as plt
import seaborn as sns
```
```
sns.countplot(data=df,x="Survived")
```
![Screenshot 2024-09-19 083629](https://github.com/user-attachments/assets/1c6c2b58-427a-48ff-9099-0d7126f1fe13)
```
df
```
![Screenshot 2024-09-19 083707](https://github.com/user-attachments/assets/d68ef8cf-bcd4-4c16-a2a1-f503ffc1f882)
```
df.Pclass.unique()
```
![Screenshot 2024-09-19 083809](https://github.com/user-attachments/assets/7a4f0f1d-9a9f-45de-9b3e-e59f13fbc2f9)
```

df.rename(columns= {'Sex': 'Gender'},inplace=True)
sns.catplot(x="Gender",col="Survived",kind= "count",data=df,height=5,aspect=.7)
```
![Screenshot 2024-09-19 083950](https://github.com/user-attachments/assets/82a4a5be-76df-40e0-88a2-a3ebb28219a8)
```
sns.catplot(x='Survived',hue="Gender",data=df,kind = "count")
```
![Screenshot 2024-09-19 084046](https://github.com/user-attachments/assets/d0aa6ad8-1317-4c41-93bd-1a1a6e29d55a)
```
sns.catplot(data=df,col = "Survived",x="Gender",hue="Pclass",kind = "count")
```
![Screenshot 2024-09-19 084138](https://github.com/user-attachments/assets/194049cb-b5ea-40fc-855e-129adc0ebf5c)
```
numeric_df = df.select_dtypes(include=[np.number])
corr = numeric_df.corr()
sns.heatmap(corr, annot=True)
```
![Screenshot 2024-09-19 084241](https://github.com/user-attachments/assets/8a2bb086-862e-4f14-b51a-a609e4f2bd08)
```
sns.pairplot(df)
```
![Screenshot 2024-09-19 084343](https://github.com/user-attachments/assets/645629ad-2dd0-486a-ad29-fcb76b9000de)     

# RESULT
       
We have performed Exploratory Data Analysis on the given data set successfully.
