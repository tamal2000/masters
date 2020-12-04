# Deep Reinforcement Learning 

## Topics
- Deep Q learning 
- Actor-Critic Methods 
- Model-Based RL

## Reinforce: 
1. 𝜏 ≈ 𝛒(𝜏|𝜃), 
where 𝜏 = reward, 𝜃 = network parameters 
2. 𝜃 ← 𝜃 + 𝛂∑<sub>t</sub><sup>t-1</sup>𝛾<sup>t</sup>G<sup>t</sup> 𝜵<sub>𝜽</sub>𝝅<sub>𝜽</sub>(a<sub>t</sub>|s<sub>t</sub>) 
where G<sub>t</sub>: discounted reward to-go, 
3. G<sub>t</sub>: ∑<sub>t'</sub><sup>t-1</sup>𝛾<sup>t'-t</sup> 

# Q-Function: 
Q-function is known as state-action value function. q-function is expected discounted reward to-go after executing action a in state t. [after the action is executed, the Q-function expects the agent to follow the policy]
**Q<sup>𝝅</sup>(s,a) = 𝔼<sub>𝛒(𝜏|𝜋, s,a)</sub>[G]**

## Recursive Reward to go: 
- G = r' + 𝛾 G'
- Discount reward to go is equal to reward in next state and discount reward to go in next state. 

## Optimal Q-Function 

* Q*(s,a) =  E<sub>p(s',r'|s,a)</sub> [r' + 𝛾E<sub>𝜋<sup>*</sup>(a'|s')</sub>[Q* (s',a')]] = E<sub>p(s',r'|s,a)</sub> [r' + 𝛾 max Q* (s',a')] 



## ATARI Q-Function Estimator 
- output layer is linear output layer 

## Bootstrap error 
- arg min(Q (s,a) - E[r' + 𝛾 max Q(s',a')])<sup>2</sup>
- Q(s,a) is predict 
- E[r' + 𝛾 max Q(s',a')] is target 
## Deep Q Learning
1. Choose action, a ⟵ arg max Q (s, a')
2. Execute action, s',r'≈ p(s',r'|s,a)
3. update params: 
    - θ ← θ - 𝛂 𝜵<sub>𝜃</sub>(Q(s,a) -r' - 𝛾 max Q (s',a'))<sup>2<sup>
    - s ← s'

## Improve DQN
- Epsilon Greedy: Exploitation only 
- moving target so detach target from graph 

1. Choose action, a ⟵ arg max Q (s, a') or random action 
2. Execute action, s',r'≈ p(s',r'|s,a)
3. update params: 
    - θ ← θ - 𝛂 𝜵<sub>𝜃</sub>(Q(s,a) -r' - 𝛾 max Q (s',a'))<sup>2<sup>
    - s ← s'

# Actor-Critic 
## Policy Gradient: 
Expected reward is equal to expectation with sum over time steps and reinforce actions based on ont discounted reward to go. 

# Monte Carlo rollout: 
have high variance. 

## Baseline 
- subtracting a value form discounted reward to go (b<sub>t</sub> baseline)
- expected value of baseline is 0 
- value function baseline: 
- difference: 
    - reinforce: agent select action based on policy and find the error to fix the policy by exploration and exploitation. 
    - baseline: reinforce + baseline: expected probability of the wining, how much better i did than i expected to do. increase of random reward wrt expected reward. 
- Training: 
    - target: bootstrapped expected reward to go 
    - predict: expected reward or reward? 
    - Step 1: select action 
    - step 2: update the baseline 
    - Step 3: update the policy 

