
# Happy/Sad Classifier

We have built a classifier for happy and sad images using a convolutional neural network, where such a model could be used in emotional detection applications like video games, psychological diagnosis, and employment safety applications .

let's  talk about how the process of building that classifier took place from the data set used till evaluating  the accuracy(and other evaluation metrics) of that classifier.




## Dataset used 
You can [download the dataset](https://drive.google.com/drive/folders/1h9wmnJNrNKNOJXsls11txNx3C2qJblAs) form here, it's 254 RGB images of size 256*256,
then for faster training the following pre-processing is done on data : 

     a)Removing the dodgy images 
     b) Scaling the data by dividing the scale of the images by 255 
        as downscaling helps in better classification 
     c) Dividing the data into batches, each  batch is 32 images

 
   - Spliting dataset 

    a)Training data (70 % of the data set )  
    b) Validation data ( 10% of the  dataset ) 
    c) Testing data (20% of the  dataset )   



## Building CNN Model 

We used the sequential model, as it's the simplest and best model for a single input and single output.   

 - Model layers  
 Three convolutional layers were enough to extract all the important features each associated with a max pooling layer  then we applied a flatten layer directly before the fully connected layer to make it easier for the MP to classify data ,  then finally three FCLs are used for final classification .
- Important hyperparameters  :  
  -For the pooling layer, padding is applied to allow further convolutional operations if needed, and stride(s = 2 )    
  -For the convolutional and fully connected layers, the activation function used is "Relu" except for the final layer, the used activation function is "sigmoid ". 

  -Here thier is no need for a drop out layer as thier is no overfitting .
 - Track the loss and accuracy on the validation dataset to determine the best hyperparameters   
 
## Classifier training  
Keras.fit() is the method used for the model training on the data set for the specified number of fixed epochs or iterations mentioned
 - Epochs here are 20 epochs.    
## Sanity checking 
Even if the validation accuracy is high, it's better to check other evaluation matrices as precision, recall, and binary accuracy.


![Screenshot (157)](https://user-images.githubusercontent.com/71048834/206542080-57933030-e3a5-4ec4-acb0-c3d62bc16c1e.png)

![Screenshot (158)](https://user-images.githubusercontent.com/71048834/206542137-01efbca7-ddae-49b2-b379-14f1dd53540c.png)

## Testing 
Finally, we tested the classifier to check everything makes sense, the testing data also should be scaled to be compatible with  the size of the training data 

 ![Screenshot (162)](https://user-images.githubusercontent.com/71048834/206542201-5d197702-deb6-4af6-ae32-5024e421f069.png)



![Screenshot (164)](https://user-images.githubusercontent.com/71048834/206542218-f4d64747-f63e-4318-ae61-0519d7468df5.png)
