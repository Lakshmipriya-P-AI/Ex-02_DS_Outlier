# Ex-02_DS_Outlier

# AIM:
To detect and remove the outliers from the given csv file.

# ALGORITHM:
Step 1 : Create a new file in jupyter notebook.

Step 2 : Upload the given csv file.

Step 3 : Open the csv file.

Step 4 : Write codes for outliers detection and removal operation.

Step 5 : Use quantile formulas and boxplot.

Step 6 : End the program.

# Program :
```
import pandas as pd
df = pd.read_csv("WEIGHT.csv")
df
df.drop('Gender',axis=1)
df
df.drop('Gender',inplace = True,axis =1)
df
df.boxplot()
import numpy as np
from scipy import stats
z = np.abs(stats.zscore(df))
z
df1 = df.copy()
df1 = df[(z<3).all(axis = 1)]
df1
df2 = df1.copy()
q1 = df2.quantile(0.25)
q3 = df2.quantile(0.75)
IQR = q3-q1
df3 = df2[((df2>=q1-1.5*IQR) & (df2>=q1-1.5*IQR)).all(axis =1)]
df3
df3.boxplot()
```

# OUTPUT
![output1](https://user-images.githubusercontent.com/93427923/161434953-340c00dd-f253-4df9-9233-0c072a7b655c.png)

![output2](https://user-images.githubusercontent.com/93427923/161434969-42290b34-d767-4a76-aeb6-dcf7212fbad6.png)

![output3](https://user-images.githubusercontent.com/93427923/161434978-673c0c52-51c3-4e07-b75f-c40f2deeb035.png)

![output4](https://user-images.githubusercontent.com/93427923/161434987-4e71d278-e341-49f0-baa7-104eecce3b95.png)

# Result:
Thus the Outliers are detected and removed from the Dataset.
