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
The key questions for image classification deal with selecting an architecture, an appropriate loss function, an optimizer, and how to solve the challenge unbalanced classes. After getting the proof of concept(PoC) right, the next step is to successfully train a model? This note contains a list of hands-on tips that has helped me address problems for a variety of datasets and can we used as a starting point for practitioners.

For selecting an architecture, an easy starting point is to pick up pre-trained image classification. This is quite useful especially when your dataset is small and similar to ImageNet. Just remove the classification layer of the pre-trained CNN and replace it with the number of classes you desire. Any architecture would suffice that performs really well on ImageNet. The most popularly available pre-trained models are DenseNets<sup>[1]</sup>, EfficientNets<sup>[2]</sup>, InceptionV3<sup>[3]</sup>, and ResNets<sup>[4]</sup> and they are available for PyTorch, Tensorflow, Keras and mx-net. If you would like to train a model that works on smartphone, using MobileNets<sup>[16]</sup> would be desirable due to computational constraints.

The next step is to pick a loss function and the appropriate optimizer. Categorical Cross-Entropy is the objective function of choice. In addtion, using label smoothing<sup>[3]</sup> and temperature scaling<sup>[12]</sup> with cross-entropy helps as this leads to smooth softmax distribution. This helps to prevent the logit corresponding to the ground truth label to become very large early in the training, thus preventing overfitting.

The standard optimizer used is Adam<sup>[5]</sup> with default parameters. Some experiments have shown that cyclic learning rates<sup>[8]</sup> with Stochastic Gradient Descent(SGD) leads to faster convergence. A combination of SGD with stochastic weighted averaging(SWA) and cyclic learning rates<sup>[7]</sup> leads to better models. The cyclic policy learns a diverse set of models and the averaging of weights of every snapshot model in SWA acts as training an ensemble of neural networks for image classification.

In terms of preprocessing pipelines, based on classical image processing, AugMix<sup>[10]</sup> is more general and encompasses all the other augmentation techniques like blur, noise, and cut. But if needed, an augmentation policy can be learned to preprocess images such that it leads to the best performing model. A shorter route would be to use the same policy that is learned for ImageNet classification like AutoAugment<sup>[9]</sup>.

To address unbalanced classes, it is important to do oversampling of under-represented classes and undersampling of over-represented classes. An alternate option to avoid sampling would is to use class weights and use focal loss for classification<sup>[13]</sup>.

<strong>Note</strong>: A nice experimental study on a few practical tricks for image classification is TrickNets<sup>[12]</sup>. If you would like to train keeping resource constraints in mind, a linear scheduling policy that decay to zero at the last iteration works really well, as pointed in Budget Training<sup>[15]</sup>. Therefore its worthwhile to train for 30-40 epochs with a linear learning rate decay.

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
12. Tricks for Classification - He, Tong, et al. "Bag of tricks for image classification with convolutional neural networks." Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition. 2019.
13. Focal Loss for Unbalanced Classes - Lin, Tsung-Yi, et al. "Focal loss for dense object detection." Proceedings of the IEEE international conference on computer vision. 2017.
14. Heavy Tailed Training Distributions of Classes - Liu, Ziwei, et al. "Large-scale long-tailed recognition in an open world." Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition. 2019.
15. Budget Training - Li, Mengtian, Ersin Yumer, and Deva Ramanan. "Budgeted Training: Rethinking Deep Neural Network Training Under Resource Constraints." International Conference on Learning Representations. 2019.
16. MobileNets - Sandler, Mark, et al. "Mobilenetv2: Inverted residuals and linear bottlenecks." Proceedings of the IEEE conference on computer vision and pattern recognition. 2018.
