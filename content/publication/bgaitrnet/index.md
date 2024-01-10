---
title: "BGaitR-Net: Occluded Gait Sequence reconstruction with temporally constrained model for gait recognition"

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here 
# and it will be replaced with their full name and linked to their profile.
authors:
- admin
- Pratik Chattopadhyay
- Lipo Wang

# Author notes (optional)


date: "2021-07-01T00:00:00Z"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: "2017-01-01T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["2"]

# Publication name and optional abbreviated publication name.
publication: In *Expert Systems*
publication_short: In *Expert Ssystems*

abstract: Recent advancements in computational resources and Deep Learning methodologies has significantly benefited development of intelligent vision-based surveillance applications. Gait recognition in the presence of occlusion is one of the challenging research topics in this area, and to date the solutions proposed by researchers lack in robustness and also dependent of several unrealistic constraints. As a result, these cannot be potentially deployed in real-world scenarios. We improve the state-of-the-art by developing novel deep learning-based algorithms to identify the occluded frames in an input sequence and next reconstruct these occluded frames by exploiting the spatiotemporal information present in the gait sequence. The four-stage pipeline adopted in this work consists of key pose mapping, occlusion detection and reconstruction, and finally gait recognition. While the key pose matching phases is done via a Graph sorting algorithm, occlusion detection is carried out in this work by employing a custom built VGG-16 model. Following this, reconstruction of occluded frames is done by fusing the key pose-specific information along with the temporal information present in the gait sequence using a Bi Directional Long Short Time Memory. This occlusion reconstruction model has been trained using synthetically occluded CASIA-B and OU-ISIR data, and the trained model is termed as Bidirectional Gait Reconstruction Network BGait-R-Net. Our approach produces frames that are temporally consistent with the periodic pattern of a gait cycle, while also preserving the body structure, i.e., silhouette-level features at a high resolution. The Pose Energy Features computed from the reconstructed gait cycle has been used as gait signatures to compare against a large set of gallery subjects. Preprint submitted to Neurocomputing September 27, 2021The effectiveness of our approach has been evaluated on the TUM-IITKGP and the synthetically occluded CASIA-B data sets, and encouraging results have been obtained. Comparative analysis with other popular state-of-the-art methods verify the suitability of our approach for potential application in real-life scenarios.
# Summary. An optional shortened abstract.

tags: []

# Display this page in the Featured widget?
featured: true

# Custom links (uncomment lines below)
# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: ''
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