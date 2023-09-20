# Handwritten_digit_recognition
* This project is for regonizing the digits from the given image
* For this project we have used neural networks on mnist dataset

## Techstack
* numpy
* tensorflow
* keras
* matplotlib
* sklearn

## Dataset:
We have used mnist dataset provided by keras consisting of images have digits ranging from 0-9
you can load the dataset using the following code as:
>(X_train, y_train), (X_test,y_test) = keras.datasets.mnist.load_data()<br/>

To know more about the dataset, refer to the page:(https://keras.io/api/datasets/mnist/)
## Model Building
For building the neural network we have used the multiple layers as:
>model = keras.Sequential([keras.layers.Flatten(input_shape=(784,)),<br/>
>                         keras.layers.Dense(100, activation='relu'),<br/>
>                         keras.layers.Dropout(0.2),<br/>
>                         keras.layers.Dense(50, activation='relu'),<br/>
>                          keras.layers.Dropout(0.2),<br/>
>                         keras.layers.Dense(10, activation='sigmoid')])<br/>

we used 10 neurons in the output layers such that the neurom having the maximum value we be output of the model i.e. 0-9<br/><br/>
For compiling and fitting it to our dataset use the following code as:
>model.compile(optimizer='adam',<br/>
>              loss='sparse_categorical_crossentropy',<br/>
>             metrics=['accuracy'])<br/>
>model.fit(X_train, y_train, epochs = 25, callbacks=[callbacks])<br/>
<br/>
## Testing
For evaluating the model we need to test it on our test data as:
>model.evaluate(X_test, y_test)

our model is giving us an accuracy of 97.85000085830688%<br/><br/>

Finally our model has trained well so its time to save our model :
>path = './finalmodel.h5'<br/>
>model.save(path)<br/>
