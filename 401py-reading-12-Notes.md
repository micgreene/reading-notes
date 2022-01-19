# 10 Minutes to Pandas

**This is a short introduction to pandas, geared mainly for new users.**
+ Customarily, we import as follows:
  + `import numpy as np`
  + `import pandas as pd`

### Object creation

+ Creating a Series by passing a list of values, letting pandas create a default integer index:

`s = pd.Series([1, 3, 5, np.nan, 6, 8])`<br />
`print(s)`<br />
`{0: 1.0, 1: 3.0, 2: 5.0, 3: NaN, 4: 6.0, 5: 8.0}`<br />
`dtype: float64`<br />

+ Creating a DataFrame by passing a NumPy array, with a datetime index and labeled columns:

`dates = pd.date_range("20130101", periods=6)`<br />

`print(dates)`<br />
`DatetimeIndex(['2013-01-01', '2013-01-02', '2013-01-03', '2013-01-04', '2013-01-05', '2013-01-06'],`<br />
`dtype='datetime64[ns]', freq='D')`<br />

`df = pd.DataFrame(np.random.randn(6, 4), index=dates, columns=list("ABCD"))`

+ ^ This will create a table of 4 rows headed by the input dates from the dates list we created above and 4 columns named 'ABCD' like we chose in the DataFrane() method.
Creating a DataFrame by passing a dict of objects that can be converted to series-like.

`df2 = pd.DataFrame({`<br />
          `"A": 1.0,`<br />
          `"B": pd.Timestamp("20130102"),`<br />
          `"C": pd.Series(1, index=list(range(4)), dtype="float32"),`<br />
          `"D": np.array([3] * 4, dtype="int32"),`<br />
          `"E": pd.Categorical(["test", "train", "test", "train"]),`<br />
          `"F": "foo",`<br />
     `})`<br />

+ The columns of the resulting DataFrame have different dtypes.

`df2.dtypes`<br />
 <br />
`A           float64`<br />
`B    datetime64[ns]`<br />
`C           float32`<br />
`D             int32`<br />
`E          category`<br />
`F            object`<br />
`dtype: object`<br />

+ If you’re using IPython, tab completion for column names (as well as public attributes) is automatically enabled. The columns A, B, C, and D are automatically tab completed. E and F are there as well; the rest of the attributes have been truncated for brevity.
  
### Viewing data

+ Here is how to view the top and bottom rows of the frame:
  + df.head() #displays each row from beginning
  + df.tail(3)#displays each row from end

+ Display the index, columns:
  + df.index # a list of all indices:
    + `DatetimeIndex(['2013-01-01', '2013-01-02', '2013-01-03', '2013-01-04', '2013-01-05', '2013-01-06'], dtype='datetime64[ns]', freq='D')`
  + df.columns
    + `Index(['A', 'B', 'C', 'D'], dtype='object')`

+ DataFrame.to_numpy() gives a NumPy representation of the underlying data. 
+ *Note that this can be an expensive operation when your DataFrame has columns with different data types*
+ Which comes down to a fundamental difference between pandas and NumPy: 
  + NumPy arrays have one dtype for the entire array
  + pandas DataFrames have one dtype per column. 
+ When you call DataFrame.to_numpy(), pandas will find the NumPy dtype that can hold all of the dtypes in the DataFrame. This may end up being object, which requires casting every value to a Python object.
