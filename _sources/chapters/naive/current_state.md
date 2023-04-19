# Current state

We still have no good idea of how the `Mandelbrot Set` actually looks like in the complex plain.
A simple overview on which numbers are in, and who is out.

A better idea to display the `Mandelbrot Set` is to mark the numbers which belong to it using a specified color and colorize the rest using an escape time algorithm, such as using the number of iterations it took until the convergence rule was no longer fulfilled.

This strategy helps us to implement the most straight forward implementation of an algorithm to render the mandelbrot set.
