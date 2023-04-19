# Local machine without GPU acceleration

**Do's:**

- Use `numbas` *jit* features in a fire and forget manner.
Just decorate your functions with a `numba.jit` and see if this already does the trick.

- Or make use of the `numpy` api as often as possible to get nuerical focus and faster execution.

- Use the *divide and conquer* pattern to split up the workload and use the `concurrent.futures` interface to create a `ProcessPoolExecutor` executing it in parallel. 

- Move forward to more specialized libraries implementing a `numpy` like interface.
The changes to make here will be usually very subtle and can be done iteratively without eating to much time.

**Dont's:**

- Do not use `ThreadPoolExecutors` due to the GIL.

- Do not mix `numba` and `concurrent.futures` based approaches, as usually `numba` will target all available cores already
