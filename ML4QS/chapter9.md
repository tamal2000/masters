
2. Assume that we used data similar to our crowdsignals data. The objective is to make the user more active. What could be an appropriate definition of a reward function for a reinforcement learning algorithm we could deploy based on the data we have? 
	- definition of a reward function. 

4. A lot of the reinforcement learning algorithms revolve around the Markov property. Given an example of a setting in the quantified self where the Markov property is clearly not satisfied. Explain why the property is not satisfied. 
	- Markov property not satisfied. 



# Reinforcement Learning to Provide Feedback and Support
Using reinforcement learning to recommend or predict action. 
	- advice on how to avoid stagnation. 
	- what action will boost the mood. 
	- Suggest on how to maintain heartbeat zones while working out. 
	- advice on sleeping time. 
- Basic Settings 
	- Environment/User: one of the quantified selves. 
	- agent: software that decides when and how to support user. 
	- state, s: user/environment at certain point. 
	- time, t: certain point in time. 
	- x_t: sensor value at time t. 
	- action, a: available action in the current state. 
	- reward, r: the result of taken action in a sate s. 
	- value function: total rewards agent may accumulate in the future. 
	- policy: action to perform in given state. 
	- exploration 
	- exploitation 
	- γ is a discount factor. value γ = 0 we only care about the immediate reward while for a value of γ = 1 future rewards are equally important as the current reward.
	- Markov Property when both probabilities are equal for all rewards r and states s over all time points.
	- 
- One-step SARSA temporal difference Learning 
- Q-learning:
- SARSA and Q
- Approximate solutions 
- Discretizing the state space

