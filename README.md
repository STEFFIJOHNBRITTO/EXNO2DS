# EXNO2DS
## Name : STEFFI J
## Register no : 212224220107
## Date : 16-09-2025

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

# CODING AND OUTPUT
# Program
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df = pd.read_csv('titanic_dataset.csv')
df
```
# Output

<img width="1513" height="682" alt="image" src="https://github.com/user-attachments/assets/2b42d64f-30b5-4f66-85c0-1a69c1a04c3b" />

# Program
```
df.info()
```
# Output

<img width="551" height="478" alt="image" src="https://github.com/user-attachments/assets/7a121fd6-84d4-4107-a91c-a69fee280328" />

# Program
```
df.describe()
```
# Output

<img width="962" height="433" alt="image" src="https://github.com/user-attachments/assets/13dc8d7e-cb34-42e7-8e9d-89eb069821c4" />

# Program
```
df.dtypes
```

# Output

<img width="400" height="626" alt="image" src="https://github.com/user-attachments/assets/b118d554-504d-48e1-8abb-55fe8e96fe14" />

# Program
```
df.value_counts()
```
# Output

<img width="1566" height="655" alt="image" src="https://github.com/user-attachments/assets/25b2f13f-0274-405a-a85c-ec5c74d38bec" />

# Program
```
df["Survived"].value_counts()
```
# Output

<img width="460" height="270" alt="image" src="https://github.com/user-attachments/assets/66ed8fe9-6b62-43da-b68d-d8eb056ca15f" />

# Program
```
df["Age"].value_counts()
```
# Output

<img width="402" height="656" alt="image" src="https://github.com/user-attachments/assets/b8e8524b-86a5-417f-b2ce-81be215646fe" />

# Program
```
df.shape
```
# Output

<img width="262" height="105" alt="image" src="https://github.com/user-attachments/assets/1e6aee9d-88a5-44c9-97d5-3b9189508e0c" />

# Program
```
df.set_index("Survived",inplace=True)
df.describe()
```
# Output

<img width="977" height="462" alt="image" src="https://github.com/user-attachments/assets/8808b0fa-22a0-4a1e-98da-97c4c78b736c" />

# Program
```
df.nunique()
```
# Output

<img width="352" height="578" alt="image" src="https://github.com/user-attachments/assets/63e28b89-f991-4d07-bd5f-8de3b52ef5e5" />

# Program
```
df.set_index("Name",inplace=True)
df.describe()
```
# Output

<img width="866" height="452" alt="image" src="https://github.com/user-attachments/assets/8b39072a-7a0c-4ea4-b352-763cc0544049" />

# Program
```
sns.countplot(data=df,x="Survived")
```
# Output

<img width="891" height="635" alt="image" src="https://github.com/user-attachments/assets/e50a991a-43be-49e7-80af-46c77e94f156" />

# Program
```
df.Pclass.unique()
```
# Output

<img width="308" height="102" alt="image" src="https://github.com/user-attachments/assets/ad8f9990-8aed-4543-a9ad-3aee66d281a4" />

# Program
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```

# Output

<img width="1485" height="637" alt="image" src="https://github.com/user-attachments/assets/1acebbb3-cdf7-4a62-8b7f-2429d42a220f" />

# Program
```
sns.catplot(x="Sex",hue="Survived",kind="count",data=df,height=5,aspect=.7)
```

# Output

<img width="1068" height="697" alt="image" src="https://github.com/user-attachments/assets/ed1cdc3a-8b57-4c61-beef-f26eddf2f6ba" />

# Program
```
sns.catplot(x="Sex",col="Survived",kind="count",data=df,height=5,aspect=.7)
```

# Output

<img width="1212" height="692" alt="image" src="https://github.com/user-attachments/assets/0507503d-0bc3-433b-a819-7caec06810e5" />

# Program
```
sns.catplot(x="Sex",col="Survived",kind="bar",data=df,height=5,aspect=.7)
```

# Output

<img width="1256" height="707" alt="image" src="https://github.com/user-attachments/assets/06370b58-9ccb-46f8-bcb3-2866e4126121" />

# Program
```
sns.catplot(x="Sex",hue="Survived",kind="bar",data=df,height=5,aspect=.7)
```
# Output

<img width="1035" height="691" alt="image" src="https://github.com/user-attachments/assets/69624922-750f-4479-a2e4-5f6b4295742d" />

# Program
```
df.boxplot(column="Age",by="Survived")
```
# Output

<img width="918" height="658" alt="image" src="https://github.com/user-attachments/assets/9ec27e71-55e4-42ba-a29f-542ae174f03e" />

# Program
```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
# Output

<img width="957" height="627" alt="image" src="https://github.com/user-attachments/assets/56f6add5-1dd4-482b-8829-25ce7e120fe3" />

# Program
```
fig,ax1=plt.subplots(figsize=(8,5))
plt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Survived',data=df)
```
# Output

<img width="1147" height="657" alt="image" src="https://github.com/user-attachments/assets/37ffd0af-d810-4f7d-8187-c5c6b811c5d6" />

# Program
```
plt=sns.boxplot(x='Pclass',y='Age',hue='Survived',data=df)
```
# Output

<img width="945" height="602" alt="image" src="https://github.com/user-attachments/assets/a79d289d-87c5-449b-8226-dba194183ab0" />

# Program
```
sns.catplot(data=df,col="Survived",x="Sex",hue="Pclass",kind="count")
```
# Output

<img width="1543" height="705" alt="image" src="https://github.com/user-attachments/assets/f6459c73-b70d-45f9-9271-8fd52ae8d8b2" />

# Program
```
corr=df.select_dtypes(include=np.number).corr()
sns.heatmap(corr,annot=True)
```
# Output

<img width="948" height="710" alt="image" src="https://github.com/user-attachments/assets/dd789e7f-c721-4ae6-ae2c-0a679f7cfb16" />

# Program
```
corr=df.select_dtypes(include=np.number).corr()
sns.heatmap(corr)
```
# Output

<img width="917" height="717" alt="image" src="https://github.com/user-attachments/assets/1f96b43d-7570-4860-91aa-2617fccd20c5" />

# RESULT
```
 Code are sucessfully executed.
```
