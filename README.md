# EX-03 UNIVARIATE ANALYSIS
### Aim:
To read the given data and perform the univariate analysis with different types of plots.
### Explanation:
Univariate analysis is basically the simplest form to analyze data. Uni means one and this means that the data has only one kind of variable. The major reason for univariate analysis is to use the data to describe. The analysis will take data, summarise it, and then find some pattern in the data.
### Algorithm:
- Step1: Read the given data.
- Step2: Get the information about the data.
- Step3: Remove the null values from the data.
- Step4: Mention the datatypes from the data.
- Step5: Count the values from the data.
- Step6: Do plots like boxplots,countplot,distribution plot,histogram plot.
### Program:
```
Developed By: ROHIT JAIN D
Register Number: 212222230120
```

- Diabetes.csv
```Python 
import pandas as pd
import seaborn as sns
import numpy as np
from scipy import stats
from google.colab import files
uploaded=files.upload()
df=pd.read_csv('diabetes.csv')
df.head()
df.describe()
df.isnull().sum()
df.info()
sns.boxplot(x="Glucose",data=df)
Glucose_q1 = df['Glucose'].quantile(0.25)
Glucose_q3 = df['Glucose'].quantile(0.75)
Glucose_IQR = Glucose_q3 - Glucose_q1
Glucose_low = Glucose_q1 - 1.5 * Glucose_IQR
Glucose_high = Glucose_q3 + 1.5 * Glucose_IQR
df=df[((df['Glucose']>=Glucose_low)&(df['Glucose']<=Glucose_high))]
sns.countplot(x="Glucose",data=df)
sns.distplot(df['Glucose'])
sns.histplot(x="Glucose",data=df)
```
- Output(diabetes.csv) :<br>
<img height=10% width=100% src="https://github.com/ROHITJAIND/EX-03-UNIVARIATE-ANALYSIS/assets/118707073/1d3b12f6-7b20-4d55-bc5b-aa87020d5b89">
<img height=20% width=100% src="https://github.com/ROHITJAIND/EX-03-UNIVARIATE-ANALYSIS/assets/118707073/fa9b48c9-50b2-4c7d-a41b-7dd97ccbeffa">
<img height=20% width=40% src="https://github.com/ROHITJAIND/EX-03-UNIVARIATE-ANALYSIS/assets/118707073/df172427-658f-4dab-a2e1-4a8ff56c8639">
<img height=20% width=50% src="https://github.com/ROHITJAIND/EX-03-UNIVARIATE-ANALYSIS/assets/118707073/a079d5b0-5e56-4a79-8b82-b23e79c26f2d">
<img height=22% width=49% src="https://github.com/ROHITJAIND/EX-03-UNIVARIATE-ANALYSIS/assets/118707073/6b8f321b-1b0b-4ef6-b1a3-15ccdb51d5f9">
<img height=22% width=49% src="https://github.com/ROHITJAIND/EX-03-UNIVARIATE-ANALYSIS/assets/118707073/5ec1bd77-8ae4-46d5-ba61-15279960d57d">
<img height=22% width=49% src="https://github.com/ROHITJAIND/EX-03-UNIVARIATE-ANALYSIS/assets/118707073/40ca042e-5c75-42e0-8786-c26c54039280">
<img height=22% width=49% src="https://github.com/ROHITJAIND/EX-03-UNIVARIATE-ANALYSIS/assets/118707073/c275a6cf-0d5e-4783-b4cc-5bd5999d1a07">
- SuperStore.csv:

