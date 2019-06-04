# Pandas

## Loading data

**Reading from multiple files**

``` python
import glob, os
df = pd.concat(map(pd.read_csv, glob.glob(os.path.join('../data/raw/', '*.csv'))), 
               ignore_index=True)
```

Explanation: in the above command `glob.glob(os.path.join('../data/raw/', '*.csv'))` returns a list of all `.csv` files in the stated directory. The **map()** function "returns a list of the results after applying the given function to each item of a given iterable (list, tuple etc.)" ([Geeks For Geeks](https://www.geeksforgeeks.org/python-map-function/)).
