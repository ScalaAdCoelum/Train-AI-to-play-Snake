# Deep Reinforcement Learning
## Project: Train AI to play Snake
*Some History:*

Among the development phase, the project has undergone significant enhancements, notably with the capability to optimize the Deep Reinforcement Learning (RL) approach through Bayesian Optimization. This addition empowers users to fine-tune and enhance the performance of the Deep RL algorithms. Notably, the code for Deep Reinforcement Learning has been migrated from Keras/TensorFlow to PyTorch, reflecting a shift in the underlying framework.

- I opted for PyTorch in my recent project update because of its dynamic computational graph, which offers a more intuitive and flexible approach to constructing and modifying neural networks during runtime. This dynamic nature significantly simplifies the processes of debugging and experimentation, making PyTorch an excellent choice for my research and prototyping endeavors.

- Moreover, I appreciate PyTorch's imperative programming style, often acknowledged for its readability and conciseness. This feature allows me to express complex ideas with fewer lines of code, enhancing overall code maintainability and fostering collaboration among developers. The seamless integration of PyTorch with Python is another factor that aligns well with the existing Python-centric deep learning ecosystem.

- While acknowledging TensorFlow's status as a powerful and widely used framework, my decision to transition to PyTorch reflects a preference for its dynamic graph capabilities, ease of use, and alignment with the specific goals of my project. The emphasis on experimentation and readability in the context of Deep Reinforcement Learning further solidifies PyTorch as the preferred framework for my development needs.

## Introduction
My primary goal was to create an AI bot that could learn how to play the famous game Snake. This project involves various challenges & issues :
- Reinforcement Learning Challenges
- State Representation 
- Training Time
- Sequence Learning
- Ethical Consideration

I opted for the Deep Reinforcement Learning algorithm [https://en.wikipedia.org/wiki/Deep_reinforcement_learning#:~:text=In%20model%2Dbased%20deep%20reinforcement,control%20using%20the%20learned%20model.] wich consists in giving the system, parameters related to its state, and a positive or negative reward based on its actions.
As for the goal after this, at the genesis of it, it was to figure it out and elaborate a strategy to maximize the score due to it's rewards or penalties.
Using Deep Q-Learning algorithm, I trained the AI bot with the Bayesian Optimization method, wich ensures the system to have the optimal parameters to train effectively. 
[https://en.wikipedia.org/wiki/Q-learning] (*Reinforcement Learning (RL) is a type of machine learning where an agent learns to make decisions by interacting with its environment*)

## Run
To run the game, executes in the snake folder:

```python
python snakeClass.py
```
Arguments description:

- --display - Type bool, default True, display or not game view
- --speed - Type integer, default 50, game speed

The default configuration loads the file *weights/weights.h5* and runs a test.

To train the agent, set in the file snakeClass.py:
- `params['train'] = True`
The parameters of the Deep neural network can be changed in *snakeClass.py* by modifying the dictionary `params` in the function `define_parameters()`

If you run snakeClass.py from the command line, you can set the arguments `--display=False` and `--speed=0`. This way, the game display is not shown and the training phase is faster.

## Optimize Deep RL with Bayesian Optimization
[https://medium.com/@okanyenigun/step-by-step-guide-to-bayesian-optimization-a-python-based-approach-3558985c6818] Shout-out to this article that granted help.
To optimize the Deep neural network and additional parameters, run:

```python
python snakeClass.py --bayesianopt=True
```

This method uses Bayesian optimization to optimize some parameters of Deep RL. The parameters and the features' search space can be modified in *bayesOpt.py* by editing the `optim_params` dictionary in `optimize_RL`.