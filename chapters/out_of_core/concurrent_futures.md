# Concurrent Futures

A more modern and flexible approach can be found in the standard libraries `concurrent.futures` module.

The usage is quite similar to the way we used `multiprocessing` before.

Now we're chosing an appropriate `Executor` to do the job.


Import section:

```{code} python
# Instead
import multiprocessing as mp

# do
import concurrent.futures as cf

```

Main block:

```{code} python
# Instead
with mp.Pool() as pool:
    iterations = pool.map(my_mandel_row, y)

# do
with cf.ProcessPoolExecutor() as executor:
    iterations = executor.map(my_mandel_row, y)
```

If you're adventoureous use 

```{code} python
with cf.ThreadPoolExecutor() as executor:
    iterations = executor.map(my_mandel_row, y)
```

to try your luck with  a `Threads` based exeutor and enjoy the **GIL**
