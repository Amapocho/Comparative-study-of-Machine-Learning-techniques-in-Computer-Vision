# Comparative-study-of-Machine-Learning-techniques

## Supervised ResNet

### Choosing Model

I tried both ResNet as well as a vanilla model and expectedly ResNet gave a better result. The ResNet was framed and trained from scratch without any pretrained weights. Since it used residual layers, it helped reducing overfitting.

![ResNet Model](https://github.com/Amapocho/Comparative-study-of-Machine-Learning-techniques/blob/main/Images/ResNet.png)

|               | Validation Loss | Validation Accuracy |
|---------------|-----------------|---------------------|
| Vanilla Model |      0.9479     |        66.49%       |
| ResNet Model  |      0.8840     |        70.57%       |

### Data Augmentation

Augmenting the data by adding transformations helped reduce overfitting. The transformations
were : <br>
• Random Horizontal Flip <br>
• Random Rotation with a range of 10° <br>
• Colour Jitter – Brightness and Contrast with a range of 0.2, Hue and Saturation with a range of 0.1

Dropout layers also helped boost val_accuracy.

### Choosing Epochs

I trained the model over a range of epochs (from 60 to 150). And for the chosen learning rate the
model gave the best performance at around 90 epochs i.e. high accuracy without overfitting

![Accuracy](https://github.com/Amapocho/Comparative-study-of-Machine-Learning-techniques/blob/main/Images/Accuracy.png)

![Loss](https://github.com/Amapocho/Comparative-study-of-Machine-Learning-techniques/blob/main/Images/Loss.png)

## Semi-Supervised Learning

### Choosing Model

Though ResNet gave a higher test accuracy on while running supervised learning, CNN gave a better final test accuracy when we carried out semisupervised using pseudo labelling. The ResNet model overfit on the dataset extremely fast.


![CNN Model](https://github.com/Amapocho/Comparative-study-of-Machine-Learning-techniques/blob/main/Images/CNN.png)

### Choosing Threshold

I tried multiple threshold’s ranging from 0.7 all the way to 0.96, the best result on the test
accuracy was given by 0.93. This can be justified by the fact that a threshold of 0.93 would
produce pseudo labels on a fairly large number of images from the unlabelled data set while
maintaining a high level of accuracy. (13,925 to be exact)

![Epoch vs Validation Accuracy](https://github.com/Amapocho/Comparative-study-of-Machine-Learning-techniques/blob/main/Images/ValAccuracy.png)

### Choosing Epochs

Rather than choosing the number of epochs manually I decided to utilise the earlyCallback method in .fit() function of Keras. I set the monitor to be val_loss and ended the training if the val_loss stopped decreasing in value.
<br>
• Training the initial supervised classifier -

![Model Accuracy](https://github.com/Amapocho/Comparative-study-of-Machine-Learning-techniques/blob/main/Images/ModelAccuracy.png)

![Model Loss](https://github.com/Amapocho/Comparative-study-of-Machine-Learning-techniques/blob/main/Images/ModelLoss.png)
<br>
• Training the model further on the new dataset -
