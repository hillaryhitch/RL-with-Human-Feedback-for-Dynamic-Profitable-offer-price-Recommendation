# SUMMARY:

This is a reinforcement learning algorithm to optimize product price recommendation for multiple customer segments based on: 
    
    1. Customer response (buy /no buy)
    
    2. COPCAR (minimum acceptable customer price)
    
    3. Human feedback loop for when customer has no buy
    
The 3 points basically mean:
    
The algorithm uses a Q-learning with an epsilon-greedy policy to learn the optimal prices for a set of products based on customer preferences. 
In addition, the algorithm incorporates human feedback to improve its performance by asking customers if they would accept a higher price for a product if they did not buy it at the current price.

The repository includes the following files:

1. RLHF.ipynb: A notebook with the code and simulation.

2. README.md: a detailed description of the algorithm and how to run the code.

3. requirements.txt: a list of Python packages required to run the code.


To run the code, users can simply execute the RLHF notebook script and follow the instructions provided. 
The script generates output that shows the product prices, rewards, and whether the customers buy the products at the given prices. 
The Q-values for each state-action pair are also updated based on the observed rewards and human feedback.



## The Problem

Imagine a situation where you are a data scientist required to figure out how to recommend the most profitable product for each customer with zero historical information.
(You have multiple products and multiple customers)

There are multiple ways you can go about solving this, but we will tackle this problem using reinforcement learning with human in the loop.

## What is Reinforcement Learning With Human In The Loop:

Reinforcement learning (RL) is a popular technique for solving problems in which an agent interacts with an environment and learns to maximize its reward over time. It has been successfully applied to a wide range of tasks, including game playing, robotics, and natural language processing. 
In this blog post, we will explore how reinforcement learning can be used to optimize dynamic pricing in e-commerce.

In the case of RL with humans in the loop, a human is incorporated into the learning process to provide additional guidance and feedback to the agent.
This approach is often used in situations where the agent has limited knowledge of the problem domain or where there are ethical or safety concerns. 
By incorporating human input, the agent can learn more quickly and effectively and is better able to operate within the constraints of the problem domain.


## How


We will have:
    
    1. 2000 products (dummy products)
    
    2. To make the computation easier, instead of looking at customers individually, we will use segments of customer who behave the same; in this case we have 10 segements
    
    3. Each segment has a minimum price that is profitable
    
    4. A human input function that allows the agent to interact with a human to get feedback on the acceptability of a price for a given customer group and product
    
    5. If there is no input from a human within the specified time limit, the code will move on to the next customer and the next product (you can change this to have a specific rule e.g no for any price below customer minimum price
                                                                                                                                           
The goal of the agent is to learn a policy that maximizes the total reward over time, which is the sum of the revenue earned from selling the products minus the cost of setting the prices.

The code is implemented in Python and uses the NumPy and datetime libraries. It consists of several functions and a main loop that runs the simulation and updates the Q-values for each state-action pair.

The Q-values represent the expected reward for taking a particular action in a particular state. 

The epsilon-greedy policy is used to balance exploration and exploitation during the learning process.

* The code is self explanatory as I have tried to comment as much as possible


