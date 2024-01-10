---
title: Gait-Occlusion-Reconstrution
summary: Reconstruction Gait sequence for gait recognition
tags:
- Computer Vision
date: "2021-03-05T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: Gait occlusion in input sequence
  focal_point: Smart

links:
- icon: github
  icon_pack: fab
  name: Code and Details
  url: https://github.com/hex-plex/Gait-Occlusion-GAN
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
# Gait-Occlusion-GAN

*UnPublished: made public temporally*

Original code for the paper **"BGaitR-Net: Occluded Gait Sequence reconstruction with temporally constrained model for gait recognition"** under Prof. Pratik Chattopadhyay.

This work proposes simple BiDirectional Filtering of the latent vectors of The silhouettes. TimeSeries Data of the latent space is been filter for reconstruction using a simple Bi-LSTM trained with A sophisticated method proposed in the paper.
The Conversion of the Spatio Data to latent space was done using a  conditional Variational AutoEncoder.
We have used a 3 Datasets : for training 2 namely, CASIA-B, OU-ISIR large population, and testing 1 namely, TumIITKGP.

*A conditional GAN based approach is also been presented in code*

## Proposed approach

We have used a Model based approach for feature extraction using **Temporally constrained Kmeans Clustering** and **Short Path in a Weighted Graph** for assigning Keypose for the Sequence even in case of Occlusion. This achieved substantially better results
<p align="center">
<img src="https://raw.githubusercontent.com/hex-plex/Gait-Occlusion-GAN/master/results/pa.png"/>
Propoesed Approach
</p>

<p align="center">
<img src="https://raw.githubusercontent.com/hex-plex/Gait-Occlusion-GAN/master/results/en.png"/>
  Model Architecture
</p>
<p align="center">
<img src="BiLSTM.png"/>
  Model Architecture - 2
</p>

## Results

<p align="center">
<img heigth="300" src="https://raw.githubusercontent.com/hex-plex/Gait-Occlusion-GAN/master/results/7333occlu.jpg"/>
Visual inspection of Reconstruction for a sequence with over 73 occlusion.<br/>
(a) Input Sequence<br/>
(b) Reconstructed Sequence<br/>
(c) Ground Truth<br/>
  
Successfully able to Reconstruct 22 Frames from just 8 Frames with a Dice score 0.98
</p>

<p align="center">
<img src="https://raw.githubusercontent.com/hex-plex/Gait-Occlusion-GAN/master/results/cmc_plot.png"/>
</p>
<p align="center">
  CMC Accuracy of Gait Recognition for TUM-IITKGP Dataset
</p>
