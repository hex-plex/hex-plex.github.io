---
layout: page
title: KiloBot MultiAgent Reinforcement Learning
description: Deep MultiAgent Reinforcement Learning on "KiloBot" by Havard University
tags:
- Reinforcement Learning
- MultiAgent Systems
- Deep Learning
- OpenAI gym
- PyGame
- Robotics
date: "2020-09-03T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""
img: assets/img/projects/kilobot/featured.jpg
image:
  caption: KiloBot Platform by Havard University
  focal_point: Smart

links:
- icon: github
  icon_pack: fab
  name: Code and Details
  url: https://github.com/hex-plex/KiloBot-MultiAgent-RL
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
This is an experimentation to learn about Swarm Robotics with help of MultiAgent Reinforcement learning. We have used KiloBot as a platform as these are very simple in the actions space and have very high degree of symmetry. The Main inspiration of this project is this paper[[1]](#1)

## Setting Up
``` bash
git clone https://github.com/hex-plex/KiloBot-MultiAgent-RL
cd KiloBot-MultiAgent-RL
pip install --upgrade absl-python \
                      tensorflow \
                      gym \
                      opencv-python \
                      tensorflow_probability \
                      keras \
                      pygame
pip install -e gym-kiloBot
```
This should fetch and install the basics packages needed and should install the environment
### Sample of environment
These envs are running on a constant **Dummy-actions!!**

|**Env with Graph Objective**|Env with Localization Objective|
|--|--|
|![Output-1](https://github.com/hex-plex/KiloBot-MultiAgent-RL/blob/master/images/env_test_graph_compress.gif?raw=true)|![Output-2](https://github.com/hex-plex/KiloBot-MultiAgent-RL/blob/master/images/env_test_localize_compress.gif?raw=true)|

## Usage
``` bash
python env-test.py ## This will help you check the functionality of the environement and should give the sample code to understand the apis as well.
python model-train.py \
        --headless=True \             ## for headless training default False
        --objective="localization" \  ## defines the objective default is graph
        --modules=10 \                ## This defines the no of modules to be initialized default 10
        --time_steps=100000 \         ## This is the total no of steps the agent will take while learning
        --histRange=10 \              ## This is the no of mu values for the histograms
        --logdir="logs" \             ## This specifies the log location for TensorBoard
        --checkpoints="checkpoints"   ## This is for defining the location where the model is to be saved
        --load_checkpoint="checkpoints/iter-500" ## This loads the specified iteration

python play-model.py \ ## This should load trained weights and show the performance
        --load_checkpoint="checkpoints/graphs/10" \ ## loads this model
        --modules=10  \                             ## no of modules in the env
        --objective="localization" \                ## Sets the objective function
        --time_steps=10000 \                        ## No of iterations to be run
        --histRange=10                              ## Same def as above
```
## Results
After a exhaustive amount of training on varies combinations of no_of_modules and task in hand I have obtained results of the following algorithm for these parameters.
I have used ``` [5, 10, 15, 20, 25, 50] ``` number of modules to carryout the tests.

One may find the Tensorboard log files here:

[ log_kilobot [Drive Link] (403MB)](https://drive.google.com/file/d/11NtimYoXOBGopIxziAojti0k1kfbaVBQ/view?usp=sharing)

and the Model Weights for each parameters here:

[ checkpoint_kilobot [Drive Link] (63.3MB)](https://drive.google.com/file/d/12qpbPIOrC-hLGVn2a8GETrkNL89bt8Dt/view?usp=sharing)
### Graph Problem
The below table is based on the number of modules used but for result tabulation I am considering
``` [5, 10, 20, 50] ```
number of modules. To infer many insights of the algorithm in hand.

<p align="center"><b>Please click on the image to zoom in</b></p>

|Model Trained on **\\** Model Run on|10|20|50|
|--|--|--|--|
|10| ![Success1](https://github.com/hex-plex/KiloBot-MultiAgent-RL/blob/master/images/10trainon10.gif?raw=true)|![Success2](https://github.com/hex-plex/KiloBot-MultiAgent-RL/blob/master/images/10trainon20.gif?raw=true)| ![Success3](https://github.com/hex-plex/KiloBot-MultiAgent-RL/blob/master/images/10trainon50.gif?raw=true) |
|20| - | ![Random1](https://github.com/hex-plex/KiloBot-MultiAgent-RL/blob/master/images/20trainon20.gif?raw=true) | - |
|50| - | - | ![Random2](https://github.com/hex-plex/KiloBot-MultiAgent-RL/blob/master/images/50trainon50.gif?raw=true) |

<hr>
The policies trained on 20 and 50 module system is completely random in sense it just goes forward.

We can see clearly the policy trained with 10 modules have yield a very good amount of coordination between each other that is the critic model taking in the input image of the system is able to specify the bots and guide them, Hence a very good amount of generalization is found when we use this model with system with different number of modules as can be seen with the 20 module system but the non stationarity of a higher order system makes it complex for the critic to reward or give baseline to the actor, As the
- The order of the reward changes drastically.
- The Reading from the histogram becomes Muddy.
- The correlation of a reward to action of a single agent reduces drastically.

<hr>

Hence the Model trained with 10 modules is not able to generalize to the 50 module system, **BUT** It looks more promising than the policy trained for the 50 module system itself, hence a curiculum learning based approach seems promising to solve such a transfer learning problem.

#### Plots for Training with 10 modules

|Actor Loss| Critic Loss | Reward|
|--|--|--|
|![Actor Loss](https://github.com/hex-plex/KiloBot-MultiAgent-RL/blob/master/images/actor10.jpg?raw=true)|![Critic Loss](https://github.com/hex-plex/KiloBot-MultiAgent-RL/blob/master/images/critic10.jpg?raw=true)|![Reward](https://github.com/hex-plex/KiloBot-MultiAgent-RL/blob/master/images/reward10.jpg?raw=true)|

<hr>

#### For 5 modules
The system can't comphensate for the negetive reward got by using fuel as the reward got for graphing is much smaller in order than it that it chooses to be stagnent.
![Failed](https://github.com/hex-plex/KiloBot-MultiAgent-RL/blob/master/images/5trainon5.gif?raw=true)

<hr>

### Localization Problem
Here the task was much easier but the training didnt yield any satisfactory result as.
- there were a lot of non stationarities and the fact the system was modelled based on a fashion which couldn't extend more than a small system of at best 10 modules <a href="1">[1]</a>.
- And the fact that the reward of localization couldnt exceed the negetive reward for moving the bot that is the bots choose to stand still to save fuel over exploring in most of the senarios.

Below are few runs with ```[10, 25]```
Number of modules.

|Localization trained for small n(=10)| Localization trained for big n(=25)|
|--|--|
| ![loc10](https://github.com/hex-plex/KiloBot-MultiAgent-RL/blob/master/images/15loc15.gif?raw=True) | ![loc25](https://github.com/hex-plex/KiloBot-MultiAgent-RL/blob/master/images/25loc25.gif?raw=True) |

Here it is clearly visible that because of randomness and the fact more number of can cover a larger space of the system exploration is much easier than being greedy to stay at a point and save fuel.

## Acknowledgment
To Center for Computing and Information Services, IIT (BHU) varanasi to provide the computational power, i.e., The Super Computer on which I was able to train for over **10 Million Timesteps** for about 1.5 months.

For any other query feel free to reachout.
## References
<a id="1">[1]</a>
**Guided Deep Reinforcement Learning for Swarm Systems** [[arXiv:1709.06011v1]](https://arxiv.org/abs/1709.06011) [cs.MA] 18 Sep 2017
