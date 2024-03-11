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
df=pd.read_csv("/content/SAMPLEDS.csv") print(df) image print(df.head(3)) image print(df.tail(3)) image x=df.dropna(how='any') print(x) image x=df.dropna(subset=['TOTAL'],how='any') print(x) image df image mn=df.TOTAL.mean() print(mn) image df.TOTAL.fillna(mn,inplace=True) print(df) image import pandas as pd import seaborn as sns age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94] af=pd.DataFrame(age) print(af) image sns.boxplot(data=af) image sns.scatterplot(data=af) image q1=af.quantile(0.25) q2=af.quantile(0.5) q3=af.quantile(0.75) iqr=q3-q1 iqr image low=q1-1.5iqr low image high=q3+1iqr high image af=af[((af>=low)&(af<=high))] af.dropna() image af=af[((af>=low)&(af<=high))] af.dropna() image import pandas as pd import numpy as np import seaborn as sns import pandas as pd from scipy import stats data={'weight':[12,15,18,21,24,27,30,33,39,42,45,65,78,202,17,19,92,56,1001,14,67,83]} df=pd.DataFrame(data) df image sns.boxplot(data=df) image z=np.abs(stats.zscore(df)) print(df[z['weight']>3]) image val=[12,15,18,21,24,27,30,33,39,42,45,65,78,202,17,19,92,56,1001,14,67,83] image out=[] def d_o(val): ts=3 m=np.mean(val) sd=np.std(val) for i in val: z=(i-m)/sd if np.abs(z)>ts: out.append(i) return out op=d_o(val) op image            <<include your coding and its corressponding output screen shots here>>
# Result
 Thus To read the given data and perform data cleaning and save the cleaned data to a file done successfully.

         <<include your Result here>>
