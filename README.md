# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output

import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df 


![Screenshot 2025-03-07 111324](https://github.com/user-attachments/assets/3f7ce120-3356-454b-ab68-1cc9b65a024f)

df.fillna({'NAME':'KESAV','GENDER':'MALE'}) 

![Screenshot 2025-03-07 111356](https://github.com/user-attachments/assets/6bdeb50a-a2e9-49af-9d19-5670a564582f)

df.head() 
![Screenshot 2025-03-07 111459](https://github.com/user-attachments/assets/7e4a1a25-4d4d-43e6-9957-081d6c674daf)

df.notnull()
![Screenshot 2025-03-07 111521](https://github.com/user-attachments/assets/a58d9e30-c338-44a9-a77f-2fca400eb35a)

df.fillna(100)
![Screenshot 2025-03-07 111539](https://github.com/user-attachments/assets/f6d4b0c5-3cf1-4570-aaf2-e8dbcb551d8f)

df.dropna(axis=0)
![Screenshot 2025-03-07 111644](https://github.com/user-attachments/assets/c940a72d-610d-4a9c-9c09-b0e944059273)


df.dropna(axis=1)
![Screenshot 2025-03-07 111718](https://github.com/user-attachments/assets/1d8659b1-13ea-44a9-86bd-0854ae9f4240)

df.fillna(method='bfill')
![Screenshot 2025-03-07 111738](https://github.com/user-attachments/assets/3c628031-01e9-4092-a228-cd31738a830a)


df.fillna(method='ffill')
![Screenshot 2025-03-07 111752](https://github.com/user-attachments/assets/5fdf91c6-08f7-4478-b1da-9023e0bede90)

df.isnull().any()
![Screenshot 2025-03-07 111803](https://github.com/user-attachments/assets/c9dbfab1-9ff8-43fc-8786-c19e4baed933)

df.isnull().sum()
![Screenshot 2025-03-07 111818](https://github.com/user-attachments/assets/369d515a-c53a-4083-9339-ea7c90c14b24)

df.tail()
![Screenshot 2025-03-07 111834](https://github.com/user-attachments/assets/ec451f4f-2d5f-4650-b75b-e0941d866206)

df.isnull()
![Screenshot 2025-03-07 111843](https://github.com/user-attachments/assets/a3a6f5cc-8809-4f1c-9e9b-434b16315c2c)

import pandas as pd
df=pd.read_csv("/content/iris.csv")
df

![Screenshot 2025-03-07 111855](https://github.com/user-attachments/assets/bd5c3787-2320-41bd-8893-7ceef96b058f)

df.info()
![Screenshot 2025-03-07 112006](https://github.com/user-attachments/assets/dca831d5-733b-4dea-bbe8-d537584583a4)

df.shape
![Screenshot 2025-03-07 112029](https://github.com/user-attachments/assets/8a68383f-4772-41dd-ac6e-31747162a065)

import seaborn as sns
sns.boxplot(x='sepal_length',data=df)
![Screenshot 2025-03-07 112041](https://github.com/user-attachments/assets/f1b73123-753f-4d67-9af8-2c42ca1b638a)

 rid=df[((df.sepal_width<(q1-1.5*iqr))|(df.sepal_width>(q3+1.5*iqr)))]
 df['sepal_width']
 
![Screenshot 2025-03-07 112052](https://github.com/user-attachments/assets/64630316-9e15-4673-b07d-99b8ce3d52fd)

 delid=df[~((df.sepal_width<(q1-1.5*iqr))|(df.sepal_width>(q3+1.5*iqr)))]
 delid
![Screenshot 2025-03-07 112114](https://github.com/user-attachments/assets/7b02d09f-fe7f-4d42-b518-73765e58e56a)

sns.boxplot(x='sepal_width',data=delid)

![Screenshot 2025-03-07 112138](https://github.com/user-attachments/assets/408976b1-cb31-4be6-8c54-4a7c042c2bf9)

q1=df.sepal_width.quantile(0.25)
q3=df.sepal_width.quantile(0.75)
iqr=q3-q1
print(iqr,q1,q3)

![Screenshot 2025-03-07 112149](https://github.com/user-attachments/assets/aef16541-5278-4ba3-92c1-194f683b214f)

 import matplotlib.pyplot as plt
 import pandas as pd
 import numpy as np
 import scipy.stats as stats
 dataset=pd.read_csv("/content/heights.csv")
 dataset
 
![Screenshot 2025-03-07 112205](https://github.com/user-attachments/assets/cc1cff20-3e76-46f6-afea-d0d54e020dca)

 df = pd.read_csv("heights.csv")
 q1 = df['height'].quantile(0.25)
 q2 = df['height'].quantile(0.5)
 q3 = df['height'].quantile(0.75)
 iqr = q3-q1
 iqr
 ![Screenshot 2025-03-07 112212](https://github.com/user-attachments/assets/2dca03c5-f870-4c22-a055-7be5bc4487c1)

low = q1- 1.5*iqr
low
![Screenshot 2025-03-07 112221](https://github.com/user-attachments/assets/aa5e184d-a5b2-4711-a78a-4a13d24baf5c)

high=q3+1.5*iqr
high
![Screenshot 2025-03-07 112228](https://github.com/user-attachments/assets/61bc7c5a-6fe7-4f6c-b66a-70bcfe84a1e9)

 df1 = df[((df['height'] >=low)& (df['height'] <=high))]
 df1

 ![Screenshot 2025-03-07 112245](https://github.com/user-attachments/assets/e926fd35-cb9b-4fe6-a9eb-cb0a4f37abe5)

z = np.abs(stats.zscore(df['height']))
z
![Screenshot 2025-03-07 112255](https://github.com/user-attachments/assets/b508a0ad-82e0-4db7-9670-5b304d7f6182)

df1=df[z<3]
df1
![Screenshot 2025-03-07 112306](https://github.com/user-attachments/assets/9add1c0c-fbe7-4698-8029-80bcfe48fdc6)



 
















# Result
           Thus we have cleaned the data and removed the outliers by detection using IQR and Z-score method
