# Flower Classification with TPUs

https://www.kaggle.com/c/flower-classification-with-tpus

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

For switch value less than 0.5 , rotation transformation type of augmentation was used finetuning
EfficientNetB5 having input shape 515*512,adam optimizer with sprase categorical crossentropy loss.
For switch value greater than 0.5,cutmix augmentation was tried out finetuning EfficientnetB5,same input shape and optimizer
configuration.

Nosiy student weights were used.

5 fold cross validation with LR scheduler and early stopping.

Number of epochs :15 

Batch Size:128

The average CV Score (Macro F1 score) : 0.9612 and the model scored 0.95727 in public LB. , 0.96415 in private LB.

### For Version 17 File:
No External data.

Efficient net B5 ,512*512 input shape images , noisy student weights

Batch cutmix augmentation

No of epochs : 18

Batch Size:128 

5 fold Cross validation with LR scheduler and early stopping.

Average Macro F1 score 0.9785

Public LB : 0.95848

Private LB : 0.95687 

