# 311023

## Transfer Learning
It will transfer the weights of one model to another model.

There will be pretrained models and these will have weights that are already calculated. 

Some models like VGG16, VGG19 and ResNet are trained on large datasets. We can simply use the weights obtained from them. 

> Imagenet is a massive image data store.


### The issue. 
If this model is utilized on differnt applications like cancer identification and we gotta use it on flower classification then?

We can still use it as:
- The weights that are obtained from the pre trained model are only applied to the hidden layers. 


### The code

We utilize CIFAR-10 datasets. 60k 32x32 colored images are there in 10 classes. 

We first scale it. 
>Divide it by 255.00 as that is the scale range.

- `include_top = False` gets rid of the fully connected layers(output) from the pretrined models. 

We use our own Fully connected layers.

- `input_shape = (32,32,3)` 3 here is the RGB color channel.

