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
  caption: Deep Metric Learning
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

Deep metric learning(DML) aims to find an feature embedding space for the images such that images of the same category are closer to each other than images of any other category. As a standard practice in DML, the distance metric used is Euclidean distance and the training pipeline used is to pick N classes and K examples from each the dataset and then mine informative triplets from the minibatch itself. A loss such as triplet loss is used to optimize over the feature space.


### Starting References
#### Architectures
1. DenseNets - Huang, Gao, et al. "Densely connected convolutional networks." Proceedings of the IEEE conference on computer vision and pattern recognition. 2017.
2. InceptionV3 - Szegedy, Christian, et al. "Rethinking the inception architecture for computer vision." Proceedings of the IEEE conference on computer vision and pattern recognition. 2016.

#### Optimization
1. Adam - Kingma, Diederik P., and Jimmy Ba. "Adam: A method for stochastic optimization." arXiv preprint arXiv:1412.6980 (2014).
2. Stochatic Weighted Average - Izmailov, Pavel, et al. "Averaging weights leads to wider optima and better generalization." 34th Conference on Uncertainty in Artificial Intelligence 2018, UAI 2018. Association For Uncertainty in Artificial Intelligence (AUAI), 2018.
3. Cyclic Learning Rates - Smith, Leslie N. "Cyclical learning rates for training neural networks." 2017 IEEE Winter Conference on Applications of Computer Vision (WACV). IEEE, 2017.

#### Feature Augmentation
1. Batch Feature Erasing - Dai, Zuozhuo, et al. "Batch DropBlock network for person re-identification and beyond." Proceedings of the IEEE International Conference on Computer Vision. 2019.
2. HORDE - Jacob, Pierre, et al. "Metric learning with horde: High-order regularizer for deep embeddings." Proceedings of the IEEE International Conference on Computer Vision. 2019.
3. Combination of Global Descriptors - Jun, HeeJae, et al. "Combination of multiple global descriptors for image retrieval." arXiv preprint arXiv:1903.10663 (2019).
4. Dividing and Conquer - Sanakoyeu, Artsiom, et al. "Divide and conquer the embedding space for metric learning." Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition. 2019

#### Basic Loss Functions for Metric Learning
1. Batch Triplet Loss - Hermans, Alexander, Lucas Beyer, and Bastian Leibe. "In defense of the triplet loss for person re-identification." arXiv preprint arXiv:1703.07737 (2017).
2. MultiSimilarity Loss - Wang, Xun, et al. "Multi-similarity loss with general pair weighting for deep metric learning." Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition. 2019.
3. Group Loss - Elezi, Ismail, et al. "The Group Loss for Deep Metric Learning." arXiv preprint arXiv:1912.00385 (2019).

#### Evaluation Metrics
- Evaluation Benchmark Reality Check - Musgrave, Kevin, Serge Belongie, and Ser-Nam Lim. "A metric learning reality check." arXiv preprint arXiv:2003.08505 (2020).

#### Libraries
- Pytorch Metric Learning:https://github.com/KevinMusgrave/pytorch-metric-learning
