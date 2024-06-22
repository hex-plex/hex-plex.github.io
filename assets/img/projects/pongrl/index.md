---
title: Pong Reinforcement Learning
summary: Implementation of Policy Gradient on self made Pong game.
tags:
- Computer Vision
- PyGame
- Reinforcement Learning
- Video Game
date: "2020-05-06T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: Pong game demo written with pygame
  focal_point: Smart

links:
- icon: github
  icon_pack: fab
  name: Code and Details
  url: https://github.com/hex-plex/Pong-ReinforcementLearning
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
I have tried baking a rudimentary RL environment and a agent recipe to learn more about the eco-system.<br/>
I have made [pong.py](https://github.com/hex-plex/Pong-ReinforcementLearning/blob/master/pong.py) a environment which one can host either locally (localhost) or on  0.0.0.0 (LAN).Allowing to communicate to [mainmodel.py](https://github.com/hex-plex/Pong-ReinforcementLearning/blob/master/mainmodel.py) which has to be connected to the same host and the same port. <br/>
I have used a simple socket connection to transfer data rather than a flask/django backend as they are based on it giving a advantage of speed of communication. <br/>
both the scripts have debug mode which allows one to see in which state or stage they are in. <br/>
## Output
![pong-agent](https://github.com/hex-plex/Pong-ReinforcementLearning/raw/master/trained.gif)
<hr/>
The one on the left is a RL agent trained for 3 days and the one on right is a hardcoded AI. This is noticible the they nearly have the same level of skills.

## Requirements
This requires only few basic libraries it only runs on python3, rather a small update can make it compatible with python2.
The libraries
```bash
pickle
numpy
cv2
pygame
# Below are mostly available preinstalled in any python distribution
socket
BytesIO # from io in python3 or directly in python2
_thread # for python 3 and thread in python2
```
Which are quite rudimentary and neccessary part of the code.

## Multithreading
Here I have use many threads to assure that no data is missed while any other calculation or process is running on the main thread as there might be some unwanted lag between inputs.Also another thread on mainmodel exists which take inputs  from the user for pausing and resuming its learning session
## Sockets
I have used sockets to send data between scripts rather than using a instance of model and the pong env on the same script well that would work just fine (or better removing all the lag of communication) , but my goal was to make it more appealing and to make me learn more real life skills that is if I train a agent with raspberry pi ( or any other weaker mobile device for that matter ) as a part of the environment or in the environment a more viable option than running both simulation and the RL agent would be to do the computation and send in actions to it. This also gave me a good understanding about data compression and network security ,though here there is none used as it just accepts the first connection to the env. <br/>
<br/>
with the use of socket one could manually control the environment with keyboard and also have a RL agent learning (half - Duplex).  

## Demo
To launch the env with mostly default values just running [pong.py](https://github.com/hex-plex/Pong-ReinforcementLearning/blob/master/pong.py) directly would start the server with default configs.
Its always recommended to use its instance, apply your configuration you want it to run and start the server.
```python
from pong import Pong

env = Pong( levelodiff=1, ## This is the level of the inbuilt AI that plays against you.
                          ## Set it to 4 and chill out (really try it!!) the scale is 1-3
            debug=False,  ## If set to True it will print the stage the environment is in and info the data inputs and outputs
            render=False, ## It would render the image that is sent to the model, This slows down the process so not a good idea to use it.
            server=True,  ## This is to set server mode on , if set false the environment will be no different from ordinary pong game.
            host="",      ## This is to specify where you want to host it, "" maps to local host "0.0.0.0" doesnt really map
                          ## to your ip address yet
            port=12345    ## This your port no. of the connection.
          )               ## This is to just initiate the environment

env.start()## This starts the env ie., hosts itself as per the given parameter and waits for a connection in async while continuing the game
```

To launch the RL agent running the [mainmodel.py](https://github.com/hex-plex/Pong-ReinforcementLearning/blob/master/mainmodel.py) directly will run it in default config. <br/>
To customize to your config import and create an instance and run the client. <br/>
```python
from mainmodel import PolicyGradient

## This uses two hidden layer to out-put 2 probabilities
agent = PolicyGradient( resume=False,  ## This is usefull to continue training from previos checkpoint.
                        render=True,   ## This will render the image got through the socket,useful if model is in another computer
                        host=None,     ## If the value is None it trys to find a localhost , else specific host is to be provided as a str
                        port=12345,    ## default value is 12345 set is as required.
                        hiddenUnits=250, ## This no of hiddenUnits in first layer depending on the dimension of input.
                        batch_size=10, ## This is to set batch size for batch reiforcement learning rather than using single episode.
                        learningRate=1e-3, ## This is to set learning rate
                        gamma=0.99,    ## This is to set gamma or the discount
                        decayRate=0.99 ## This is decayRate for RMSprop
                      )                ## This creates an instance of PolicyGradient algorithm as a client_socket

agent.start()         ## This starts the agent ie., connects to the server and communicates and learns from its experience.
```

Running them should launch the env and agent would start leaning. There is a propriety control in mainmodel.py which takes input in its terminal as
- 'p'    ==> Pausing/Resuming the training process
- 'q'    ==> Quit the training process , But this makes a Checkpoint as interrupt.p
- 'ping' ==> This pings the pong server 10 times and returns the average time it took to send and receive packets.
else with a better score of agent, the model is saved continuosly as save.p.
## Fast-training
I have experimented the whole thing with networking sockets and asynchronous methods limiting the training process to human level speed for which I have uploaded the pong-fast-train.tar.gz
``` bash
tar -xvzf pong-fast-train.tar.gz
cd pong-fast
python mainmodel.py
mv save.p ../save.p
```
So this should train the model and save it into the main directory this should load the trained model in the main algo.
