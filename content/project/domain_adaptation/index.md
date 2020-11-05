---
title: Domain Adaptation
summary:
tags:
- neuralnetworks
- image_classificaton
date: "2017-04-01T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: Domain Adaptation
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

Given only labelled data from the source domain(synthetic data), the goal is to learn features such that they transfer to the target domain(real images), which has no labels. A few ideas in this section are to adversarial train the neural network on both source data and target, with cross-entropy and domain confusion loss.

### Starting References

#### Adversarial Domain Adaptation
1. Domain Adversarial Training for Neural Networks - Ganin, Yaroslav, et al. "Domain-adversarial training of neural networks." The Journal of Machine Learning Research 17.1 (2016): 2096-2030.
2. Features Normalization For Adversarial Domain Adaptation - Roy, Subhankar, et al. "Unsupervised domain adaptation using feature-whitening and consensus loss." Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition. 2019.


#### Image Blending for Domain Adaptation
1. BASNet - Qin, Xuebin, et al. "Basnet: Boundary-aware salient object detection." Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition. 2019.
2. Rendering Realistic Images - Tsai, Yi-Hsuan, et al. "Deep image harmonization." Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition. 2017.
3. Learning to Compose Images - Zhang, Lingzhi, Tarmily Wen, and Jianbo Shi. "Deep image blending." The IEEE Winter Conference on Applications of Computer Vision. 2020.
3. Adversarial Image Generation - Tripathi, Shashank, et al. "Learning to generate synthetic data via compositing." Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition. 2019.

#### Self Training Based Methods
1. Noisy Student - Xie, Qizhe, et al. "Self-training with noisy student improves imagenet classification." Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition. 2020.
2. Pre-training vs Self-Training: Zoph, Barret, et al. "Rethinking pre-training and self-training." arXiv preprint arXiv:2006.06882 (2020).
2. FixMatch with weak and strong augmentations: Sohn, Kihyuk, et al. "Fixmatch: Simplifying semi-supervised learning with consistency and confidence." arXiv preprint arXiv:2001.07685 (2020).
