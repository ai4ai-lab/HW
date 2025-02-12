# Gridworld Reinforcement Learning (Q-Learning)

Due date: Wed 19 Feb 2025 EOD

Submission Instructions:
--------
Turn in your code script marked firstname_lastname.py
Late submissions will be penalized by 10\% per day late and will not be marked after the 3rd day. 
Then read the paper linked in the homework titled Risk Sensitive Dead End Discovery and answer the questions below. Upload these as a pdf 


In this exercise, you will implement the interaction of a reinforcement learning agent with its environment. We will use the Gridworld environment from the second lecture. You will find a description of the environment below, along with two pieces of relevant material from the lectures: the agent-environment interface and the Q-learning algorithm.

1. Create an agent that chooses actions randomly with this environment. 

2. Create an agent that uses Q-learning. You can use initial Q values of 0, a stochasticity parameter for the $\epsilon$-greedy policy function $\epsilon=0.05$, and a learning rate $\alpha = 0.1$. But feel free to experiment with other settings of these three parameters.

3. Plot the mean total reward obtained by the two agents through the episodes. This is called a **learning curve**. Run enough episodes for the Q-learning agent to converge to a near-optimal policy. 


## The environment: Navigation in a gridworld

<img src="/Screenshot 2025-02-12 at 11.54.13.png"; style="width: 200px;" align="left"/>

The agent has four possible actions in each state (grid square): west, north, south, and east. The actions are unreliable. They move the agent in the intended direction with probability 0.8, and with probability 0.2, they move the agent in a random other direction. It the direction of movement is blocked, the agent remains in the same grid square. The initial state of the agent is one of the five grid squares at the bottom, selected randomly. The grid squares with the gold and the bomb are **terminal states**. If the agent finds itself in one of these squares, the episode ends. Then a new episode begins with the agent at the initial state.

You will use a reinforcement learning algorithm to compute the best policy for finding the gold with as few steps as possible while avoiding the bomb. For this, we will use the following reward function: -1 for each navigation action, an additional +10 for finding the gold, and an additional -10 for hitting the bomb. For example, the immediate reward for transitioning into the square with the gold is -1 + 10 = +9. Do not use discounting (that is, set gamma=1).

Risk sensitive Dead End Discovery Questions:
-----------------
1) How does the proposed solution in the paper differ from Q-learning?
2) Describe the Distributional RL paradigm and how it works
3) What are the limitations of the proposed approach for dead-end discovery
4) How might you formulate the problem of finding dead ends differently instead of using distributional RL?
