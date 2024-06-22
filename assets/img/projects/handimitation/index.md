---
title: Hand Imitation
summary: Reinforcement Learning for an Imitating Robotic Arm.
tags:
- Computer Vision
- PyBullet
- Reinforcement Learning
- OpenAI gym
- 3D Modelling
- Robotics
date: "2020-06-06T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: Robotic arm used in the simulation
  focal_point: Smart

links:
- icon: github
  icon_pack: fab
  name: Code and Details
  url: https://www.github.com/hex-plex/Hand-Imitation
- icon: document
  icon_pack: fab
  name: Abstract
  url: https://docs.google.com/document/d/1_qCllQiJLehKjnqM8FxTcfWmQpp4JSpf9QeZYaxmxv0/edit?usp=sharing
url_code: ""
url_pdf: "https://docs.google.com/document/d/1_qCllQiJLehKjnqM8FxTcfWmQpp4JSpf9QeZYaxmxv0/edit?usp=sharing"
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
#slides: example
---
RL-based learning for a robotic arm to imitate a given hand in a image feed
with [handOfJustice](https://github.com/hex-plex/gym-handOfJustice) as our environment

## To Setup
``` console
pip install gym-handOfJustice
```
else
``` console
git clone https://github.com/hex-plex/gym-handOfJustice
cd gym-handOfJustice
pip install -e .
```
## To Train

we used Actor Critic technique to update the a CNN
examples are RL-train.py and RL-Test.py
- In RL-train we have built the Actor and the critic model using tensorflow
- In RL-Test we have used stable-baselines SAC model with LnCnnpolicy policy
- Dataset which we used consisted of 50,000 images that meant content for 50,000 episodes.
	to use the same it could be downloaded from the [drive link](https://drive.google.com/file/d/1YeJecxl8LDR_r3JAWfSbDP4X_klVQfrO/view)<br/>
	----or----<br/>
``` console
wget --no-check-certificate -r 'https://docs.google.com/uc?export=download&id=1YeJecxl8LDR_r3JAWfSbDP4X_klVQfrO' -O dataset.7z
pacman -Sy p7zip-full  
# Or any package manager you like
7z e dataset.7z
```

## Training Metrics
The training was completed( only on ~50% of the dataset ) over a span 36 days. Special thanks to Center for Computing and Information Services, IIT (BHU) varanasi to provide the computational power i.e., the Compute Cluster. It ran for about 20,960 episodes making upto 20 Million steps. the following are the log of all the metrics.

| Actor Loss | Critic Loss | Reward | Cummulative Reward |
|--|--|--|--|
|![Actor_loss](https://github.com/hex-plex/Hand-Imitation/blob/master/log_images/actor_loss.jpg?raw=True)|![Critic_loss](https://github.com/hex-plex/Hand-Imitation/blob/master/log_images/critic_loss.jpg?raw=True)|![Reward](https://github.com/hex-plex/Hand-Imitation/blob/master/log_images/reward.jpg?raw=True)|![Cum_reward](https://github.com/hex-plex/Hand-Imitation/blob/master/log_images/eps_total_reward.jpg?raw=True)|

These results may look decent but we should keep in mind that what i have tried to do is a end to end model for a very complex and really having a few layers after a mobile net is surely not sufficient for learning the forward kinematics of a robotic arm and being able to estimate the pose of the arm in the image.
## Output
These are the best result after training over a limited amount of time

**Note**
we have used clips from different versions of trained model and environment so there is a edit on these clips that in the gym-handOfJustice==0.0.6 a flip in the environment was added to make feel of the robotic hand more mirror like which can be spotted in the gif files

![Output-1](https://github.com/hex-plex/Hand-Imitation/blob/master/normal%26four_diff.gif?raw=true)
![Output-2](https://github.com/hex-plex/Hand-Imitation/blob/master/3Pose.gif?raw=true)

## The End
Thats all from our side

<p align="center"> <img src="https://github.com/hex-plex/Hand-Imitation/blob/master/Thank_You.gif?raw=true" height="50%" width="50%"></img> </p>

## The Team
<table>
 <td align="center">
     <a href="https://github.com/hex-plex">
    <img src="https://avatars0.githubusercontent.com/u/56990337?s=460&v=4" width="100px;" alt=""/><br /><sub><b>Somnath Sendhil Kumar </b></sub></a><br />
    </td>
    <td align="center">
     <a href="https://github.com/numberbee7070">
    <img src="https://avatars3.githubusercontent.com/u/63304283?s=460&v=4" width="100px;" alt=""/><br /><sub><b>Yash Garg</b></sub></a><br />
	</td>
	<td align="center">
     <a href="https://github.com/infini8-13">
    <img src="https://avatars2.githubusercontent.com/u/54203063?s=460&v=4" width="100px;" alt=""/><br /><sub><b>L N Saaswath</b></sub></a><br />
	</td>
	<td align="center">
     <a href="https://github.com/AtuL-KumaR-00">
    <img src="https://avatars3.githubusercontent.com/u/64649440?s=460&v=4" width="100px;" alt=""/><br /><sub><b>Atul Kumar</b></sub></a><br />
	</td>

</table>
