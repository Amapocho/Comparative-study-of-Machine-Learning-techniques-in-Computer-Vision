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
