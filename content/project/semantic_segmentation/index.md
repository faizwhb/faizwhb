---
title: End to End Semantic Segmentation
summary:
tags:
- neural networks
- pixel-wise prediction
- structure prediction
date: "2017-04-01T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: End to End Semantic Segmentation
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
How can we train an end-to-end model for semantic segmentation? What is the role of architecture and how can we improve to get high resolution prediction maps? How can we deal with resource constraint environments? How can we improve the predictions of the edge pixels?

#### Standard Architectures
1. Pyramid Scene Parsing Networks - Zhao, Hengshuang, et al. "Pyramid scene parsing network." Proceedings of the IEEE conference on computer vision and pattern recognition. 2017.
2. Atrous Convolutions - Chen, Liang-Chieh, et al. "Encoder-decoder with atrous separable convolution for semantic image segmentation." Proceedings of the European conference on computer vision (ECCV). 2018.

#### Real Time Models
1. ICNet - Zhao, Hengshuang, et al. "Icnet for real-time semantic segmentation on high-resolution images." Proceedings of the European Conference on Computer Vision (ECCV). 2018.
2. ENet - Paszke, Adam, et al. "Enet: A deep neural network architecture for real-time semantic segmentation." arXiv preprint arXiv:1606.02147 (2016).

#### Optimization
- Adam - Kingma, Diederik P., and Jimmy Ba. "Adam: A method for stochastic optimization." arXiv preprint arXiv:1412.6980 (2014).

#### Robustness
- Robustness to Corruptions in Images: Kamann, Christoph, and Carsten Rother. "Benchmarking the Robustness of Semantic Segmentation Models with Respect to Common Corruptions." International Journal of Computer Vision (2020): 1-22.

#### Tricks for Training
- Focal Loss for Unbalanced Classes - Lin, Tsung-Yi, et al. "Focal loss for dense object detection." Proceedings of the IEEE international conference on computer vision. 2017.
- Boundary Refinement by SegFix - Yuan, Yuhui, et al. "Segfix: Model-agnostic boundary refinement for segmentation." European Conference on Computer Vision. Springer, Cham, 2020.

#### Incorporating Class Information for Segmentation
1. Object Contextual Representations - Yuan, Yuhui, Xilin Chen, and Jingdong Wang. "Object-Contextual Representations for Semantic Segmentation." arXiv preprint arXiv:1909.11065 (2019).
