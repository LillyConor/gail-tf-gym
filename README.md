# gail-tf-4gym
TensorFlow implementation of Generatve Adversarial Imitation Learning (GAIL) and Behavioural Cloning (BC) for classic CartPole-v0 environment from OpenAI Gym. 

## Dependencies
- python: 3.5.2
- tensorflow: 1.1.0 (with GPU)
- gym: 0.9.3

## Gym environment 
- CartPole-v0  
- State: Continuous 
- Action: Discrete 

## Implementation of GAIL:

### Step: 1 Generate expert trajectory data  
Reinforcement Learning algorithm: PPO, is used for generating the expert trajectory data for the CartPole-v0 environment.

python3 run_ppo.py

<p align= "center">
  <img src="gail(tf)4gym/gif/training_ppo.gif/">
</p>

### Step: 2 Sample the expert trajectory data from the PPO generated trajectories. 

python3 sample_trajectory.py

### Step: 3.1 Execute Imitation Learning - GAIL.  

python3 run_gail.py  

<p align= "center">
  <img src="gail(tf)4gym/gif/training_gail.gif/">
</p>

### Step: 3.2 Run Behavioral Cloning  

python3 run_behavior_clone.py 

### Step: 4 Test trained policy for GAIL

python3 test_policy.py  
<p align= "center">
  <img src="gail(tf)4gym/gif/test_gail.gif/">
</p>

Default policy is trained with gail  

***--alg=bc*** or ***--alg=ppo*** allows you to change test policy  

### Note: If you want to test bc policy, specify the _number_ of model.ckpt-_number_ in the directory trained_models/bc  
For example to test behavioral cloning:  
python3 test_policy.py --alg=bc --model=1000

### Reference:
- Generative Adversarial Imitation Learning, Jonathan Ho & Stefano Ermon (https://arxiv.org/abs/1606.03476)
- Proximal Policy Optimization by OpenAI: https://blog.openai.com/openai-baselines-ppo/
- GAIL with PPO implementation using tensorflow: https://github.com/uidilr/gail_ppo_tf
- GAIL with TRPO & PPO using tensorflow: https://github.com/andrewliao11/gail-tf
 
