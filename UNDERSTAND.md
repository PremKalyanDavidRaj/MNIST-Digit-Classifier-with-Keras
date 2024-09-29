###Challenge###
1. `MNIST hand-written digits should be white, and the background should be black`.
ans. The default, matplotlib's plt.imshow() function may display MNIST digits using the viridis colormap, which results in digits being shown in various colors. 
     
     plt.imshow(255 - x_train[i], cmap='Greys')

 The traditional representation of MNIST digits as white digits on a black background, you can change the colormap to 'Greys' and invert the image using the expression.

 Reference - I used the IDL website to understand https://www.nv5geospatialsoftware.com/docs/Image_Types.html#:~:text=Pixel%20Values%20in%20Image%20Data&text=The%20original%20data%20type%20of,ranging%20from%200%20to%20255.


2. `Why are they showed here as yellowish with green margins? Why is the background purple?`
ans. The colormap used by plt.imshow() in matplotlib dictates the colors seen in the image, with viridis being common. This colormap maps pixel values to a band of colors, such as purple for low values and yellow for high values. 

 Reference - Git hub copilot
###Question###
1. `Why is the pixel an integer between 0 and 255?`
ans. Each pixel's intensity is commonly represented as an 8-bit byte, providing 256 different values ranging from 0 to 255. 
here 0 represents black and 255 represents is white and Values in between represent various shades of gray.
 
 Reference - I used the Git hub copilot to understand the pixel integer

###Question###

1. `What is the representation of these images in this program? What's the data type of x_train, for example?How can you find out?`
ans. The representation MNST images are a 2D Numpy  in this program of dataset.
     The data type of x_train is usually a numpy array for example The data type of its elements depends on the data loading if the images were loaded in grayscale format the data type typically unasigned 8- bit integer. 
     TO find out the data type of  x_train simply using the python coding below code.
     eg:
     print(type(x_train))
     print(x_train.dtype)
 Reference - I used the The Keras blog to understand neural network
         The Keras blog https://blog.keras.io/building-powerful-image-classification-models-using-very-little-data.html
2. `Why do we need to reshape x_train and x_test?`
ans. The reason to reshape the x_train and x_test in the context of the MNIST dataset  because many machine learning model fully connected to the neural network. each input data in a flat, one-dimensional format.

 Reference - I used the The Keras blog to understand neural network https://blog.keras.io/building-powerful-image-classification-models-using-very-little-data.html

        

###Challenge###

1. `Is there a simpler way in Keras to flatten the input image dataset?`
ans. The simple way in keras to flatten the input image dataset directly in a keras model using the flatten layer.

Here's an example of how to use the Flatten layer in a Keras model:

                 from keras.models import Sequential
                 from keras.layers import Flatten

                 model = Sequential()
                 model.add(Flatten(input_shape=(28, 28)))
in this example flatten layer will transfrom the input images from a 28x28 matrix into a 1D array elements.

 Reference - I used the Git hub copilot to get understanding the layers
kevinMclean in Aug 29,2021 https://kevinmlean.medium.com/how-to-use-keras-layers-flatten-c3f29ed1b686.


###Question###

1. `What's the original datatype of each pixel value? How do know?`
ans. The datatype of each pixel value in a image its depends on the how an image is represented 
for grayscale and color images the datatype is unit8 unsigned 8-bit integer.

example: to check the data type in the given MNSIT Dataset
        print(x_train.dtype)

 Reference: I used the IDL website to understand https://www.nv5geospatialsoftware.com/docs/Image_Types.html#:~:text=Pixel%20Values%20in%20Image%20Data&text=The%20original%20data%20type%20of,ranging%20from%200%20to%20255.

###Question###
Finally, we get to build our neural network. We'll start by instantiating a Keras Sequential model.

1. `Why is this type of model a good choice for our problem?`
Ans The keras sequential model is good for this MNSIT Dataset problem and The Sequential model offers a linear stack of layers, making it intuitive for beginners to understand and use. Layers are added sequentially, simplifying the model-building process, and its capable of constructing various neural network architectures. From basic feed-forward networks to more intricate designs, it adapts well to different tasks and requirements. 

###Challenge###

The statement model.add(Dense(512, input_shape(784,))) does two things.

1. `How can we decompose it into two separate statements? It will improve clarity and readability.`
ans.  To decompose  the two separate statements for clarity and readability, first we need to define the dense layer and second add the model to the layer

for example:
         
         from keras.layers import Dense

         layer = Dense(512, input_shape=(784,))

         model.add(layer)

in this way it will improve the clarity and readability.


2. `What is softmax? Consider the following output array.`

This array represents the class 0.

[ 1, 0, 0, 0, 0, 0, 0, 0, 0, 0 ]

ans. the softmax is a function used in machine learning particularly in the image classfication problems, the array represents the class 0 it is a one-hot encoded representation of the class 0.

Similarly, the following array represents the class 9 its is also the one-hot encoded representation of the class 9:

[ 0, 0, 0, 0, 0, 0, 0, 0, 0, 1 ]

When predicting the class, softmax assigns a probility or likelihood to each of the 10 classes. The class with the greatest probability is the predicted class.

The following example output would predict the class 1:

[ 0, 0.8, 0, 0, 0.05, 0, 0, 0.15, 0, 0 ]

 Reference - I used the  Machine learning blog to understand array https://machinelearningmastery.com/softmax-activation-function-with-python/

###Challenge###
1. `Why the number of parameters for the 1st hidden layer is 401,920?`
ans. The parameters are fully connected to the dense layer of a neural network of the input features and number of neurons in the layer.

the input data is a 784 and the 512 neurons multiply n*m.
eg: 784 * 512 (weights) + 512 (biases) = 401,408 + 512 = 401,920.

2. `Why the numnber of parameters for the 2nd hidden layer is 262,656?`
ans. In second layer the number of parameters in a layer of neural network depends on the number of the neurons in that layer and the number of neurons in the previous layer.

the input layer has n neurons and the 2nd hidden layer has m neurons eaach neurons in the previous layer in second layer has the adding another m more parameters  n*m+m .

eg:  512 * 512 (weights) + 512 (biases) = 262,144 + 512 = 262,656.


3. `Why the number of parameters for the 3rd hidden layer is 5130?`
ans. In Thrid layer the number of parameters of neurons in previous and the current layers and the thrid hidden layer has 10 neurons.

eg: 512*10(weights) +10(biases) = 5120 +10 = 5130

reference: i used the github copilot  to understand the calculations part.

###Challenge###
1. `What does it mean to train the model "per gradient update"?`
ans. In machine learning to train the model "per gradient update" is nothing but updating the models's parameters, The model's parameters are adjusted based on the computed gradients of the loss function. These adjustments, made in the opposite direction of the gradient, aim to minimize the loss and enhance prediction accuracy, This process repeated for each batch of training data, constituting training"per gradient update." 

`### More relevant questions`
1. How do I invert a grayscale image and convert it to a binary image? 
2. Reshapeing the 1D image into a 4D for keras?
3. Is there any alternate versions of softmax?
4. is there any chance to run two different dataset in one model?