# EDSR
* The EDSR architecture is based on the SRResNet architecture and consists of multiple residual blocks. It uses constant scaling layers instead of batch normalization layers to produce consistent results. Instead of using a L2 loss (mean squared error), the authors employed an L1 loss (mean absolute error), which performs better empirically.
* Original EDSR's scale is 4x. But I used DIV2K 8x scale dataset.

## Comparison with model with three residual blocks
* The residual block design of EDSR differs from that of ResNet. Batch normalization layers have been removed (together with the final ReLU activation): since batch normalization layers normalize the features, they hurt output value range flexibility. It is thus better to remove them. Further, it also helps reduce the amount of GPU RAM required by the model, since the batch normalization layers consume the same amount of memory as the preceding convolutional layers.
![edsr](https://user-images.githubusercontent.com/93169315/171980522-6709b270-9a96-459c-99fe-447d3b41d800.PNG)

## Result
![edsr2](https://user-images.githubusercontent.com/93169315/171980565-82d45d7b-6f3f-4b9d-9df1-f24a213fb43f.PNG)
