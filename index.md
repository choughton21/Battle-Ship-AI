## Welcome to Battle Ship AI

### Introduction

In this project, we teach a computer to play battleship. Since battleship is a technical game and the ideal move changes as the game progresses, it is interesting to see how well we are able to tach the AI to play. The main reason this is a challenging task is that we need advanced algorithms to learn how to play the game, if we want our AI to actually play well, and the learning technique needs to understand how to learn well. If an adult plays battelship against a toddler who makes moves randomly, the adult will win almost every time. Our goal is to train the computer to play less like a toddler making random moves and more like a skilled adult; this is a challenging task. The fact that deep learning is a black box is a further difficulty since we cannot help the computer learn better since we do not know how it is learning exactly, and we only see performance. We hope to find that after training, our AI is able to play battleship well beyond that of a random player.

In terms of an ethical extension, as battlehsip is a game that mimicks a military procedure, we talk about some of the ethical implications of AI being used for military purposes.

### LITERATURE REVIEW

There are a few projects that have been done which talk teach AI to play board games. In the article, Measuring AI advancement through games, the authors discuss the progress of AI in terms of playing several different board games. Some of the games they look into are Chess, Pacman, Texas hold'em, Jeoparty, Atari, and Dota2. These games have all been conquered at some level, and most of them have an AI which can beat all human players. There is one game which is yet to be conquered and that game is Bridge. The article also talks to OpenAI and their platform, universe, to continue training AI for games and other projects.

Google has created an AI to play the board game, GO, and it has been able to beat some of the highest regarded GO players in the world. First it was able to beat Lee Sedol in 2016 and then in 2017 the AI beat GO grandmaster Ke Jie. In terms of AI and learning to play board games this was a huge accomplishment. The game was livestreamed on Youtube. The number of possible boards for GO is larger than the number of atoms in the universe.

In addition to GO, a board game that has been studied with AI is Ticket to Ride. In thier paper, Lee, Silva, Togelius, and Nealen discuss a few playing styles are taught and then analyzed to see how effective each is. They use the playing styles to look at what pieces of the game are most valuable in terms of winning. They find that certain cities are more important in order to win the game.

The research on AI and games is not all board games, and OpenAI ran a project for teams to compete to play hide and seek. the teams had to adapt to each other while they were playing. The games start crazily and frantic but finally, after many rounds, the hiders learn to lock out the seekers to win in general. The hider-teams had to learn to work together. They found some errors with the way they coded the physics, and it created some fun-to-watch results that would not be possible in a real game of hide and seek.

### METHODS

In this project there are a few steps taken before the learning can take place. To begin, I used python to write a battleship game. After this, I used an openai gym environment and stable baselines3 reinforcement learning library for the implementaiton of the learning algorithm and finally I will use pytorch to build my neural network. 

The input to the network is a two-dimensional array which is coming from the python battleship program,and the output are actions (moves) which are represented as a one dimensional array. 

In order to have the AI able to learn, I found a framework from https://towardsdatascience.com/creating-a-custom-openai-gym-environment-for-stock-trading-be532be3910e and, as it turns out, you must use classes for the AI to be able to learn. The first step to using the framework was therefore to turn the program I had written into a class. After this, we created the _init_ function to define the action space and the observation space for the AI, and we set a reward variable. We then made the makeObs function which computes an observation for the network and decides what info the network will use to make an action. We also make step, reset, and render functions to help with execution of the game and communicate with the network.

Once this was working, we ran it and saw the results after 100 games of battleship. The following are our initial results:


In terms of rewards, we tried a few different reward structures and we saw different results. At first, we gave only positive rewards, and rewarded every time the AI hit a ship, and again when they sunk a ship. This seemed to only give mediocre results and the network, against a random player, was not doing much better than 50%.

We decided to give more weight to the end of the game win, less weight to sinking a ship, and we removed the reward for each ship “hit”. 

(currently at the stage of getting the output from python to make sense with the openai gym environment)

### DISCUSSION

From this project I will present the results from the AI playing battleship against a random opponent. I will show the initial win-rate and game time, and then will show the win-rate and game time after learning. To compare the work to others, I will reserach battleship AIs and compare on the win-rate, and also touch on the differences between my project and other board-game AIs. I will also touch on the techniques I have learned along the way and how I learned to implement the gym environment. Finally I will discuss the different tweaks and turns I did during the training, to try and have the AI learn better/ more accurately. We do hope that the AI is able to play better after learning, but if not, then we will discuss some of the potential places where this went wrong. 

Following, I will talk about the pros and cons of AI being used for military robotics and how AI might shape the military in the future. 

### GRAPHED RESULTS


### ETHICS DISCUSSION
Battleship is a game in which you aim to sink your opponents’ ships by launching attacks. In this project, we looked at an AI who will learn where to launch the attacks as to best defeat the opponent. However, if this was not a game and was AI for the military the stakes are quite a bit different. For example, a “miss” might mean firing into a civilian town instead of hitting a military base. In terms of AI and use by the military this concern should be addressed; it is not easy to train the AI and consequences means lives lost. In economics we learned that the US government places each life at about US $125,000, but the US military budget is 1.92 trillion. If the military wants to run tests and only values lives at 125,000 they might be a little bit too quick to trust their AI, and I am not aware of any real ramifications in play for the military if a test goes wrong. Of course, there is a positive look that if AI can provide more accuracy than humans can in various situations, then we might actually avoid causalties and mistakes could happen much less. This would be of course a benefit, and there are many applications where technology has improved the military so far. For example, weapons, transportation, machines to carry items, robots to detect and robots that can shoot. 

AI however should be treated a bit differently since it is something that “thinks” and to the extent that we do not know exactly what a network has learned, we don’t know how the network will behave. It could be that for 100 days the network looks perfect and does what it should, but on the 101th day everything happens badly. There is no way to truly know why the change happened or what caused the good days in the first place. There are positives and negatives to using AI with regards to the US military, but I do believe we should approach the subject with caution.



### REFLECTIONS
