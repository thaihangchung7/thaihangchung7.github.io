---
layout: notes
title: Numerical Methods 
---

# Logistic Map

The bifrucation diagram of the logistic map is given by:

$$ x_{n+1} = r x_{n} (1 - x_{n})$$

where $$x$$ is some number between $$0$$ and $$1$$. $$n$$ denotes the iteration step. $$r$$ is the a scaling factor 

# Solving ODEs

## Using Euler's Method

Euler's method is a numerical method for approximating differential equations. As a first order method, the error per step is proportional to the square of the step size, and the error at a given time is proportional to the step size. 

Consider the differential equation $$ x'(t)=f(t,x(t)) $$. 

We can discretize the first derivative as,

$$ x'(t) = \frac{x(t+h) - x(t)}{h} + O(h)$$

where $$h$$ is the step size $$h=\Delta t$$.

The first derivative can then be approximated as,

$$ f(t,x(t)) \approx \frac{x(t+h) - x(t)}{h}$$

By letting $$x_{n+1} = x(t_{n} + h)$$ and $$x_{n} = x(t_{n}) $$, the approxmiation can be rewritten in terms of "iterative steps":

$$ x_{n+1} - x_{n} \approx h f(t,x(t)) $$

$$ x_{n+1} \approx x_{n} + h f(t_{n},x_{n})$$




# Singular Value Decomposition

Given an $$n \times p$$ matrix $$\mathbf{A}$$.  Singular Value Decomposition is summarized as:

$$\mathbf{A_{n\times p}} = \mathbf{U_{n\times n}} \mathbf{S_{n \times p}} \mathbf{V^{T}_{p \times p}} $$

some properties of $$\mathbf{U}$$ and $$\mathbf{V}$$ include,

$$\mathbf{U^{T}} \mathbf{U} = \mathbf{I_{n \times n}}$$

$$\mathbf{V^{T}} \mathbf{V} = \mathbf{I_{p \times p}}$$

# Self Organizing Maps (SOM)

A self organizing map is an unsupervised, competitive machine learning technique, as opposed to backpropogation or gradient descent used by other neural networks.

The algorithm has 1 input layer and 1 output layer. The 2nd layer is a 2 dimensional lattice of neurons or nodes usually arranged in a rectangular or hexagonal lattice. Each node is assigned a weight vector, which is related to the position of the node in the input space. 

During training, the weight vectors are updated such that the vector's distance metric is reduced without changing the original topology of the map. After training...

## SOM Algorithm

Suppose we have 20 objects (labels) with 12 parameters (features) to categorize. In other words, this input has 12 dimensions. Below steps of constructing a self organizing map is elaborated from the "alternative" steps in SOM page from [wikipedia](https://en.wikipedia.org/wiki/Self-organizing_map#Alternative_algorithm).

### 0. Hyperparamters and Learning rate

Before we begin building the SOM, we need to initialize a couple of paramters, such as a search grid plane, the learning rate, and an interation limit $$\lambda$$.


We also introduce the Euclidean distance that will be used to calculate vector distances:

$$ d(x,y) = \sqrt{ \bigg(\frac{x}{2}\bigg)^{2} + \bigg(\frac{y}{2}\bigg)^{2} } $$

later on, SciPy's implementation of Euclidean distance is used

```python

def e_distance(x,y):
  return distance.euclidean(x,y)

```

Below are some hyperparameters, non-trainable values that can be tuned for model to converge. Note that hyperparameters such as learning rate and neighborhood ranges are not set in stone. For instance if the learning rate is too small, there will be more training steps, which can lead to overfitting. Thus, these hyperparamters are generally experimentally improved such that the model is not under/over trained. 

```python

# learning grid
nx = 8
ny = 8
R_l = 0.5 #learning rate
sig = sig = ((nx/2)**2 + (ny/2)**2)**0.5
lamb = 500 #max 
max_iter = int(lamb * np.log(sig))

```

We normalize the input data in the form of a helper function using sklearn's MinMaxScaler method

```python
def normalize(data):
    scaler = MinMaxScaler()
    scaled = scaler.fit_transform(data)
    return scaled

norm_x = normalize(data_x)
```

We also split the data into training and testing ($$80%$$ for training, and $$20\%$$ for testing)

```python

train_x, test_x, train_y, test_y = train_test_split(data_x, data_y, test_size=0.2, random_state=42)

```

### 1. Randomize the node weight vectors

We first initialize a map of neuron with normalized data between 0 and 1 and randomize the weight 

Numpy's random seed is used to generate pseudo random numbers from the same seed, which will be useful for debugging purposes.

```python

"""Initiating Neuron Grid with random weights"""

num_dims = norm_x.shape[1] 
np.random.seed(40) #Random seed for debugging
weights = np.random.random_sample(size=(nx, ny, num_dims)) 

```

### 2. Traverse each node in the input data 

This step just takes the form of multiple for loops as the learning grid travels across the input data.

### 3. Update the weight vectors of the nodes in the neighborhood, including the BMU, pulling them closer to the input vector

The function below defines the "Best Matching Unit" (BMU) of the the SOM. In other words, this is where the competitive learning takes place. A sample data $$t$$, the input signal, is selected and the euclidean distance is calculated between the input and each neighboring node. The if statement returns and sets the grid position of the node that had the minimum distance computed, which also defines the **winning neuron**.

```python

def bmu(data, t, som_grid, ny, nx):
    winner = [0,0]
    shortest_distance = np.sqrt(data.shape[1]) # initialise with max distance
    input_data = data[t]
    for row in range(ny):
        for col in range(nx):
            distance = e_distance(som_grid[row][col], input_data)
            if distance < shortest_distance: 
                shortest_distance = distance
                winner = [row,col]
    return winner

```

The learning rate is decreased through each iteration of the training based on the learning rate ```R_l```

```python

# Learning rate decay and neighbourhood range calculation
def decay(step, max_steps,max_learning_rate,max_distance):
    #coefficient = 1.0 - (np.float64(step)/max_steps)
    coefficient = sig_0 * np.exp(-np.float64(step)/max_distance)
    #learning_rate = coefficient*max_learning_rate
    learning_rate = R_l * np.exp(- np.float64(step)/max_learning_rate)
    neighbourhood_range = ceil(coefficient * max_distance) #????
    return learning_rate, neighbourhood_range

```

A random input is selected and weights are adjusted based the vector distances, more specifically, ```euclidean``` and ```manhattan``` distances.

The Manhattan distance (more like "staircase distance"), is the distance between two points calculated as the sum of their **fixed** cartesian $$x,y$$ components. 

```python

for step in range(max_iter):
    if (step+1) % 10 == 0:
        print("Iteration: ", step+1) # print out the current iteration for every 1k
    learning_rate, neighbourhood_range = decay(step, max_iter,R_l,sig_0)

    t = np.random.randint(0,high=norm_x.shape[0]) # random index of training data
    winner = bmu(norm_x, t, weights, ny, nx)
    for row in range(ny):
        for col in range(nx):
            if m_distance([row,col],winner) <= neighbourhood_range:
                weights[row][col] += learning_rate*(norm_x[t]- weights[row][col]) #updating weights of neighborhood nodes

```

### 4. Repeat from step 2 increasing $$s$$ while $$s<\lambda$$









