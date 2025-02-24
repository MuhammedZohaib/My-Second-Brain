# Machine Learning Specialization

### What is Machine Learning?

Field of Study that gives computers the ability to learn without being explicitly programmed. ~ Arthur Samuel

Two main types of machine learning:

- Supervised Learning
- Unsupervised Learning
- Recommenders Systems
- Reinforcement Learning

Supervised Learning:

- Regression
- Classification

Unsupervised Learning:

- Clustering
- Anomaly Detection
- Dimensionality Reduction

# Linear Regression :

```other
It means fitting a straight line through the data. It is the most used alogirthm
in the whole industry.

x = input variables
y = output variable or target variable
m = no. of observations or total no. of rows

In regression model we have a function f which takes an input x and returns us
and output prediction which we call y^ (y-hat)

Simple Linear Regression: f(x) = wx + b

Formula for cost function: Summation of (y^ - y)2
we usually divide it by total number of observations or 2 times the observations
which is a convention.

Cost Function = 1 / 2m Summation (y^ - y)2

we can make a contour plot to get the best value of w,b for linear regression 
model but this is not most efficient way to do. For this we have an algorithm
known as gradient descent which can find the best value of w,b and hence best fit
line.
```

```other
# Gradient Descent
gradient descent is a function that can be used to minimize any function not 
just the cost function. In this algo with start with some initial value
for linear regression we pick w=0 and b=0 then keep changing the w and b until
we are at or near a minimum.

alpha = learning rate
The learning rate here controls how big the step you take in gradient descent.
if learning rate is chosen poorly gradient descent may not work properly.
if learning rate is too small it will work but it will be slow.
if learning rate is too large it might not reach the minimum.

when we are close to reach the local minima the derivative becomes smaller
and so the update steps.

## Implementing Gradient Descent:
w = w - alpha (derivative of cost function w.r.t w)
b = b - alpha (derivative of cost function w.r.t b)

make sure to simultaneously update the values of w and b

tmp_w = w - alpha (derivative of cost function w.r.t w) 
tmp_b = b - alpha (derivative of cost function w.r.t b)
w = tmp_w
b = tmp_b
```

```other
# Multi-Linear Regression
f(x) = w1x1 + w2x2 + w3x3 + w4x4 + xnwn + b
vector w = [w1 + w2 + w3 .... + wn]
vevtor x = [x1 + x2 + x3 .... + xn]
f(x) = vector (w) . vector (x) + b

## Vectorization
- shorter code
- faster code
- use of parallel hardware in background for computation
suppose we have two vector w and x
the non-vector implementation will be

```python
for j in range(0, n):
  f = f + w[j] * x[j]
f = f + b
```

the vector implementation will be as:
```python
f = np.dot(w, x) + b
```
```

```other
# feature Scaling
if we apply operations like gradient descent on large data it might take to a lot
of iterations to find the global minima, to prevent this we apply some 
trasformation on the features such as scaling the data between the range of 0 and
1.

## Techniques
- Divide by the max value
- mean normalization: subtract mean from value and divide by max - min
- z-score normalization: value - mean divide by std
```

```other
# computer cost function

```python
def compute_cost(x, y, w, b):
   m = x.shape[0] 
   total_cost = 0
   cost_sum = 0
   for i in range(m):
       f_wb = (w * x[i]) + b
       cost = (f_wb - y[i]) ** 2
       cost_sum = cost_sum + cost 
   total_cost = (1 / (2 * m)) * cost_sum
   return total_cost
```
```

```other
# compute gradient function

```python
def compute_gradient(x, y, w, b): 
   m = x.shape[0]
   dj_dw = 0
   dj_db = 0

   for i in range(m):  
       f_wb = (w * x[i]) + b
       dj_dw_i = (f_wb - y[i]) * x[i]
       dj_db_i = f_wb - y[i]
       dj_db += dj_db_i
       dj_dw += dj_dw_i
   dj_dw = dj_dw / m
   dj_db = dj_db / m
   return dj_dw, dj_db
