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
cimport pandas as pd
df=pd.read_csv('titanic_dataset.csv')
df

<img><img width="995" height="356" alt="{C61E20DE-A89F-4828-A5B6-094FF3C9F871}" src="https://github.com/user-attachments/assets/e0ac3291-5b2a-4cb9-a6df-d3bdd4bd493e" />

df.shape

<img><img width="101" height="20" alt="{CA596E9F-DF49-44C8-8AD2-9BD68480E775}" src="https://github.com/user-attachments/assets/9295601a-db05-40b2-950c-8b1946e7421f" />


df.set_index("PassengerId",inplace=True)
df

<img><img width="992" height="377" alt="{E53CA081-2775-4FF6-8B4F-A177B07DDAD7}" src="https://github.com/user-attachments/assets/0090f4f1-ad5d-40c7-920f-7611b97c7d44" />

df.nunique()

<img><img width="173" height="207" alt="{4DCBB3F2-A7EE-4745-9C05-B909B70D8688}" src="https://github.com/user-attachments/assets/4a72c8f4-4158-4c98-b2ce-d341bcaa55c6" />

df['Sex'].value_counts()

<img><img width="210" height="70" alt="{5103926E-B9B1-47B9-B593-5753EFC93BBD}" src="https://github.com/user-attachments/assets/f099bcf2-600f-42c2-8a27-8e637fdc925d" />


df.Survived.unique()


<img><img width="217" height="29" alt="{FCE974FB-428D-4395-B49E-58625554415E}" src="https://github.com/user-attachments/assets/005c62a8-4226-4ed7-91cf-1642b9fbe78e" />


df.rename(columns={"Sex":"Gender"},inplace=True)
df


<img><img width="1006" height="373" alt="{78CA99EF-C04E-488F-90A9-194DA0402223}" src="https://github.com/user-attachments/assets/725c64fa-c17f-4784-8322-71aac0dc9d90" />



import seaborn as sns
sns.countplot(data=df)


<img><img width="595" height="303" alt="{FD50CA0E-431E-477E-8FB8-84C09B9A914A}" src="https://github.com/user-attachments/assets/ad6e224b-deab-4f72-abf4-d65aa43303cc" />

sns.countplot(x="Survived",hue="Gender",data=df)


<img><img width="579" height="401" alt="{0E472425-9A12-4AB6-88B2-2A45F506FC5D}" src="https://github.com/user-attachments/assets/160ca6d0-b08b-4695-9993-1e1fe1d0e459" />


sns.catplot(x="Survived",hue="Gender",data=df,kind="count")


<img><img width="572" height="438" alt="{3D53BF58-5C62-47A8-99A6-947E19BBBB6B}" src="https://github.com/user-attachments/assets/f0354af9-29d5-4b62-bae6-95e9306eaa45" />

sns.catplot(x="Survived",col="Gender",data=df,kind="violin")


<img><img width="975" height="310" alt="{D42C9F3B-0FB2-46C7-B82C-835BC9BDDE71}" src="https://github.com/user-attachments/assets/7e0173c8-0307-498b-a8ad-ab132d4a06c2" />

sns.boxplot(data=df)



<img><img width="561" height="291" alt="{FABAEC61-888F-4E17-A345-7A1FD69879AB}" src="https://github.com/user-attachments/assets/5a05edf9-1889-4257-ad9e-b7f20ce582e2" />

df.boxplot(column="Survived",by="Gender")


<img><img width="580" height="424" alt="{D9ED30E2-72B2-48FB-BB68-ADBCA8365DFF}" src="https://github.com/user-attachments/assets/5c027bcf-7d72-4439-b42e-62374c1b3edc" />


sns.scatterplot(data=df)


<img><img width="614" height="408" alt="{ABA31F30-60DF-49F6-A671-522099E0FAF5}" src="https://github.com/user-attachments/assets/7b26b551-dd50-4d6c-8d1d-28b99aa9f6c2" />

sns.scatterplot(x=df['Age'],y=df['Fare'])



<img><img width="567" height="431" alt="{DC9E96D1-03AF-4F24-B069-47B355404AE0}" src="https://github.com/user-attachments/assets/6cd96bd8-6330-4f1f-a3f8-f182ff698d23" />

sns.jointplot(x='Age',y='Fare',data=df)


<img><img width="595" height="319" alt="{79B82AC9-0D19-4FA6-A5A7-28AF84771997}" src="https://github.com/user-attachments/assets/07ac3f13-8e20-4cb2-933e-ec6fd76aa737" />

sns.jointplot(x='Age',y='Fare',data=df,kind="kde")


<img><img width="668" height="586" alt="{CB6156C2-534B-4694-A8DC-9330B69EA744}" src="https://github.com/user-attachments/assets/7b782a2a-7954-47ef-97fc-8d79ad6aa0c1" />

sns.jointplot(x='Age',y='Fare',data=df,kind="hist") 


<img><img width="576" height="574" alt="{43D5C63D-CB11-4720-9B57-73E9365E0385}" src="https://github.com/user-attachments/assets/8c107e85-1292-474e-932a-4b14f8bacb32" />

sns.pairplot(data=df)


<img><img width="781" height="728" alt="{8415268A-F189-4C32-976B-DCA7E21099F1}" src="https://github.com/user-attachments/assets/f4eed93e-a6a6-483c-aead-e1c48b2d2bf5" />

corr1=df.select_dtypes(include=['number']).corr()
sns.heatmap(corr1,annot=True)


<img><img width="416" height="323" alt="{E99B17B8-24DC-42C4-84FB-CEC4422F3B1E}" src="https://github.com/user-attachments/assets/450a7cc9-a8f8-4cec-b9c9-4eaafbd4f077" />

sns.catplot(x='Gender',col='Survived',data=df,kind='count',color='green')


<img><img width="751" height="386" alt="{DE224E60-9342-4097-9724-9D03C3D48312}" src="https://github.com/user-attachments/assets/e03425f0-8b33-46f8-8a80-c7ce41bc07c9" />

# RESULT
        <<INCLUDE YOUR RESULT HERE>>
