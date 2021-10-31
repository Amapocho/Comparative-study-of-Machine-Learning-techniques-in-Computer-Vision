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
were: -
• Random Horizontal Flip
• Random Rotation with a range of 10°
• Colour Jitter – Brightness and Contrast with a range of 0.2, Hue and Saturation with a range of 0.1

Dropout layers also helped boost val_accuracy.
