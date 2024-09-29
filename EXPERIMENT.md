#### Experimentation

""" Apply the approach used in building this digit classifier to build another classifier.
Use another dataset available through Keras websiteLinks to an external site., such as CIFAR10 dataset.
Try using Matplotlib to create a graph of the training history.
After training, we can visualize models accuracy with Matplotlib. See reference code below:
training_results =fit(x_train, y_train, batch_size=128,  epochs=5, verbose=1, validation_split=2)

plot(training_results.history['accuracy'])
plt.plot(training_results.history['val_accuracy'])
plt.xlabel('Epoch')
plt.ylabel('Accuracy')
plt.legend(['Train', 'Validation'], loc='upper left')
plt.show()

Experiment with 2 hidden layers and 3 different batch sizes
Record findings from your experiment in a new file, md:
How many parameters were adjusted during training?
How long did the training take?
What loss and accuracy did the model produced?"""
 


### `BY using the CIFAR10 dataset i did Small image classfication  using the convolution neural network.`###

1. `How many parameters were adjusted during training?`
ans. 
    1. Flatten Layer (Flatten): Since the Flatten layer does not have any trainable parameters (it simply reshapes the input), there are 0 parameters adjusted.
    2. Dense Layer (dense_7): This layer has 32 output neurons, each connected to all 3072 neurons from the previous Flatten layer. Hence, the total number of parameters for this layer is 3072×32+32=983363072×32+32=98336. 
    3. Dense Layer (dense_9): This final layer has 10 output neurons, each connected to all 32 neurons from the previous layer. Hence, the total number of parameters for this layer is 32×32+32=105632×32+32=1056.
    4.Dense Layer (dense_9): This final layer has 10 output neurons, each connected to all 32 neurons from the previous layer. Hence, the total number of parameters for this layer is 32×10+10=33032×10+10=330. 

    Adding these up, the total number of parameters adjusted during training is: 

    0+98336+1056+330=997220+98336+1056+330=99722 

     So, 99,722 parameters were adjusted during training.  

2. `How long did the training take?`   

ans.  Training took 12.312610864639282 seconds.

3.`What loss and accuracy did the model produced?`
ans. The model produced the following metrics: 

Loss: 1.6816 

Accuracy: 0.3869 

These values indicate that during evaluation on the test dataset, the model lost about 1.6816 and accuracy of about 0.3869. 

Reference: Dataset link https://github.com/codebasics/deep-learning-keras-tf-tutorial/blob/master/16_cnn_cifar10_small_image_classification/cnn_cifar10_dataset.ipynb
 


