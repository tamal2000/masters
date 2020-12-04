# Markov decision Process (MDP)

Open Questions:
1. what is v_π, q_π?
2. what is Bellman equation?
3. what is deterministic policy
4. what is deterministic transition 
5. Optimal policy 

# What is Reinforcement Learning 
- RL: interact, explore, exploit experience
- __Environment:__
    - state(s)
    - action(a)
    - transition: s --a--> s'
    - reward: r (s,a,s')
- __Policy π:__ tell for each state (s), which action (a) to take  
- __RL Goal:__ Determine optimal policy π<sup>*</sup> for optimise end-result {long-term/cumulative reward}

- Overview: 
    1. MDP: state, actions, transitions, rewards -> Policy, Value Function
    2. Policy: What to do -> value function 
    3. value functions: v(s), and q(s,a) -> Bellman equations 
    4. Bellman equations -> SARSA, Q-learning 
    5. SARSA and Q learning -> value function 

- Challenges: 
    - evaluate reward, not prescriptive 
    - Sequential/delayed consequences 
    - Online learning: improve policy while interacting.
    - trail and error, combine of exploration and exploitation.  

# Markov Decision Process MDP 
- Markov decision process provide a formal model for a sequential decision problem. 
    - A finite MDP (S,A,P,R,𝛾)
        - discrete time t = 0, 1, 2
        - a set of sates, s ∈ S 
        - a set of actions, a ∈ A
        - transition function: p(s'|s,a) probability of transition to s to s' with action a 
        - reward function: r(s,a,s') = E[r|s,a,s']
        - discount factor: how important are future reward (0 < 𝛾 > 1)
- Transition Probability: to state s' when taking action a in state s:
    - p(s'|s,a):= P(S_t+1 = s'|S_t = s, A_t = a) = P(s'|s,a)
    - deterministic: p(s'|s,a) = 1
    - probabilistic: p(s1'|s,a) = 0.7, p(s2'|s,a) = 0.3 

- Expected immediate reward: transition from state s to s' under action a: 
    r(s,a,s'):= E(R_t+1 = r | S_t =s, A_t=a, S_t+1 = s') = E(r|s,a,s')
- Markov Property: 
    - (Future is independent of Past | Present)
    - current state is sufficient statistic 
    - conditioning action on the history cannot possibly help 
- Chess as MDP:
    - current state provides all the information need to determine next(optimal) move. 
    - No need to know the history 
    - can restrict reactive policies 


# Policies, Value Functions and the Bellman Equation 
- Policy: Policy, π specify what actions should be taken in a given state. 
    - Deterministic policy, π(s) = a
    - Stochastic policy, π(a|s):= P(A<sub>t+1</sub>=a|S<sub>t</sub> = s)
- Long-term return: $G_0(s_0) = ∑ R_t$
- Discounted return: $G_0(s_0) = \sum{R_t+k \cdot \gamma^{k-1}}$
- Recursion relation: $G_t = R_{t+1} + \gamma G_{t+1}$
- Episodic task/Infinite horizon: if episode termination as transition to an absorbing state with self-transition and zero reward. 
- State value function v<sub>π</sub>(s): value of state s when actions are specified by policy π. v<sub>π</sub>(s) = ∑ R<sub>t</sub> [deterministic policy]
    - Expected value v<sub>π</sub>(s) = E<sub>π</sub>(∑R<sub>t</sub> | s<sub>0</sub>=s) [probabilistic policy]
    - $v_\pi(s) = E_\pi (\sum{\gamma^{k} R_{K+1}|S_0 =s })$
- State action value function for policy π: 
    - q_π = E[G_0|S_0=as,A_0 = a] = E[∑ 𝛾^k R_k+1]

-v_π(s) vs q_π(s): 
    - v_π(s) allows the policy π to dictate every action along the path. 
    - q_π(s): first action a is taken independently of the policy π, from then onward, π dictates the remaining actins taken along the rest of the path. 
- Relationship between v_π(s) vs q_π(s): 
    - v_π(s) = ∑ q(s,a) π(a|s)

# Bellman equations 
- For Deterministic policy: v_π(s) = r(s,a,s') + v_r(s')
- For stochastic policy: v_π(s) = ∑ π(a|s)q_π(s,a)
- Bellman equation: q_π(s,a) = ∑ p(s'|s,a) [r(s,a,s') + 𝛾v_π(s') ]


# Bellman equations for optimality 
- The optimal value functions are defined by the pointwise maximum over policies 
    - v^*(s):= max v_π(s) 
    - q^*(s,a): = max q(s,a) 
- The optimal policy π* such that tis value functions corresponds to the optimal value functions. 



# Taxonomy of RL problems 

* Finite MDP
    - discrete time t = 0,1,2,... 

* The Markov properties 

* Policy 
    - deterministic policy 
    - Stochastic policy: π(a|s) 
    - deterministic vs probabilities policy 

## Long-term (cumulative) return 
G = r<sub>t+1</sub> +  𝛾 G<sub>t+1</sub>
G is stochastic which can be fixed by mdp with policy 


## Bellman Equations

q<sub>π</sub>(s,a) = E[G0|S0 = s, A0 = a]
= ∑ E[G0|s0=s, a0 = a, S1 = s']p (s'|s,a)

### backup Diagram 




