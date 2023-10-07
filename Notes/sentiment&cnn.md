# 071023

## Sentiment Analysis

It is the analysis of sentiments. 
If we have some reviews for a hotel.
```
XYZ Hotel
- It is good
- Expensive
- Staff very bad
- Food good
- Drinks are bad
- Idk
```

Among these we can largely classify them into two types(binary), Good and Bad. But we can have others like Sarcastic, neutral etc.

We'll use **ANN** to analyze sentiments. 

Since we are dealing with words we'll have to use TFIDFVectorizer.

### Steps
- Find useful features and choose them.
- Eliminate missing values
- Encode the data and store them in train and target variables. 
  - `max_features = 5000` means 5000 words of the text message is considered. 
- We will have to flatten the data(SPARSE MATRIX) before passing it into the neural network. That's why we do `X = X.toarray()`
- Then split into train and test. 
- Proceed to create the mode.
  - `keras.Sequential` as we are building hte model sequentially.
  - `keras.layers.Dense(32.....)`, 32 is the number of neurons in the next layer(hidden layer)
  - We do `X_train.shape[1]`-> Results in `(1234,3)`, this selects the number of neurons in the input. 
  - Then we create another hidden layer(dense network) with 64,128, 256 and 512 neurons.
  - The output layer will have only one neuron as we are only in need if the comment is good or not(binary).
- Compile the model.
- We then save the model with `model.save("senti.keras")`. This will allow us to straight up use the model with the trained weights already ready.



## CNN - Classification of handwritten digits using CNN
CNN is largely used for image calssificaiton. It has three parts 
- Convolution
- Pooling/strides
- ANN

### Steps
- We import Conv2D, MaxPoolin2D, Flatten, Dense and a few other things. 
- `x.shape[0],8, 8, 1` -> (number of samples, h, w, channel).
- Then spitting into train and test. 
- The model is created sequentially hence `Sequential()`. 
- Some CNN concepts that went overhead.... `Conv2d(32)` 32 is the number of features. It is helpful in identifying. 
- Then the ANN stage comes. We cannot immediately identify the input to this stage, so the model does this by itself. 
- We stop the model using earlystop and best_weights(skip for now.)
- Then we plot and find the test accuracy etc.