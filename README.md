# Ex:03 Univariate Analysis

# AIM
To read the given data and perform the univariate analysis with different types of plots.

# EXPLANATION
Univariate analysis is basically the simplest form to analyze data. Uni means one and this means that the data has only one kind of variable. The major reason for univariate analysis is to use the data to describe. The analysis will take data, summarise it, and then find some pattern in the data.

# ALGORITHM
Step1
Read the given data.

Step2
Get the information about the data.

Step3
Remove the null values from the data.

Step4
Mention the datatypes from the data.

Step5
Count the values from the data.

Step6
Do plots like boxplots,countplot,distribution plot,histogram plot.

# Program
```
import pandas as pd
from scipy import stats
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```
```
from google.colab import files
uploaded = files.upload()
```
```
df = pd.read_csv('diabetes.csv')
df
```
![image](https://github.com/Poojariyaa/Ex-3/assets/127511817/a6ea260d-3b5a-439b-beb2-9e3d5dacc035)

```
df.isnull().sum()
```
![image](https://github.com/Poojariyaa/Ex-3/assets/127511817/e3d55637-10a7-43ad-9e58-0925f0e92a67)


```
q1 = df.quantile(0.25)
q3 = df.quantile(0.75)
iqr = q3 - q1
iqr
```
![image](https://github.com/Poojariyaa/Ex-3/assets/127511817/581d674e-fae1-43d4-ada6-2a188347289c)

```
low = q1 - 1.5*iqr
high = q1 + 1.5*iqr
df = df[(df >= low) & (df <= high)]
df
```
![image](https://github.com/Poojariyaa/Ex-3/assets/127511817/f35b0281-ba8c-44d0-9088-e11373999036)

```
sns.boxplot(df)
```
![image](https://github.com/Poojariyaa/Ex-3/assets/127511817/bf55926d-5ffb-4b51-93c6-519b872669c2)

```
sns.displot(x ="Glucose", data = df)
```
![image](https://github.com/Poojariyaa/Ex-3/assets/127511817/18cbea11-21f7-4c6c-9193-5d23ef4c6de4)

```
sns.displot(x ="BloodPressure", data = df)
```
![image](https://github.com/Poojariyaa/Ex-3/assets/127511817/0b1cf8e5-4486-426a-bcfb-9be46c90487b)

```
sns.displot(x ="BMI", data = df)
```
![image](https://github.com/Poojariyaa/Ex-3/assets/127511817/741ca1a7-fa6e-4c3a-9339-df26c839f440)


```
sns.displot(x ="DiabetesPedigreeFunction", data = df)
```
![image](https://github.com/Poojariyaa/Ex-3/assets/127511817/82745abc-2a74-442a-a8b2-32e9b1ca1350)

```
sns.displot(x ="Age", data = df)
```
![image](https://github.com/Poojariyaa/Ex-3/assets/127511817/2318f36d-e47a-4672-bd6e-5456d98d990b)

```
from google.colab import files
uploaded = files.upload()
```
![image](https://github.com/Poojariyaa/Ex-3/assets/127511817/d550eb46-5a04-4b08-8243-9f12f2eb30ce)

```
df = pd.read_csv('employeesal.csv')
df
```
![image](https://github.com/Poojariyaa/Ex-3/assets/127511817/51054db4-a545-413f-a210-ff102ed00236)

```
df.isnull().sum()
```
![image](https://github.com/Poojariyaa/Ex-3/assets/127511817/8348115e-443a-4b3c-b3c3-1d5e48a2bfdb)

```
numeric_cols = df.select_dtypes(include=[int, float])
q1 = numeric_cols.quantile(0.25);
q3 = numeric_cols.quantile(0.75);
iqr = q3 - q1
iqr
```
![image](https://github.com/Poojariyaa/Ex-3/assets/127511817/2e033507-b1b5-43de-85a2-7abd5fbd5799)

```
low = q1 - 1.5*iqr
high = q1 + 1.5*iqr
numeric_cols = numeric_cols[(numeric_cols >= low) & (numeric_cols <= high)]
numeric_cols.dropna()
```
![image](https://github.com/Poojariyaa/Ex-3/assets/127511817/a45ab7fa-606e-4e0d-8907-08d8e4c62836)

```
sns.boxplot(numeric_cols)
```
![image](https://github.com/Poojariyaa/Ex-3/assets/127511817/4d524d86-3c79-437c-8261-b65b7c00e2bc)

```
sns.histplot(x = 'Experience_Years',data = numeric_cols)
```
![image](https://github.com/Poojariyaa/Ex-3/assets/127511817/62e54e82-b483-4d3a-8c72-968fe275da82)

```
sns.histplot(x = 'Age',data = numeric_cols)
```
![image](https://github.com/Poojariyaa/Ex-3/assets/127511817/848c29f9-6709-4ef9-a2ea-fe6834ae284c)

```
sns.histplot(x = 'Salary',data = numeric_cols)
```
![image](https://github.com/Poojariyaa/Ex-3/assets/127511817/94ba43c7-b559-4429-8ce8-64bd5ef629f8)

```
from google.colab import files
uploaded = files.upload()
```
![image](https://github.com/Poojariyaa/Ex-3/assets/127511817/7398f533-74d8-4b2e-a476-46a77430fd71)

```
df = pd.read_csv('SuperStore.csv')
df
```
![image](https://github.com/Poojariyaa/Ex-3/assets/127511817/ec8c3286-4921-4953-baae-82fa7ac592e4)

```
df.isnull().sum()
```
![image](https://github.com/Poojariyaa/Ex-3/assets/127511817/814e6dc3-f30f-411a-9c4c-c7f1ea764ca0)

```
df.dropna()
```
![image](https://github.com/Poojariyaa/Ex-3/assets/127511817/fdfe2e7b-a35f-4056-ae1e-dd77813d795e)

```
df.dtypes
```
![image](https://github.com/Poojariyaa/Ex-3/assets/127511817/ef588fdb-621b-4563-a6d3-cac3570b1485)

```
numeric_cols = df.select_dtypes(include=[float])
q1 = numeric_cols.quantile(0.25);
q3 = numeric_cols.quantile(0.75);
iqr = q3 - q1
iqr
```
![image](https://github.com/Poojariyaa/Ex-3/assets/127511817/45f95291-9b5f-416b-bb86-61f4c071a345)

```
low = q1 - 1.5*iqr
high = q1 + 1.5*iqr
numeric_cols = numeric_cols[(numeric_cols >= low) & (numeric_cols <= high)]low = q1 - 1.5*iqr
```
```
sns.boxplot(numeric_cols)
```
![image](https://github.com/Poojariyaa/Ex-3/assets/127511817/a9038bd1-cefa-4e4a-97ba-e0fa2c557ae5)

```
sns.histplot(x = 'Sales',data = numeric_cols)
```
![image](https://github.com/Poojariyaa/Ex-3/assets/127511817/8ee72968-3466-47a9-9d32-113d3e4c0a88)

```
sns.countplot(x="Postal Code", data=numeric_cols)
```
![image](https://github.com/Poojariyaa/Ex-3/assets/127511817/a588d377-0cd3-4b74-a676-e85e3bf9dc16)

# Result
Thus we have read the given data and performed the univariate analysis with different types of plots.
