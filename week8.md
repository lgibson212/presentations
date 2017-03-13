# How do you iterate over rows in a DataFrame in Pandas? Provide at least two ways to solve the question.

###dataframe.iterrows()
- Iterate over the rows of a DataFrame as (index, Series) pairs.
- uses a generator: next()


Because iterrows returns a Series for each row, it does not preserve dtypes across the rows (dtypes are preserved across columns for DataFrames). For example,

```python
>>> df = pd.DataFrame([[1, 1.5]], columns=['int', 'float'])
>>> row = next(df.iterrows())[1]
>>> row
int      1.0
float    1.5
Name: 0, dtype: float64
>>> print(row['int'].dtype)
float64
>>> print(df['int'].dtype)
int64
```

To preserve dtypes while iterating over the rows, it is better to use itertuples() which returns tuples of the values and is generally faster than iterrows.


###dataframe.itertuples(index=True)
- Iterate over the rows of a DataFrame as tuples of the values.
  - index value as first element of the tuple

```python
>>> df = pd.DataFrame({'col1': [1, 2], 'col2': [0.1, 0.2]}, index=['a', 'b'])
>>> df
   col1  col2
a     1   0.1
b     2   0.2
>>> for row in df.itertuples():
...     print(row)
('a', 1, 0.10000000000000001)
('b', 2, 0.20000000000000001)
```


references:
- http://pandas.pydata.org/pandas-docs/version/0.17.0/generated/pandas.DataFrame.iterrows.html
- http://pandas.pydata.org/pandas-docs/version/0.17.0/generated/pandas.DataFrame.itertuples.html



