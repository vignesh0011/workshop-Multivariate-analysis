# WORKSHOP - MULTIVARIATE ANALYSIS

## AIM: 

To Perform Multivariate Analysis

## ALGORITHM:

1.Read the given data

2.Get information from the data

3.Perform the Multivariate Analysis

4.Save the clean data to file

## PROGRAM:
~~~
Developed by: M VIGNESH
Regno: 212220233002
~~~
~~~
import pandas as pd

import numpy as np

import seaborn as sns

import matplotlib.pyplot as plt

import io

from google.colab import files

uploaded = files.upload()

dd = pd.read_csv(io.BytesIO(uploaded['FlightInformation.csv']))

print(dd)
~~~

## Types of Bivariate Analysis:

## (i) Numerical & Numerical
sns.scatterplot (dd['Date_of_Journey'],dd['Dep_Time'])

![1](https://user-images.githubusercontent.com/53014593/195491340-68a3bc53-3938-457c-bae4-2138d5c5ff99.png)

## (ii) Numerical & Categorical
sns.barplot (x=dd['Duration'],y=dd['Price'])

![2](https://user-images.githubusercontent.com/53014593/195491432-7694c436-7caa-4e9d-9ddc-3b2a55e19f1b.png)

sns.barplot(x=dd["Arrival_Time"],y=dd["Price"],data=dd)

![3](https://user-images.githubusercontent.com/53014593/195491501-48e2b95b-a751-495e-bf50-4f3b33335862.png)

states=dd.loc[:,["Duration","Price"]]

states=states.groupby(by=["Duration"]).sum().sort_values(by="Price")

sns.barplot(x=states.index,y="Price",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("Duration")

plt.ylabel=("Price")

plt.show()

![4](https://user-images.githubusercontent.com/53014593/195491650-bd1ce9da-0399-469f-ad84-4f02854f6f6b.png)

## Multivariate Analysis

dd.corr()

data = np.random.randint(low = 1, high = 100, size = (10, 10))

print("The data to be plotted:\n")

print(data)

hm = sns.heatmap(data = data)

plt.show()

![5](https://user-images.githubusercontent.com/53014593/195491749-357f3918-d627-4566-85ab-44b21a758900.png)


## RESULT:
Thus, Bivariate/Multivariate Analysis is performed  successfully.







