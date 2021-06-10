# Bark Classification

This Classification shows the power of the pretrained models of tensforflow keras. It applies the MobileNet model to classify the 12 bark types in the dataset. 

## Dataset

The used dataset is from https://www.vicos.si/Downloads/TRUNK12 . The TRUNK12[[1]](#1) dataset contains pictures of tree trunks. They can be downloaded as a zip file. Luckily the data is organized in a way so that the function image_dataset_from_directory() from the keras preprocessing package can read it. 

To see how the pictures look alike a visualization is implemented in the code. 

The dataset contains 360 images of 12 bark classes which are more or less equally distributed over the classes. The resolution of the pictures is 3000 x 4000 pixels. 

## Models

To obtain a good impression of the pretrained model, a self-implemented CNN with just a few layers and a chopped off early layer from the MobileNet are measured too. 

| Model | #Layer | #Accuracy |
| ----- | ------ | --------- |
| MobileNet | 95 | 96.8 %|
| Chopped MobileNet | 52 | 43.7 %|
| Self-CNN | 12 | 21.0 %|

It must be added, that the accuracy measured is not the accuracy of the training or validation set. It is the accuracy on an unknown test set. Another important aspect is that some data preprocessing is also added to train the model. For example a data augmentation to add more images to train the models and also a rescaling and preprocessing with the MobileNet preprocessing function. 

After the CNN-Layers for all the models there was also a Sequential Model added with Dropout to handle the output of the features of the CNNs. 

For better understanding I want to motivate you to look up everything in the code. As the Code is a jupyter notebook it is very easy to see the outputs and the results of the models.

## References
<a id="1">[1]</a> 
Computer-vision-based tree trunk recognition, 
Matic Švab, Bsc Thesis, (Mentor: doc. dr. Matej Kristan), 
Fakulteta za računalništvo in informatiko, Univerza v Ljubljani, 2014


