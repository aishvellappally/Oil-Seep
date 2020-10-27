# Oil-Seep
Exercise to detect oil seeps from SAR images

oil_seep.ipynb file contains the code used to preprocess the dataset, split data, build and train the model and evaluation of the model. The code is written in Python, using Keras for deep learning libraries.

The dataset is accessed through google drive, where it was uploaded. 
Images are divided into train, validation and test sets in the ratio 8:1:1

The model used is Fully Convolutional Neural Networks- FCNN. It is a simple encoder-decoder architecture, which learns more features through convolution as it goes into the encoder, and uses transposed convolution (conv+upsample) to get predictions. This network is used to predict the mask, which can then be compared with ground truth.

Metrics used are IOU Coefficient and Dice Coefficient. 

IOU coefficient - It is the Intersection over Union coefficient that evaluates the overlap ratio between the ground truth and the predicted mask.

IOU = Area of Intersection / Area of Union.

An IOU of 0 means no overlap, that is predicted mask is not at all overlapping with ground truth.IOU of 1 is perfect overlap.

DICE COEFFICIENT - The dice coefficient is like F1 score for image segmentation problem. It shows how many pixelsin the image is predicted correctly at the right location as a ratio of the total number of pixels in both ground truth and predicted image. 

Dice Coefficient = 2* (Area of Overlap / Total Number of Pixels in both images)

The value ranges from 0 to 1, 0 for no overlap and 1 for perfect overlap.

model-fcnn.h5 is the final model saved with best weights obtained on training. It can be loaded and tested using keras.models.load_model

