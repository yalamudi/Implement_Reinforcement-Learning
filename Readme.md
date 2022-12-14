This project aims at Implementing Reinforcement Learning by gaming.
We are gonna build an AI model specifically a reinforcement learning model to be able to play mario to see the back and forth as we go and build up this model.

We are going to run this in python language. We're going to be using open ai gym.This is a common framework that makes it easy to train ai to play games
and interact with other simulated environments think alphago but on a smaller scale for our mission we are using gym super mario brothers environment that's
been built - "https://pypi.org/project/gym-super-mario-bros/" on top of the NES emulator for python.

Our code is written with each line of explaination. The way that the environment works is using "Reward function" that can be known in gym-super-mario-bros

Preprocessing the Environment: You can know Rubbish Data = Rubbish AI, We need to preprocess our mario game data before we ai fight we applied 2 preprocessesing steps grayscale and frame stacking our ai is going to be taking images of the mario game to learn. A color image has 3 times as many pixels to process, So converting it to grayscale cuts down the data it has to learn from frame stacking helps our ai have context by stacking consecutive frames we're effectively giving our ai model memory it'll be able to see mario and his enemies movements time to pre-process.

Install RL libraries: You need to have some sort GPU acceleration running either CUDA or ROCm 4.2(beta) to display your output. One can check GPU versions and install from https://pytorch.org/get-started/locally/ which ever version suits your GPU

Install Stable-Baselines3: There are certain algorithms that are available we can check it "https://stable-baselines3.readthedocs.io/en/master/" here we are going to use DQN. We used all these in wrappers that are explained in code.

Applying Vectorization: we are going to stack our frame using VecFrameStack(env, 4, channels_order='last')

Training Reinforcement model: We are going to use Proximal Policy Optimization algorithm. Firstly we import those dependencies and then we are going to have a sample code that actually allows you to save models as you're training them so you can actually go back through and see the different models that you've actually gone and built so let's go ahead and do this and we'll be able to import our dependencies.
# Import os for file path management
import os 
# Import PPO for algos
from stable_baselines3 import PPO
# Import Base Callback for saving models
from stable_baselines3.common.callbacks import BaseCallback
In the code we have class TrainAndLoggingCallback(BaseCallback) where you can find cod eto tain our model.

Finally Testing:
Now we are going to test first we are going to load our model from memory so say for example we stop this training or we shut down this notebook we want to be able to reload it from a file rather than relying on the model that we've got in memory so we can do this so in order to do that we can use model.load or the actual ppo.load method.
According to code: We are going to train our model and implement that trained model in the code as per quoted.

Finally our code when we run it output will be opened in a new window.

