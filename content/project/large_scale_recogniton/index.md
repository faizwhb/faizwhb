---
title: Large Scale Visual Recognition
summary:
tags:
- neuralnetworks
- image_classificaton
date: "2017-04-01"

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

{{< rawhtml >}}
<div style="text-align: justify">

The idea to develop novel algorithms that can efficiently train neural networks on a large amounts of data. The keys questions of concern are how to select an architecture, how to choose an appropriate loss function, an optimizer, what kind of tricks are useful for successful training of neural networks for image classification.

</div>
 {{< /rawhtml >}}

### Starting References
#### Architectures
1. DenseNets - Huang, Gao, et al. "Densely connected convolutional networks." Proceedings of the IEEE conference on computer vision and pattern recognition. 2017.
2. InceptionV3 - Szegedy, Christian, et al. "Rethinking the inception architecture for computer vision." Proceedings of the IEEE conference on computer vision and pattern recognition. 2016.

#### Optimization
1. Adam - Kingma, Diederik P., and Jimmy Ba. "Adam: A method for stochastic optimization." arXiv preprint arXiv:1412.6980 (2014).
2. Stochatic Weighted Average - Izmailov, Pavel, et al. "Averaging weights leads to wider optima and better generalization." 34th Conference on Uncertainty in Artificial Intelligence 2018, UAI 2018. Association For Uncertainty in Artificial Intelligence (AUAI), 2018.
3. Smith, Leslie N. "Cyclical learning rates for training neural networks." 2017 IEEE Winter Conference on Applications of Computer Vision (WACV). IEEE, 2017.

#### Tricks for Training
1. General Implementation Tricks - He, Tong, et al. "Bag of tricks for image classification with convolutional neural networks." Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition. 2019.
2. Budget Training - Li, Mengtian, Ersin Yumer, and Deva Ramanan. "Budgeted Training: Rethinking Deep Neural Network Training Under Resource Constraints." International Conference on Learning Representations. 2019.
