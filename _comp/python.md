---
layout: notes
title: Python 
---

Table of Contents
=================

   * [Numba](#numba)
      * [When and where should you use Numba?](#when-and-where-should-you-use-numba)
      * [The @jit decorator](#the-jit-decorator)
      * [No Python Mode](#no-python-mode)
      * [Object Mode](#object-mode)
      * [Numba @vectorize](#numba-vectorize)
      * [What's the catch?](#whats-the-catch)
   * [Python Benchmarking](#python-benchmarking)
      * [Python magic %timeit](#python-magic-timeit)

# Numba
Numba is an Python Just In Time compiler that essentially translates Python functions into fast machine code using LLVM. With the relatively recent boom of data-driven programming, Numba's library is gaining more attention from its developers and [community](https://github.com/numba/numba). (Sponsored by NVidia, Anaconda, Inc., DARPA, Intel...)

In the documentation, Numba advertises JIT performace similar to C, C++, and Fortran!  

## When and where should you use Numba?
Numba's motto is to keep things simple. You shouldn't have to spend hours optimizing code when the opportunity cost isn't worth it. In many cases, Numba has the benefit of massively accelerating your computing with little code modification. If the following describes your code, Numba can help you out:
 - Numerically oriented
 - Uses lots of numpy
 - loops

***Prescription drug ad disclaimer: Numba can speed these up [but keep Numba's limitations in mind (see "Limitations to be aware of" section for more details)]***  

### The @jit decorator
Let's see what's going on under the hood...

<img src="/assets/jitcompile.PNG" width=640 height=360 class="center">
<div style="text-align:center">
<a href="https://julialang.org/benchmarks/">julia language benmarks</a>
</div> 

When you add the ``` @jit ``` decorator, Numba analyzes the Python bytecode and translates it to Numba IR (think of this as Numba's own bytecode) which is "lowered" to a low-level, machine specific language using the LLVM compiler (think Assembly). Then by passing ```cache=True```, this is also True by default, you can instruct Numba to write the resulting compilation into a cache, which avoids compilation time on the next run. 

### No Python Mode
You can instruct Numba to compile your function independent of the Python interpreter. In fact, this is considered "best practice" as it leads to the best performace. 

You can tell Numba to execute No Python mode in two ways:

```python
@jit (nopython=True) 
```

or its alias:

```python 
@njit 

```

However, you need to use ```from njit import numba``` for the latter.

### Object Mode
If Numba comes across Python code it cannot understand, it falls back to "Object Mode". For instance, as of Numba 0.51.2, dictionaries are not supported. If you try to compile a function with a dictionary with ```@jit```, you may be surprised to see that Numba was still able to compile the function since it uses Object mode to enable other Numba functionality.

But given what was just said, in many cases, you can tell Numba provide information when type interface fails by passing ``` nopython=True ``` into the decorator argument. In this case, you will come across the error:

``` python

- argument 0: cannot determine Numba type of <class 'dict'> 

```

### Numba ```@vectorize```
To optimize a ```ufunc``` with Numba, decorate the function with ```@vectorize```. This will instruct Numba to parallelize the function that is decorated. Some arguments will need to be passed in order to process the function on the GPU. 

When working with Numpy arrays, another benefit to using Numba is that it will figure out broadcasting rules for different arrays with compatible dimensions.


## Numba Limitations to be aware of
### First time compiling
The first time you throw ```@jit``` on top of you function, you will find that your function actually take longer to run. Why?

Since Numba is a JIT compiler, when you run the function, Numba will compile the code using LLVM for the first run, introducing some overhead. Once the code is cached and ran a second time, it will result in an optimized run time.
### Supported Python
There is work to support as much of the Python language as possible but some widely used features are not available in Numba compiled functions:

+ dict/list/exception/set are partially supported (usually means you have to use an alternative e.g. typed lists)

+ mixing types confuses Numba

+ Some popular libraries are partially supported(p)/not supported(n):
  - numpy (p)
  - pandas (n)
  - pypy (?)


## Python Benchmarking

### Python magic ``` %timeit ```
When benchmarking Numba code, it would be best to use ``` %timeit ``` which runs a function or loop multiple times to accurately get an estimate of run time. The output is the mean and standard deviation of multiple runs. Hence, accomodating for the compilation time of the first execution. 

# NumPy

## NumPy ufuncs

NumPy arrays operate element-wise. NumPy ```ufuncs``` or "universal functions" operate in the same fashion. For instance, ```np.sin(a)``` applies $$sin$$ to **each** element in array ```a``` .

# Solving ODE's with Runge Kutta Methods

As a step up from Euler

# Python Idiosynchrasies

## ```if __name__ = __main__```

Colloquially, when this shows up in python code, this signals to those who are reading it that this particular file is running as a script. 
