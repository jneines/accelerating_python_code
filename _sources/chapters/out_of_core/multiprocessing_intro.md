# Use of multiprocessing

The oldest approach that is possible comes with the standard library and can be found in the `multiprocessing` module.

A `Pool` class is available here, which offers a *context manager* to manage our workload.

It's `map` method can be used to *map* a callable on a list of inputs.

As the function that is called is not allowed to have more than one parameter, we have to modify our function call by using `functools.partial` to settle all the other parameters that can considered to be constant.

Once all method calls have been executed, the result contains all return values in a list matching the length of the input array.
This in turn is our desired 2D `iterations` array again.

