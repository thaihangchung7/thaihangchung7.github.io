---
layout: notes
title: Accelerated Computing 
---

A collection of notes for efficient computing.

## Numba
Numba is an Python Just In Time compiler that essentially translates Python functions into fast machine code using LLVM. With the relatively recent boom of data-driven programming, Numba's library is gaining more attention from its developers and [community](https://github.com/numba/numba). (Sponsored by NVidia, Anaconda, Inc., DARPA, Intel...)

In the documentation, Numba advertises JIT performace similar to C, C++, and Fortran!  

### When and where should you use Numba?
Numba's motto is to keep things simple. You shouldn't have to spend hours optimizing code when the opportunity cost isn't worth it. In many cases, Numba has the benefit of massively accelerating your computing with little code modification. If the following describes your code, Numba can help you out:
 - Numerically oriented
 - Uses lots of numpy
 - loops

***Prescription drug ad disclaimer: Numba can speed these up [but keep Numba's limitations in mind (see "What's the catch" section for more details")]***  

### The @jit decorator
Let's see what's going on under the hood...

<img src="/assets/jitcompile.PNG" width=640 height=360 class="center">

When you add the ``` @jit ``` decorator, Numba analyzes the Python bytecode and translates it to Numba IR (think of this as Numba's own bytecode) which is "lowered" to a low-level, machine specific language using the LLVM compiler (think Assembly). Then by passing ```cache=True```, this is also True by default, you can instruct Numba to write the resulting compilation into a cache, which avoids compilation time on the next run. 

### No Python Mode
You can instruct Numba to compile your function independent of the Python interpreter. In fact, this is considered "best practice" as it leads to the best performace. 

You can tell Numba to execute No Python mode in two ways:

``` @jit (nopython=True) ```

or its alias:

``` @njit ```

However, you need to use ```from njit import numba``` for the latter.

### Object Mode
If Numba comes across Python code it cannot understand, it falls back to "Object Mode". For instance, as of Numba 0.51.2, dictionaries are not supported. If you try to compile a function with a dictionary with ```@jit```, you may be surprised to see that Numba was still able to compile the function since it uses Object mode to enable other Numba functionality.

But given what was just said, in many cases, you can tell Numba provide information when type interface fails by pass the ``` nopython=True ```. In this case, you will come across the error:

``` - argument 0: cannot determine Numba type of <class 'dict'> ```


### Numba ```@vectorize```
A common used tool in ```numpy```'s library are ```ufunc```s

To optimize a ```ufunc``` with Numba, decorate the function with ```@vectorize```. Another added benefit to using Numba is that it will figure out broadcasting rules for different arrays with compatible dimensions.


### What's the catch?
The first time you throw ```@jit``` on top of you function, you will find that your function actually take longer to run. Why?

Since Numba is a JIT compiler, when you run the function, Numba will compile the code using LLVM for the first run, introducing some overhead. Once the code is cached and ran a second time, it will result in an optimized run time. 

There is partial support for the Pandas library.

## Python Benchmarking

### Python magic ``` %timeit ```
When benchmarking Numba code, it would be best to use ``` %timeit ``` which runs a function or loop multiple times to accurately get an estimate of run time. The output is the mean and standard deviation of multiple runs. Hence, accomadating for the compilation time of the first execution. 


