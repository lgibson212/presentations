# How do you iterate over rows in a DataFrame in Pandas? Provide at least two ways to solve the question.

###iterrows()
- Iterate over the rows of a DataFrame as (index, Series) pairs.
- uses a generator


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


###itertuples()
- Iterate over the rows of a DataFrame as tuples of the values.



