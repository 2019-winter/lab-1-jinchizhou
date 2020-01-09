---
jupyter:
  jupytext:
    formats: ipynb,md
    text_representation:
      extension: .md
      format_name: markdown
      format_version: '1.1'
      jupytext_version: 1.2.4
  kernelspec:
    display_name: Python 3
    language: python
    name: python3
---

Jinchi Zhou


**Instructions:** This is an individual assignment, but you may discuss your code with your neighbors.


# Python and NumPy

While other IDEs exist for Python development and for data science related activities, one of the most popular environments is Jupyter Notebooks.

This lab is not intended to teach you everything you will use in this course. Instead, it is designed to give you exposure to some critical components from NumPy that we will rely upon routinely.

## Exercise 0
Please read and reference the following as your progress through this course. 

* [What is the Jupyter Notebook?](https://nbviewer.jupyter.org/github/jupyter/notebook/blob/master/docs/source/examples/Notebook/What%20is%20the%20Jupyter%20Notebook.ipynb#)
* [Notebook Tutorial](https://www.datacamp.com/community/tutorials/tutorial-jupyter-notebook)
* [Notebook Basics](https://nbviewer.jupyter.org/github/jupyter/notebook/blob/master/docs/source/examples/Notebook/Notebook%20Basics.ipynb)

**In the space provided below, what are three things that still remain unclear or need further explanation?**


Will we be using simple panda commands? I think that is more of data manipulation rather than analyzing. 


## Exercises 1-7
For the following exercises please read the Python appendix in the Marsland textbook and answer problems A.1-A.7 in the space provided below.


## Exercise 1

```python
import numpy as np
a = np.full((6, 4), 2)
print(a)
```

## Exercise 2

```python
b = np.full((6, 4), 1)
np.fill_diagonal(b, 3)
print(b)
```

## Exercise 3

```python
print(a*b)
# Dot uses Matrix multiplication. (6x4) * (6x4) doesn't work
```

## Exercise 4

```python
print(a.transpose())

print(np.dot(a.transpose(), b)) # (4x6) * (6x4) = (4x4)
print(np.dot(a, b.transpose())) # (6x4) * (4x6) = (6x6)
```

## Exercise 5

```python

def rando(a):
    print(a);
        
array = np.array([5, 6, 7]);
rando(array)
```

## Exercise 6

```python
arr = np.random.random(10)
print(arr)

print("Sum is", np.sum(arr)) # sum
print("Mean is", np.mean(arr)) # Mean
print("Median is", np.median(arr)) # Median

```

## Exercise 7

```python
c = np.full((6, 7), 1)

def countOnes(array):
    ct = 0;
    for i in range(len(array)):
        for j in range(len(array[0])):
            if (array[i][j] == 1):
                ct+=1;
                
    return ct

print(countOnes(c))
```

## Excercises 8-???
While the Marsland book avoids using another popular package called Pandas, we will use it at times throughout this course. Please read and study [10 minutes to Pandas](https://pandas.pydata.org/pandas-docs/stable/getting_started/10min.html) before proceeding to any of the exercises below.


## Exercise 8
Repeat exercise A.1 from Marsland, but create a Pandas DataFrame instead of a NumPy array.

```python
import pandas as pd
dfA = pd.DataFrame(np.full((6, 4), 2))
print(dfA)
```

## Exercise 9
Repeat exercise A.2 using a DataFrame instead.

```python
dfB = pd.DataFrame(np.full((6, 4), 1))

np.fill_diagonal(dfB.values, 3)
dfB
```

## Exercise 10
Repeat exercise A.3 using DataFrames instead.

```python
dfC = dfA.multiply(dfB)
dfC
```

## Exercise 11
Repeat exercise A.7 using a dataframe.

```python
df2 = pd.DataFrame(np.array([[1, 2, 3], [4, 1, 6], [7, 8, 9]]))

countOnes(df2)
```

## Exercises 12-14
Now let's look at a real dataset, and talk about ``.loc``. For this exercise, we will use the popular Titanic dataset from Kaggle. Here is some sample code to read it into a dataframe.

```python
titanic_df = pd.read_csv(
    "https://raw.githubusercontent.com/dlsun/data-science-book/master/data/titanic.csv"
)
titanic_df
```

Notice how we have nice headers and mixed datatypes? That is one of the reasons we might use Pandas. Please refresh your memory by looking at the 10 minutes to Pandas again, but then answer the following.


## Exercise 12
How do you select the ``name`` column without using .iloc?

```python
titanic_df['name']
```

## Exercise 13
After setting the index to ``sex``, how do you select all passengers that are ``female``? And how many female passengers are there?

```python
# titanic_df.set_index('sex',inplace=True)
titanic_df.groupby('sex').sum()

# THere are 1004 female passengers
```

## Exercise 14
How do you reset the index?

```python

```

```python

```
