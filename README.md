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
import seaborn as sns
df = pd.read_csv('C:/Users/admin/Downloads/titanic_dataset.csv')
df
``` 
<img width="1402" height="500" alt="image" src="https://github.com/user-attachments/assets/768fac28-5c04-4427-95bc-72e8f8d04be8" />


```
df.shape
```
<img width="197" height="57" alt="image" src="https://github.com/user-attachments/assets/7d7ffab9-6431-4779-b0dc-38526ceecb57" />

```
df.set_index("PassengerId",inplace=True)
df
```

<img width="1367" height="537" alt="image" src="https://github.com/user-attachments/assets/10086c01-3363-40b2-b169-dcc3146ad3b7" />

```
df.nunique()
```

<img width="283" height="273" alt="image" src="https://github.com/user-attachments/assets/a5b5ad06-4073-4e21-a6a7-a4fd62a5239d" />

```
df['Survived'].value_counts()
```

<img width="467" height="78" alt="image" src="https://github.com/user-attachments/assets/7fd05a13-eb9c-4224-a8bf-aa238dc5b70e" />

```
df['Sex'].value_counts()
```

<img width="632" height="146" alt="image" src="https://github.com/user-attachments/assets/3b9295b4-a83c-42e9-be8c-d1380a87407e" />

```
df.Survived.unique()
```

<img width="493" height="90" alt="image" src="https://github.com/user-attachments/assets/f0fcd548-46b7-42a9-af3f-c60be72f3807" />

```
df.rename(columns={"Sex":"Gender"},inplace=True)
df
```

<img width="1367" height="553" alt="image" src="https://github.com/user-attachments/assets/975e04f8-784d-4db2-940e-9d7a0c10b4b9" />

```
sns.countplot(data=df)
```

<img width="571" height="413" alt="image" src="https://github.com/user-attachments/assets/9ba0029f-1d43-45b3-9afa-202cf9fec3f5" />

```
sns.countplot(x="Survived",hue="Gender",data=df)
```

<img width="571" height="432" alt="download" src="https://github.com/user-attachments/assets/2b47f9f5-5405-4b62-9016-fe7ca7542a91" />

```
sns.catplot(x="Survived", hue="Gender", y="Fare", data=df, kind="box")
```

<img width="582" height="490" alt="download" src="https://github.com/user-attachments/assets/a2df238d-fb95-4054-ba74-bdcc6f3259e5" />

```
sns.catplot(x="Survived", hue="Gender", data=df, kind="count")
```

<img width="582" height="489" alt="download" src="https://github.com/user-attachments/assets/84e3194e-edfc-4974-b124-8b7d915015ee" />

```
sns.catplot(x="Survived", hue="Gender", y="Fare", data=df, kind="violin")
```

<img width="582" height="490" alt="download" src="https://github.com/user-attachments/assets/463c78a6-faf8-4353-a8a7-6917c477baaa" />

```
sns.boxplot(data=df)
```

<img width="552" height="413" alt="download" src="https://github.com/user-attachments/assets/2f237734-ed5c-46b7-ab31-59e058d31026" />

```
df.boxplot(column="Survived",by="Gender")
```

<img width="563" height="461" alt="download" src="https://github.com/user-attachments/assets/f941978a-06d6-4ff5-afec-b8e7cfbc691c" />

```
sns.scatterplot(data=df)
```

<img width="552" height="432" alt="download" src="https://github.com/user-attachments/assets/05016d0d-d853-45ee-8958-26c4537cc8a2" />

```
sns.scatterplot(x='Age',y='Fare',data=df)
```

<img width="571" height="432" alt="download" src="https://github.com/user-attachments/assets/be3b6d56-9bc5-48d3-8933-19a0ac5d9697" />

```
sns.jointplot(x='Age',y='Fare',data=df,kind='hist')
```

<img width="594" height="590" alt="download" src="https://github.com/user-attachments/assets/aba4b12b-5a8a-45cc-a731-2aaf3f5289a0" />

```
sns.jointplot(x='Age',y='Fare',data=df,kind='kde')
```

<img width="594" height="590" alt="download" src="https://github.com/user-attachments/assets/6e138839-4822-43e9-a434-fb79795272a5" />

```
sns.pairplot(data=df)
```

<img width="1476" height="1476" alt="download" src="https://github.com/user-attachments/assets/21b33333-67a8-4173-9d28-28ea6bfdcca1" />

```
corr1=df.select_dtypes(include=['number']).corr()
sns.heatmap(corr1,annot=True)
```

<img width="527" height="418" alt="download" src="https://github.com/user-attachments/assets/0bf45549-1546-430c-89a7-c9074a800579" />

```
group=df.groupby(['Pclass','Survived'])
pclass_survived=group.size().unstack()
sns.heatmap(pclass_survived,annot=True,fmt='d')
```

<img width="539" height="432" alt="download" src="https://github.com/user-attachments/assets/ee75d51f-e342-4552-8a36-6d68ac36740a" />

# RESULT
Thus exploratory data analysis on the given data set has been executed successfully.
