---
title: "Insights into Ordinal Embedding Algorithms: A Systematic Evaluation"
authors:
- Leena C Vankadara *
- Siavash Haghiri *
- Faiz Ul Wahab *
- Michael Lohaus *
- Ulrike von Luxburg
date: "2020-10-01T00:00:00Z"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: "2020-10-01T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["3"]

# Publication name and optional abbreviated publication name.
publication: ""
publication_short: "Preprint"

abstract: The objective of ordinal embedding is to find a Euclidean representation of a set of abstract items, using only answers to triplet comparisons of the form ``Is item $i$ closer to the item $j$ or item $k$?''. In recent years, numerous algorithms have been proposed to solve this problem. However, there does not exist a fair and thorough assessment of these embedding methods and therefore several key questions remain unanswered - Which algorithms scale better with increasing sample size or dimension?  Which ones perform better when the embedding dimension is small or few triplet comparisons are available? In our paper, we address these questions and provide the first comprehensive and systematic empirical evaluation of existing algorithms as well as a new neural network approach. In the large triplet regime, we find that simple, relatively unknown, non-convex methods consistently outperform all other algorithms, including elaborate approaches based on neural networks or landmark approaches. This finding can be explained by our insight that many of the non-convex optimization approaches do not suffer from local optima. In the low triplet regime, our neural network approach is either competitive or significantly outperforms all the other methods. Our comprehensive assessment is enabled by our unified library of popular embedding algorithms that leverages GPU resources and allows for fast and accurate embeddings of millions of data points.
# Summary. An optional shortened abstract.
#summary: Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis posuere tellus ac convallis placerat. Proin tincidunt magna sed ex sollicitudin condimentum.

tags:
- deep learning
- unsupervised learning
- Large scale Learning
-
featured: false

links:
url_pdf: AISTATS_Submission.pdf
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
