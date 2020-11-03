---
title: "Large scale ordinal embedding: training neural networks with structure-free inputs"
authors:
- Leena C Vankadara *
- Siavash Haghiri *
- Faiz Ul Wahab
- Ulrike von Luxburg
date: "2019-09-01T00:00:00Z"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: "2019-09-01T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["3"]

# Publication name and optional abbreviated publication name.
publication: ""
publication_short: "A pre-print"

abstract: In this paper, we discuss the fundamental problem of representation learning when no explicit representation of the input items (for example, RGB images) is accessible. All we are provided with are the answers to triplet comparisons of the following form - Is item A closer to item B than to item C? Existing approaches to this problem, which is also called ordinal embedding, are painfully slow and cannot embed more than an order of 1000 items in a reasonable amount of time. We use a feedforward network architecture as a basis of an ordinal embedding method that works on any given set of triplet comparisons. Our algorithm is significantly faster than the existing state of the art approaches and to date is the only approach that can scale to large real-world datasets. Our paper also features a somewhat unconventional way to use neural networks in a discrete setup - we do not use any input representation beyond the index of the item, yet achieve compelling results.
# Summary. An optional shortened abstract.
#summary: Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis posuere tellus ac convallis placerat. Proin tincidunt magna sed ex sollicitudin condimentum.

tags:
- deep learning
- unsupervised learning
- Large scale Learning
-
featured: false

links:
url_pdf: https://arxiv.org/abs/1912.01666
#url_project: ''

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
image:
  caption: 'Reconstructing 2D datasets using triplets'
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects:
- internal-project

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
#slides: example
---
