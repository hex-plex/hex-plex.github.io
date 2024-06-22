---
title: "VidModEx: Black Box Model Extraction for Video Classification models with Efficient Query Samples"

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here 
# and it will be replaced with their full name and linked to their profile.
authors:
- admin
- Pavan Kulkarni
- Yuvaraj Govindarajulu
- Manojkumar Pamar


date: "2022-11-14T00:00:00Z"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: "2017-01-01T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["1"]

# Publication name and optional abbreviated publication name.
publication: In *Conference on Computer Vision and Pattern Recognition*
publication_short: In *CVPR 2023*

abstract: Current model extraction attacks have a generator or a synthetic dataset with the objective of maximizing the disagreement between the victim and replica model, in these techniques the generators have very limited success in learning representations for higher dimensional datasets. Another set of algorithms levers a proxy dataset to train a generator to have a similar data distribution, these approaches work only if the dataset is a superset or closely related to the target dataset. Hence making these approaches limited in terms of the domains of the model that can be attacked as well as the higher computational time required for training an additional discriminator. In the current work, we propose a simple generator with the standard objective of maximizing the disagreement between the outputs of the victim and the replica model, with an additional loss for improving visual features of the generated samples using a gram matrix as the objective computed against samples of a hyper class from a proxy dataset which is correlates to the target class of the victim. This assignment of a hyper class is done using Kmeans clustering of the word embedding of the target dataset classes and the proxy dataset classes, this helps in the efficient usage of the proxy dataset while generalizing the approach for different target datasets. In the paper, we show the success of the technique with experiments carried out on the victim model as Movie-Net-A6 (Video Action Classifier) trained and a proxy dataset of Image Net (Image classification) supporting the argument of enhancing the extraction of the model from a cross-modal dataset. We are the first to demonstrate the scalability of the extraction algorithm on Video Classification for datasets with 600 classes. The proposed approach achieves the highest extraction results on video classification models trained on Kinetics-600, Charades, and UCF101 with a reasonable query complexity of 35M, 20M, and 15M respectively. 

# Summary. An optional shortened abstract.

tags: []

# Display this page in the Featured widget?
featured: true

# Custom links (uncomment lines below)
# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: 'https://hex-plex.github.io/publication/vidmodex'
url_code: ''
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: ''
url_video: ''

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
image:
  caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/pLCdAaMFLTE)'
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.


# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
---
