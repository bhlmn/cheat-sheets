# Pandas

## Loading data

**Reading from multiple files**

``` python
import glob, os
df = pd.concat(map(pd.read_csv, glob.glob(os.path.join('../data/raw/', '*.csv'))), 
               ignore_index=True)
```

Explanation: in the above command `glob.glob(os.path.join('../data/raw/', '*.csv'))` returns a list of all `.csv` files in the stated directory. The **map()** function "returns a list of the results after applying the given function to each item of a given iterable (list, tuple etc.)" ([Geeks For Geeks](https://www.geeksforgeeks.org/python-map-function/)). In this case the **read_csv()** method is applied to each file in the list returned by **glob()** -- returning a list of dataframes. Finally, **concat()** concatenates the information from each dataframe in the list.

## Removing Duplicates

``` python
df.drop_duplicates(subset=None, keep='first', inplace=False)
```

where `subset` is a column label or list of column labels to be considered. By default all columns are considered.

## Bootstrap analysis

I'm in search of the quickest way to do bootstrap analysis. I've come up with a two-liner:

``` python
# Imports and set sample size.
import pandas as pd
import numpy as np
samples = 1000

# Create a random dataframe and run the analysis.
df = pd.DataFrame(np.random.randn(5000, 5), columns=['a', 'b', 'c', 'd', 'e'])
pd.DataFrame([df.sample(n=len(df), replace=True).mean() for i in range(samples)]).describe(percentiles=[.1, .25, .5, .75, .9])
```