```Python
import pandas as pd
import seaborn as sns
import numpy as np
from scipy import stats
from google.colab import files
uploaded=files.upload()
df=pd.read_csv('SuperStore.csv')
df.head()
df.describe()
df.isnull().sum()
df.info()
df['Postal Code']=df['Postal Code'].fillna(method='ffill')
sns.boxplot(x='Postal Code', data=df)
sns.countplot(x='Postal Code',data=df)
sns.distplot(df["Postal Code"])
sns.histplot(x="Postal Code",data=df)
```
- Output(SuperStore.csv) :  
<img height=10% width=100% src="https://github.com/ROHITJAIND/EX-03-UNIVARIATE-ANALYSIS/assets/118707073/c01fd877-a11f-4f76-942e-f8b61469d0bd">
<img height=23% width=40% src="https://github.com/ROHITJAIND/EX-03-UNIVARIATE-ANALYSIS/assets/118707073/027f846a-c889-4446-b217-5c9e041be521">
<img height=23% width=30% src="https://github.com/ROHITJAIND/EX-03-UNIVARIATE-ANALYSIS/assets/118707073/e03e85ee-9873-4f11-9182-6435206a0570">
<img height=30% width=80% src="https://github.com/ROHITJAIND/EX-03-UNIVARIATE-ANALYSIS/assets/118707073/d6554d40-d4ce-4ee9-8679-21e2fbf49ebf">
<img height=22% width=49% src="https://github.com/ROHITJAIND/EX-03-UNIVARIATE-ANALYSIS/assets/118707073/50394024-0d2b-4141-95bb-0792351caf8d">
<img height=22% width=49% src="https://github.com/ROHITJAIND/EX-03-UNIVARIATE-ANALYSIS/assets/118707073/4dc2f8ef-9d9e-4408-a4f5-28f2c7091bf0">
<img height=22% width=49% src="https://github.com/ROHITJAIND/EX-03-UNIVARIATE-ANALYSIS/assets/118707073/8c10f57f-7bea-4eb2-8b3d-cb91624fb331">
<img height=22% width=49% src="https://github.com/ROHITJAIND/EX-03-UNIVARIATE-ANALYSIS/assets/118707073/242cf82d-98d0-44c8-a02b-b2b7cd24650f">

- employeesal.csv:
```Python
import pandas as pd
import seaborn as sns
import numpy as np
from scipy import stats
from google.colab import files
uploaded=files.upload()
df=pd.read_csv('employeesal.csv')
df.head()
df.describe()
df.isnull().sum()
df.info()
sns.boxplot(x='Experience_Years',data=df)
sns.countplot(x="Experience_Years",data=df)
sns.distplot(df['Experience_Years'])
sns.histplot(x="Experience_Years",data=df)
```
- Output(employeesal.csv) :
<br>

<img height=22% width=49% src="https://github.com/ROHITJAIND/EX-03-UNIVARIATE-ANALYSIS/assets/118707073/3c6aa2b1-a2c9-4e5c-b244-c1fd7b95de74">
<img height=22% width=49% src="https://github.com/ROHITJAIND/EX-03-UNIVARIATE-ANALYSIS/assets/118707073/50535ce5-798d-4689-a510-8b64542272e2">
<img height=22% width=49% src="https://github.com/ROHITJAIND/EX-03-UNIVARIATE-ANALYSIS/assets/118707073/7d5f1c67-e2ec-403f-908b-bba9fc6a1923">
<img height=22% width=49% src="https://github.com/ROHITJAIND/EX-03-UNIVARIATE-ANALYSIS/assets/118707073/d33eeccd-9096-470d-852f-1d7d5e76b979">
<img height=22% width=49% src="https://github.com/ROHITJAIND/EX-03-UNIVARIATE-ANALYSIS/assets/118707073/73f32d4e-4fbc-46c7-bd18-18cc201e5998">
<img height=22% width=49% src="https://github.com/ROHITJAIND/EX-03-UNIVARIATE-ANALYSIS/assets/118707073/bbdeff51-b108-4786-9223-8f6e825262a7">
<img height=22% width=49% src="https://github.com/ROHITJAIND/EX-03-UNIVARIATE-ANALYSIS/assets/118707073/9506c400-a405-424e-bbd8-5fc0417c3572">
<img height=22% width=49% src="https://github.com/ROHITJAIND/EX-03-UNIVARIATE-ANALYSIS/assets/118707073/e574c9ed-8fdb-4f37-ad51-d8294e17a846">

### Result:
Thus we have read the given data and performed the univariate analysis with different types of plots.
