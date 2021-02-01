# Multi-Agent Systems
# Overview of Exam Topics 
Dec'2020  
## 1 Game Theory
### Payoff matrix in normal form game 

### Best response, mutual best response 
- Best response: is what player should do to maximize payoff. best response is not necessarily unique. when best actions includes two or more actions, then the agent must be indifferent amount them. any mix of these actions would be best response (mixed) strategy. 
- Mutual best response: 
- Dominant strategy: if all the best strategies of a single player matches then it know as dominant strategy for that player. 

### Pareto 
- optimality: an outcome of a game is Pareto optimal if there is no other outcome that makes every player at least as well off and at least one player strictly better off. 
- dominance: defines a partial ordering over strategy profiles. 

### Dominated strategies: 
is dominated by at least one of the agent. A strictly dominated strategy will never be the best response to anything. 
- strictly dominated strategies payoff is less regardless what other player dose. 

### IESDS 
- it is common knowledge that all agents are rational. 
- rational agents never play strictly dominated actions. 
- strictly dominated actions can be eliminated. 

### Grip trigger:
Players cooperate in in finte repeated game as long as other players has coopearted in past. but as soon as a player defected once, the other player will defect ever.  

## 3. Reinforcement Learning

### First-visit and every-visit Monte Carlo 
- **First-visit MC:** average returns only for the first time s is visited in an episode. 
- **Every-visit MC:** average returns every time s is visited in an episode. 
- pseudo-code: 
    - Initialize, π, v and Returns(s) - empty list 
    - For loop:
        - generate an episode using π
        - for each s appears in the episode: 
            - R <- return following the first occurrence of s 
            - append R to Returns(s)
            - V(s) <- average(Return(s))
Update Rules:
#### Temporal Differencing (TD)
Temporal differencing (TD) use Bellman eqs to propagate values  
v(s) <- r + v(s')  
v_new(s) = (1 - alpha)v_old(s) + alpha(r + v_(s'))  
V(s_t) <- V(s_t) + alpha(R_t+1 + gamma V(s_t+1) - V(s_t))  
pseudo-code: 
- initialize v randomly to evaluate π 
- repeat for each episode: 
    - initialize s 
    - repeat for each step of episode: 
        - a <- action given by π for s 
        - take action a and observe reward, r and next state, s'
        - V(s) - V(s) + alpha(r + gamma v(s')- v(s))
        - s <- s' 
#### SARSA 
In state s, action a, transition to state s' use policy π to select next action a'
q_π(s,a) <- q_π(s,a) + alpha(r(s,a,s') + gamma q_π(s',a') - q_π(s,a))

#### Q-learning 
bootstrap with best action, not actual action
q(s,a) <- q(s,a) + alpha(r(s,a,s')+gamma max_a q(s',a') - q(s,a))

### On policy / Off policy 
SARSA on policy but q-learning off policy. 