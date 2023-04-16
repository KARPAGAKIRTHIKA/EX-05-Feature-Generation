# EX-05-Feature-Generation


## AIM
To read the given data and perform Feature Generation process and save the data to a file. 

# Explanation
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.
 

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature Generation techniques to all the feature of the data set
### STEP 4
Save the data to the file


# CODE
# data.csv
``
import pandas as pd  
import seaborn as sbn
df=pd.read_csv("/content/data.csv")
df.info()
df.isnull().sum()from sklearn.preprocessing import LabelEncoder
le = LabelEncoder()
df['Ord_2'] = le.fit_transform(df['Ord_2'])
sbn.set(style ="darkgrid")
sbn.countplot(df['Ord_2'])from sklearn.preprocessing import OneHotEncoder
enc = OneHotEncoder()
enc = enc.fit_transform(df[['City']]).toarray()
encoded_colm = pd.DataFrame(enc)
df = pd.concat([df, encoded_colm], axis=1)
df = df.drop(['City'], axis=1)
df.head(10)
df = pd.get_dummies(df, prefix=['Ord_2'], columns=['Ord_2'])
df.head(10)
df = pd.get_dummies(df, prefix=['Ord_1'], columns=['Ord_1'])
df.head(10)
``

## encoding.csv
``
import pandas as pd
import seaborn as sbn
data=pd.read_csv("/content/Encoding Data.csv")
data.info()
data.isnull().sum()
from sklearn.preprocessing import LabelEncoder
le = LabelEncoder()
data['ord_2'] = le.fit_transform(data['ord_2'])
sbn.set(style ="darkgrid")
sbn.countplot(data['ord_2'])
from sklearn.preprocessing import OneHotEncoder
en = OneHotEncoder()
en = en.fit_transform(data[['nom_0']]).toarray()
encoded_colm = pd.DataFrame(en)
data= pd.concat([data, encoded_colm], axis=1)
data= data.drop(['nom_0'], axis=1)
data.head(10)
data = pd.get_dummies(df, prefix=['bin_2'], columns=['bin_2'])
data.head(10)
``
##  titanic.csv
``
 import pandas as pd
import seaborn as sbn
dt=pd.read_csv("/content/titanic_dataset.csv")
dt.info()
dt.isnull().sum()
dt['Age']=dt['Age'] . fillna(dt ['Age'].mean())
dt ['Cabin']=dt['Cabin']. fillna(dt['Cabin']. mode() [0])
dt ['Embarked']=dt['Embarked'] . fillna(df ['Embarked'].mode( )[0])
dt.isnull().sum( )
from sklearn.preprocessing import LabelEncoder
lc = LabelEncoder()
df['Sex'] = lc.fit_transform(df['Sex'])
sbn.set(style ="darkgrid")
sbn.countplot(df['Sex'])
from sklearn.preprocessing import OneHotEncoder
enc= OneHotEncoder()
enc= enc.fit_transform(dt[['Name']]).toarray()
encoded_colm = pd.DataFrame(enc)
dt= pd.concat([dt, encoded_colm], axis=1)
dt= dt.drop(['Name'], axis=1)
dt.head(10)
dt = pd.get_dummies(dt, prefix=['Ticket'] ,columns=['Ticket'])
df.head(10)
dt = pd.get_dummies(dt, prefix=['Embarked'] ,columns=['Embarked'])
df.head(10)
``
## OUPUT

## Data.csv
![image](https://user-images.githubusercontent.com/103020162/232278121-a4b5a4d9-765e-40da-994d-244f5562b88e.png)

![image](https://user-images.githubusercontent.com/103020162/232278140-c34ae3ad-f880-4d6b-bbc0-f8f38187b1cd.png)

![image](https://user-images.githubusercontent.com/103020162/232278162-c01b7c17-2e44-4946-bc7d-1bdd7ae26439.png)

![image](https://user-images.githubusercontent.com/103020162/232278178-4cd19e11-30e6-4545-a095-3c2f13e5d360.png)

![image](https://user-images.githubusercontent.com/103020162/232278211-1963e708-2ffa-44d8-a28d-7b89a773f4a4.png)

## Encoding.csv

![image](https://user-images.githubusercontent.com/103020162/232278250-6d092bdc-020f-4558-9f28-aea9bb4a855a.png)

![image](https://user-images.githubusercontent.com/103020162/232278276-cf8d88be-3553-474d-91cd-106fc145be1d.png)

![image](https://user-images.githubusercontent.com/103020162/232278316-41521c0b-be59-4656-9140-ee425b68f13e.png)

![image](https://user-images.githubusercontent.com/103020162/232278335-42cf76f6-ed12-4867-bfca-5a1921d4c5f7.png)

## Titanic.csv

![image](https://user-images.githubusercontent.com/103020162/232278351-4736dc89-017b-467d-b1f6-721b13a5ec6e.png)

![image](https://user-images.githubusercontent.com/103020162/232278374-ecdec98f-3c42-4800-9329-5260fc00067e.png)

![image](https://user-images.githubusercontent.com/103020162/232278384-4753099d-ce11-470a-b55f-ce88fab4a68b.png)

![image](https://user-images.githubusercontent.com/103020162/232278451-e7e24d2c-79aa-442e-a813-4a83fdb98274.png)

![image](https://user-images.githubusercontent.com/103020162/232278538-9b14a7ad-84d0-4bd4-bc7b-19ffa93030fe.png)

![image](https://user-images.githubusercontent.com/103020162/232278566-a4b78ad5-b9a7-4f04-b968-b6a470f9eaeb.png)

## RESULT:

Thus the program for Feature Generation is executed successfully.
