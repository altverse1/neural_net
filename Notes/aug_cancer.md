# 171023

## Data Aug.
CNN requires more data for training purpose. <br>
Data in datasets like MNIST can have different representations for different numbers. 

Data aug. is synthetic generation of image(4 real instances can generate like 100 synthetic). Helps in aug. It can turn the image in different angles. However synthetic images arent always great can lead to overfitting.

### Steps 
- `tensorflow.keras.preprocessing.image` is where it is imported from.
- We scale the data because ``
- We expand dimension because `-1` specifies an extra dimension as CNN model requires 4 dimensions. 
- The validation data is useful to come to know when the training is to be stopped.
  - If there are no changes to the weights in the 10th epoch why to let the model go higher?
- Here comes the generator. Used for aug. is a part of preprocessing. 
```python
datagen = ImageDataGenerator(
    rotation_range = 10,
    zoom_range = 0.1,
    width_shift_range = 0.1,
    height_shift_range=0.1.
    shear_range = 0.1, #Shearing is like making a square a not square thing(rhombus)
    horizontal_flip = False,
    vertical_flip = False,
)
```
- Utilize Conv2D for CNN. 
- In the first later of CNN we are utilizing AF relu or leakyrelu.
- Padding is also something.
- Flattening is needed as ANN requires 1D.
- We utilize `softmax` as it's a multiclassification problem.
- Then compile. 
- While fitting we do something with datagen.


## Cancer Dataset

### Steps
- Load the data
- Scale it 
- Define the model
  - The image is colored. That's why we got `(32,32,3)`
  - This time more Convolution layers
  - We got an hidden layer
- Compile it
- Train it