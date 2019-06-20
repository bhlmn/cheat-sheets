Multiprocessing

``` python
import multiprocessing as mp
# When an error occurs, specify which process in the logging.
mp.log_to_stderr(logging.WARN)

n_threads = 12
p = mp.Pool(processes=n_threads)
p.starmap(func, zip(args1, args2))
```
