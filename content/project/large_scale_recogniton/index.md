---
title: Large Scale Visual Recognition
summary:
tags:
- neuralnetworks
- image_classificaton
date: "2017-04-01T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: Image Classification
  focal_point: Smart

links:
#- icon: twitter
#  icon_pack: fab
#  name: Follow
#  url: https://twitter.com/georgecushen
url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
# slides: example
---
#### [_To be updated_]
Our goal is to train a neural network for image classification.The key questions deal with selecting an architecture, an appropriate loss function, an optimizer, and dealing with unbalanced classes. After getting the proof of concept(PoC) right, the next step is that given so many parameters, how can we efficiently and successfully train a model? Are there any practical tips and tricks to take advantage of? This note contains a list of tips and tricks that has helped me address problems in practice for a variety of datasets and can we used as a starting point for practitioners.

For selecting an architecture, an easy starting point is to pick up pre-trained image classification and remove the last fully connected layer of the CNN. Any architecture would suffice that performs really well on ImageNet. The three most popularly available pre-trained models are DenseNets[1], EfficientNets[2], InceptionV3[3], and ResNets[4] and they are available for PyTorch, Tensorflow, Keras and mx-net. If you would like to train a model that works on smartphone, a suggestion is to use MobileNets[16]

The next step is to pick a loss function and the appropriate optimizer. Categorical Cross-Entropy in practice works really well along with label smoothing and temperature[3]. Using cross-entropy with with label smoothing and temperature helps to prevent the logit corresponding to the ground truth label to become very large early in the training, thus preventing overfitting.

The standard optimizer used is Adam[5] with default parameters, but there is some evidence that cyclic learning rates[8] leads to faster convergence, which stochastic weighted averaging(SWA) with cyclic learning rates[7] leads to better models. The cyclic policy learns a diverse set of models and the averaging of weights for every snapshot model in SWA acts as training an ensemble of neural networks.

In terms of preprocessing piplines, which deals with feeding image data into the network, based on classical image processing, AugMix[10] is more general and encompasses all the other augmentation techniques. But if needed, an augmentation policy can be learned to preprocess images such that it leads to the best performing model. One example would be to use the same policy that was learned for ImageNet classification like AutoAugment[9].

To address unbalanced classes, it is important to do oversampling of under-represented classes and undersampling of over-represented classes. Likewise an alternate option to avoid sampling would is to use class weights and use focal loss for classification[13].

Notes: A nice experimental study on a few practical tricks for image classification is TrickNets[12]. If you would like to training keeping resource constraints in mind, a linear scheduling policy that zero at the last iteration works really well, as pointed in Budget Training[15].

### Important References
#### Architectures
1. DenseNets - Huang, Gao, et al. "Densely connected convolutional networks." Proceedings of the IEEE conference on computer vision and pattern recognition. 2017.
2. EfficientNets - Tan, Mingxing, and Quoc Le. "EfficientNet: Rethinking Model Scaling for Convolutional Neural Networks." International Conference on Machine Learning. 2019.
3. InceptionV3 - Szegedy, Christian, et al. "Rethinking the inception architecture for computer vision." Proceedings of the IEEE conference on computer vision and pattern recognition. 2016.
4. ResNets - He, Kaiming, et al. "Deep residual learning for image recognition." Proceedings of the IEEE conference on computer vision and pattern recognition. 2016.

#### Optimization
5. Adam - Kingma, Diederik P., and Jimmy Ba. "Adam: A method for stochastic optimization." arXiv preprint arXiv:1412.6980 (2014).
6. Batch Normalization - Ioffe, Sergey, and Christian Szegedy. "Batch Normalization: Accelerating Deep Network Training by Reducing Internal Covariate Shift." International Conference on Machine Learning. 2015.
7. Stochatic Weighted Average - Izmailov, Pavel, et al. "Averaging weights leads to wider optima and better generalization." 34th Conference on Uncertainty in Artificial Intelligence 2018, UAI 2018. Association For Uncertainty in Artificial Intelligence (AUAI), 2018.
8. Cyclic Learning Rates - Smith, Leslie N. "Cyclical learning rates for training neural networks." 2017 IEEE Winter Conference on Applications of Computer Vision (WACV). IEEE, 2017.

#### Augmentation
9. AutoAugment - Cubuk, Ekin D., et al. "Autoaugment: Learning augmentation policies from data." arXiv preprint arXiv:1805.09501 (2018).
10. AugMix/MixUp/CutMix/CutOut - Hendrycks, Dan, et al. "AugMix: A Simple Data Processing Method to Improve Robustness and Uncertainty." International Conference on Learning Representations. 2019.
11. imgaug - https://github.com/aleju/imgaug


#### Tricks for Training
12. Implementation Tricks for Classification - He, Tong, et al. "Bag of tricks for image classification with convolutional neural networks." Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition. 2019.
13. Focal Loss for Unbalanced Classes - Lin, Tsung-Yi, et al. "Focal loss for dense object detection." Proceedings of the IEEE international conference on computer vision. 2017.
14. Heavy Tailed Training Distributions of Classes - Liu, Ziwei, et al. "Large-scale long-tailed recognition in an open world." Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition. 2019.
15. Budget Training - Li, Mengtian, Ersin Yumer, and Deva Ramanan. "Budgeted Training: Rethinking Deep Neural Network Training Under Resource Constraints." International Conference on Learning Representations. 2019.
16. MobileNets - Sandler, Mark, et al. "Mobilenetv2: Inverted residuals and linear bottlenecks." Proceedings of the IEEE conference on computer vision and pattern recognition. 2018.
