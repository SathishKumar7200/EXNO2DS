# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
      The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: 
      Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2:
      Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: 
      Use boxplot method to analyze the outliers of the given dataset.

STEP 4: 
      Remove the outliers using Inter Quantile Range method.

STEP 5: 
      Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: 
      Use displot method to represent the univariate distribution of data.

STEP 7:
      Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8:
      Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
from google.colab import drive
drive.mount('/content/drive')
![Screenshot 2024-12-14 203758](https://github.com/user-attachments/assets/d430ab4b-666f-472e-99b7-0a2f842d883f)

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

ls drive/MyDrive/titanic_dataset.csv
![Screenshot 2024-12-14 203822](https://github.com/user-attachments/assets/0f653018-d87a-47ea-a638-ff32cb2cf75b)

df=pd.read_csv('drive/MyDrive/titanic_dataset.csv')
df
![Screenshot 2024-12-14 203839](https://github.com/user-attachments/assets/bba2f4cc-66ad-4d5a-8a80-1afe11ded97e)

df.info()
![Screenshot 2024-12-14 203856](https://github.com/user-attachments/assets/b6c07a64-3e8b-4478-9abb-376dfbd56ba5)

df.set_index('PassengerId',inplace=True)
df.describe()
![Screenshot 2024-12-14 203910](https://github.com/user-attachments/assets/abcf1f54-c9ae-470e-ab9c-f2ba29e1ddb6)

df.shape
![Screenshot 2024-12-14 203932](https://github.com/user-attachments/assets/0fc385c3-b97d-41d8-81b6-c64f3ba01dfd)

df.nunique()
![Screenshot 2024-12-14 204002](https://github.com/user-attachments/assets/6d9e8ba1-6d12-4993-9d08-6047b52fc2a5)

df['Survived'].value_counts()
![Screenshot 2024-12-14 204017](https://github.com/user-attachments/assets/b3568c02-9317-439c-8a62-00c8e7b333ac)

per=(df['Survived'].value_counts()/df.shape[0]*100).round(2)
per
![Screenshot 2024-12-14 204029](https://github.com/user-attachments/assets/6876cbd9-0fda-413e-978b-0f38b2ed9b43)

sns.countplot(data=df,x='Survived')
![Screenshot 2024-12-14 204041](https://github.com/user-attachments/assets/e3a02dbc-1940-4991-86d7-30eb619f82fe)

df
![Screenshot 2024-12-14 204057](https://github.com/user-attachments/assets/af08b48e-93fd-4d34-858e-d318567c0d45)

df.Pclass.unique()
![Screenshot 2024-12-14 204110](https://github.com/user-attachments/assets/40962967-ab58-471f-a28f-68cb82e3c4b6)

df.rename(columns={'Sex':'Gender'},inplace=True)

sns.catplot(x='Gender',col='Survived',kind='count',data=df,height=5,aspect=.7)
![Screenshot 2024-12-14 204217](https://github.com/user-attachments/assets/1a597ec7-1a01-457b-8c21-6a6ee95bbca6)

sns.catplot(x='Survived',hue='Gender',data=df,kind='count')
![Screenshot 2024-12-14 204231](https://github.com/user-attachments/assets/9d7809f0-a6ae-4a24-b763-6287839a18cf)

df.boxplot(column='Age',by='Survived')
![Screenshot 2024-12-14 204246](https://github.com/user-attachments/assets/4bdf289c-9b24-404e-a737-cb07b1e57fbe)

sns.scatterplot(x=df['Age'],y=df['Fare'])
![Screenshot 2024-12-14 204303](https://github.com/user-attachments/assets/a8153217-be70-4784-955b-cb49b42eb457)

fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
![Screenshot 2024-12-14 204318](https://github.com/user-attachments/assets/20ac6283-06c2-42d0-a904-d1cab3ac3121)

sns.catplot(data=df,col='Survived',x='Gender',hue='Pclass',kind='count')
![Screenshot 2024-12-14 204335](https://github.com/user-attachments/assets/64c0b6ed-4eda-4b19-b7d1-5fe492fdd1df)

numeric_df=df.select_dtypes(include=np.number)
corr=numeric_df.corr()
sns.heatmap(corr,annot=True)
![Screenshot 2024-12-14 204348](https://github.com/user-attachments/assets/39a7eea8-680b-4fcc-a724-9c3b2f182501)

sns.pairplot(df)
![Screenshot 2024-12-14 204411](https://github.com/user-attachments/assets/7da324a2-fbeb-4852-b742-0762bc56b0f3)
   
ND OUTPUT SCREENSHOTS>>

# RESULT
      The above code is executed successfully.
