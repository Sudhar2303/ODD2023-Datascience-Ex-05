# Ex:05 Feature Generation
# AIM
To read the given data and perform Feature Generation process and save the data to a file.

# Explanation
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.

# ALGORITHM
## STEP 1
Read the given Data

## STEP 2
Clean the Data Set using Data Cleaning Process

## STEP 3
Apply Feature Generation techniques to all the feature of the data set

## STEP 4
Save the data to the file

# CODE AND OUTPUT FOR FEATURE ENCODING AND FEATURE SCALING:
```
import pandas as pd
import numpy as np
```
```
from google.colab import files
upload = files.upload()
```
![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex-05/assets/133684710/889ff369-96f5-4507-918e-0bd77005deac)
```
df = pd.read_csv("bmi.csv")
df
```
![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex-05/assets/133684710/4551f158-81de-451f-ace4-f2979f5fa663)
```
from category_encoders import BinaryEncoder
e1 = BinaryEncoder()
bn = e1.fit_transform(df['Gender'])
df = pd.concat([df,bn],axis = 1)
df
```
![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex-05/assets/133684710/da2dcf79-9e97-4566-bdd9-474b17a55347)
```
from sklearn.preprocessing import RobustScaler
rs = RobustScaler()
df[['Height','Weight']] = rs.fit_transform(df[['Height','Weight']])
df
```
![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex-05/assets/133684710/23b8ec28-d7a3-4879-946e-0eef6e4e0f5f)
```
from google.colab import files
upload = files.upload()
```
![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex-05/assets/133684710/0f588600-b735-44f1-b7ec-70a291c4f678)
```
df = pd.read_csv("data1.csv")
df
```
![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex-05/assets/133684710/3554b5b8-403c-4f99-9a88-3eb0d0506cf9)
```
from sklearn.preprocessing import OrdinalEncoder,LabelEncoder,OneHotEncoder
data = ['Very Hot','Hot','Warm','Cold']
e1 = OrdinalEncoder(categories = [data])
df['Ord_1'] = e1.fit_transform(df[['Ord_1']])
df
```
![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex-05/assets/133684710/28801bad-25d0-45d5-ac6c-e44b17480885)
```
data1 = ['High School','Diploma','Bachelors','Masters','PhD']
e1 = LabelEncoder()
df['Ord_2'] = e1.fit_transform(df['Ord_2'])
df
```
![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex-05/assets/133684710/8a0d9f2f-ccaf-473c-83a6-9126289d838d)
```
e2 = OneHotEncoder(sparse = False)
enc = pd.DataFrame(e2.fit_transform(df[['City']]))
df = pd.get_dummies(df,columns = ['City'])
df
```
![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex-05/assets/133684710/09ec489c-3b16-4aec-9946-b5f4e4927c48)
```
pip install --upgrade category_encoders
from category_encoders import BinaryEncoder
e3 = BinaryEncoder()
bn = e3.fit_transform(df[['bin_1','bin_2']])
df = pd.concat([df,bn],axis = 1)
df
```
![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex-05/assets/133684710/b45ed778-a52c-4ade-81ea-a9f513847ff9)
```
from sklearn.preprocessing import MinMaxScaler
mm = MinMaxScaler()
df[['Ord_1','Ord_2']] = mm.fit_transform(df[['Ord_1','Ord_2']])
df
```
![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex-05/assets/133684710/1579d587-a6b9-45c1-bccc-906e53b24a4d)
```
from google.colab import files
upload = files.upload()
```
![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex-05/assets/133684710/e88f3a82-4c26-4ada-aaf5-41abd94aa33a)
```
df = pd.read_csv("Encoding Data.csv")
df
```
![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex-05/assets/133684710/6ffc8a78-1efa-4db6-a87c-31e1a23edd8a)

```
from sklearn.preprocessing import LabelEncoder,OneHotEncoder
data1 = ['Hot','Warm','Cold']
e1 = LabelEncoder()
df['ord_2'] = e1.fit_transform(df['ord_2'])
df
```
![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex-05/assets/133684710/02d3474b-61e8-4497-af5b-7e18b863743c)
```
e2 = OneHotEncoder(sparse = False)
enc = pd.DataFrame(e2.fit_transform(df[['nom_0']]))
df = pd.get_dummies(df,columns = ['nom_0'])
df```
```
![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex-05/assets/133684710/c586a791-8421-46b7-8f35-51451c284e27)

```
from category_encoders import BinaryEncoder
e3 = BinaryEncoder()
bn = e3.fit_transform(df[['bin_1','bin_2']])
df = pd.concat([df,bn],axis = 1)
df
```
![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex-05/assets/133684710/cdc67ca4-6919-4760-a5f2-604f9cf6183e)

```
from sklearn.preprocessing import  StandardScaler
ss = StandardScaler()
df[['ord_2']] = ss.fit_transform(df[['ord_2']])
df
```
![image](https://github.com/Sudhar2303/ODD2023-Datascience-Ex-05/assets/133684710/890f7fe6-45d3-4457-ba92-789ed60afa0a)

# RESULT:
Feature Encoding process and Feature Scaling process is applied to the given data frame sucessfully.
