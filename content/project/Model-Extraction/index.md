---
title: Black Box Model Extraction
summary: Extraction of Model using Black box queries, from limited or no original data.
tags:
- Model Extraction
- Deep Learning
- Computer Vision
date: "2022-03-03T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: Samples from Kinetics 600 dataset.
  focal_point: Smart

links:
- icon: github
  icon_pack: fab
  name: Code
  url: https://github.com/COPS-IITBHU/Model-Extraction-Attacks-Video-Classification
- icon: open-access
  icon_pack: ai
  name: Slides
  url: https://www.canva.com/design/DAE7snq2f24/B38vm5NbWS2XIt4GrFQLKA/view?utm_content=DAE7snq2f24&utm_campaign=designshare&utm_medium=link&utm_source=publishsharelink#20

url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""
# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
#slides: example
---

Please go through the slides linked above or watch through our presentation below.

<iframe src="https://drive.google.com/file/d/1l75HNPUfXPEQmIOUbBsiiD6kHIoHM8gi/preview?t=2823&end=3080" width="720" height="405" ></iframe>


## End to End Approach

![](https://raw.githubusercontent.com/COPS-IITBHU/Model-Extraction-Attacks-Video-Classification/master/media/end_to_end.png)

## Installation

```bash
$ pip install vidmodex ## Stable version
$ pip install git+https://github.com/hex-plex/Model-Extraction-Attacks-Video-Classification ## Latest development
```

## Usage
Simple snippet explaining the usage :

### BlackBox Extraction
```python
# Black Box Victim: SwinT, Student: ViViT, Generator: Tgan

from vidmodex.models import ViViT as Student
from vidmodex.models import SwinT as Victim
from vidmodex.generator import Tgan as Generator

custom_config = {}
custom_config["num_classes"] = 400

blackbox_main(custom_config)
```
### GreyBox Extraction

```python
# Grey Box Victim: SwinT, Student: ViViT, Generator: Tgan, Dataset: Kinetics 400

from vidmodex.models import ViViT as Student
from vidmodex.models import SwinT as Victim
from vidmodex.generator import Tgan as Generator

custom_config = {}
custom_config["csv_file"] = "ENTER-THE-LOCATION-OF-DATA-CSV"
custom_config["root_dir"] = "ENTER-THE-LOCATION-OF-DATA-ROOT"
custom_config["ucf_gan_weights"] = "ENTER-THE-LOCATION-OF-UCF-WEIGHTS" or "state_normal81000.ckpt"
custom_config["num_classes"] = 400

greybox_main(custom_config)
```


## References

[[1]](#1) **ViViT: A Video Vision Transformer** [https://arxiv.org/abs/2103.15691] [cs.CV] 1 Nov 2021

[[2]](#2) **MoViNets: Mobile Video Networks for Efficient Video Recognition** [https://arxiv.org/abs/2103.11511] [cs.CV] 18 Apr 2021

[[3]](#3) **Swin Transformer: Hierarchical Vision Transformer using Shifted Windows** [https://arxiv.org/abs/2103.14030] [cs.CV] 17 Aug 2021

[[4]](#4) **Temporal Generative Adversarial Nets with Singular Value Clipping** [https://arxiv.org/abs/1611.06624] [cs.LG] 18 Aug 2017

[[5]](#5) **Data-Free Model Extraction** [https://arxiv.org/abs/2011.14779] [cs.LG] 31 Mar 2021

[[6]](#6) **MAZE: Data-Free Model Stealing Attack Using Zeroth-Order Gradient Estimation** [https://arxiv.org/abs/2005.03161] [stat.ML] 6 May 2020

[[7]](#7) **Robustness and Diversity Seeking Data-Free Knowledge Distillation** [https://arxiv.org/abs/2011.03749] [cs.LG] 10 Feb 2021 
