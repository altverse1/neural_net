# 3rd & 4th Lab Program

## Hyper Parameter Tuning

We use hyperparameter to get 
- The number of hidden layers needed
- The number of neurons in each hidden layer.
- Learning Rate is also a hyperparameter 
- Optimizer is also a hyperparameter. 
- Activation function is also actually a hyperparameter but it can be chosen. 

Using keras hypertuner module we can do hyperparameter tuning.

## Explaination
> Here too we have concepts of random search and grid search.

Keras hyperparameter in the code we use Random Search. 
We make use of sequential model. 

In the `hyper_tune` function we use `param.Int('num_layers', 2,20)` This means minimum of 2 and max of 20 hidden layers. Also in `model.add(layers.Dense(units=param.Int('units_'+str(i),min_value=32, max_value=512, step =32)))` The `min_value=32` means the minimum number of neuron that can be in the hidden layer and `max_value=512` is the maximum. `step=32` means if in the first trial 32 neurons are chosen then in the next its is 32+32 = 64 and then 64+32 =.... and so on till 512.

`'Units_'+str(i)` is just some sort of naming that we do to know which iteration is going on. 

> Regression problems will not have metric as accuracy.

Here we use error as a measure.


## Handwritten Classification

It is an ANN classification. We do a image classification here. Image classificaton doesn't fare well with ANN but we can still try it. 

MNIST data is handwritten data for identifying images of numbers form 0-9. 
- There are three dimensions
- The image is grayscale. Hence we can ignore the third dim.
  - As the third dim is 1.

Usually the image resolution in MNIST is $28\times28\times1$ == $28\times28$.

This data is 2D but the neurons take 1D data. Hence we cannot pass the data directly. A numpy array can be used to convert it into 1D. 

`keras.layers.Dense(10, activation='softmax')`, its 10 here cuz, we are trying to get the classification of numbers from 0-9 at the output layer. 