```
```

# Logistic Regression :

```other
we cannot use linear regression for classification problem because due to 
outliers the linear regression shifts the best fit line to the right which may
cause wrong predictions of some data.

sigmoid or logistic function:
z =  wx + b
g(z) = 1 / 1 + e ^ -z where 0 < g(z) < 1
f(x) = 1 / 1 + e ^ -(wx + b)

if z is a large negative number the g(z) will become very small and if it's a
large positive number it will become close to 1 and when z = 0 g(z) becomes 0.5
The squared error cost function is not ideal for logistic regression so we will
use another cost function which is:
Loss function (L) = Summation (y^ - y)2
if y = 1 then -log (f(xi))
if y = 0 then -log (1 - f(xi))

simplified loss function = - y(i) log(f(xi)) - (1 - y(i))log(1-f(xi))
where y(i) can either b 0 or 1

cost function becomes = 
- 1 / m summation [y(i) log(f(xi)) + (1 - y(i))log(1-f(xi))]
```

```other
# cost function for logistic regression
```python
def compute_cost_logistic(X, y, w, b):
    m = X.shape[0]
    cost = 0.0
    for i in range(m):
        z_i = np.dot(X[i],w) + b
        f_wb_i = sigmoid(z_i)
        cost +=  -y[i]*np.log(f_wb_i) - (1-y[i])*np.log(1-f_wb_i)
    cost = cost / m
    return cost
```
```

```other
# logistic gradient descent

```python
def compute_gradient_logistic(X, y, w, b): 
    m,n = X.shape
    dj_dw = np.zeros((n,))                           #(n,)
    dj_db = 0.
    for i in range(m):
        f_wb_i = sigmoid(np.dot(X[i],w) + b)          #(n,)(n,)=scalar
        err_i  = f_wb_i  - y[i]                       #scalar
        for j in range(n):
            dj_dw[j] = dj_dw[j] + err_i * X[i,j]      #scalar
        dj_db = dj_db + err_i
    dj_dw = dj_dw/m                                   #(n,)
    dj_db = dj_db/m                                   #scalar
    return dj_db, dj_dw
```
```

```other
# The Problem of Overfitting
To address overfitting we use a technique knows as Regularization

underfit = does not fit the training set well or high bias
overfit = fit the training set extremely well or high variance

## Addressing Overfitting
- collect more training examples
- feature selection (include -  exclude)
- Regularization

## Cost function for Regularization
- penalize all the parameters or weights (lambda / 2m summation w ** 2)
wj = wj - alpha [1/m summation [f(xi) - yi]xi] + lambda / m wj]
```

# Advanced Learning Algorithms :

```other
As we have progressed the amount of data has grown significantly throughout the
years. With tradational learning algorithms like linear regression and logistic
regression even though if we fed a large amount of data they were not able to
take adavantage of all the data points. This led to neural networks where the
amount of data impacts the performance of the trained model.

# Terminologies
- Neuron: a simple function or model or activation function
- Layer: a group of neurons at same level (can also have single neuron)
- Activations: the output of an layer is activation
- Input Layer: Features fed to the neural network
- Hidden Layers: The layers other than input and output layers are hidden layers

The value associated in the superscript means the value belongs to that layer of
the neural network.

The conventional way of counting the layers is to not include the input layer
so if we have 4 layers in a neural network it means the neural network has
3 hidden layers and 1 output layer.
```

### Parameters of w and b of layer L

$$
a_j^{[l]} = g\left( \vec{w}_j^{[l]} \cdot \vec{a}^{[l-1]} + b_j^{[l]} \right)
$$

### Forward Propagation

```python

```

?descriptionFromFileType=function+toLocaleUpperCase()+{+[native+code]+}+File&mimeType=application/octet-stream&fileName=Machine+Learning+Specialization.md&fileType=undefined&fileExtension=md