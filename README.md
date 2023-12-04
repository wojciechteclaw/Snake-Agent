# SNAKE-RL

Welcome on the repo presenting my own implementation of Reinforcement Learning using for snake control.

The agent part structure is inspired by <a href='https://github.com/patrickloeber/snake-ai-pytorch'>Patrick Loebers</a> work.

![Snake](snake-rl/docs/snake.gif)

## Run DEMO

`docker-compose up`

**Runs using pretrained model from:**

`/snake-rl/models/q_learning_net_v2.pt`

# Structure
## TRANSMITER

It's a simple flask project enabling the communication between environment state and snake-visualizer app.

It contains two endpoints:

#### /publish-environment
Gets json data and emits it using socketio for listeners observing `new_environment` event

#### /health
Returns ok if service is available.

## SNAKE-VISUALIZER
React + Three.js application visualizing snake in 2D grid of boxes.

It uses following json properties:
* `x_rows (int)` - gives number of columns in x direction
* `y_rows (int)` - gives number of columns in y direction
* `is_sphere (bool)` - if true displays snake grid as sphere else as 2d board
* `is_alive (bool)` - status of snake
* `reward (int)` - reward in the current game
* `score (int)` - score in the current game
* `number_of_steps (int)` - total number of steps in the game
* `number_of_steps_without_food (int)` - number of steps since the last chunk of food was found
* `number_of_games (int)` - total number of games


## SNAKE-RL 
Please read detailed description of the snake concept in designated folder:

[Snake agent docs](./snake-rl/README.md)

