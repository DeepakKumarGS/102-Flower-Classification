#Flower Classification with TPUs

The objective of this competition is to build a ML model that identifies the type of flowers in a dataset of images
The model can be trained using TPUs which are powerful hardware acclerators specalized in deep learning tasks.This was
a playground competition organized by website Kaggle to try and test the solutions using TPUs.

Scored 479th position out of 848 participated teams

## Writeup :
### For Version 30 File :
Used Oxford flowers external dataset along with the competition dataset for training the model .
But since the competition does not allow external data for training , I did not select this version for final submission.
### Approach:
I used two augmentation strategies for training the data.The models were selected from a random normal distribution.
The random variable was named as switch. 
For switch value less than 0.5 , rotation transformation type of augmentation was used with 
EfficientNetB5 having input shape 515*512,adam optimizer with sprase categorical crossentropy loss
For switch value greater than 0.5,cutmix augmentation was tried out with EfficientnetB5,same input shape and optimizer
configuration with categorical crossentropy loss. 
5 fold cross validation with early stopping was used.
The average Macro F1 score for all epoch was 0.9612 and the model scored 0.95727 in public LB. , 0.96415 in private LB.
