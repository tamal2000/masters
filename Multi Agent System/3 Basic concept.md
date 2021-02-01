# Game Theory Basic concept 
### Ingredients of interesting games
- Players: one to multiple 
- `Rules` determine `action` which returns `pay-offs`
- Target: maximize payoff 
- competition and collaboration: individuals or team 

### Cooperative vs Noncooperative: 
- non-cooperativce: 
    - selfish individuals
    - do not coordinate actions in group 
- Cooperative: 
    - payoff of each individual increase 
    - need to find a fair way to divide the additional utility. 

## Game and solutions: 
1. Children dividing pie:
    - selfish but rational 
    - minimax and maximin 
        - cutter: mitigate the worst result that chooser can enforce 
        - Choose: maximizing his payoff 
2. Prisoner' dilemma
    - find maximum penalty for action
    - minimize between action. 
3. Penalty kicks
    - find minimum gain from each action
    - select action that would maximize the most 

## Normal-form games (Matrix Games)
- players: make simultaneous moves and immediate payoffs. payoffs are specified for combinations of actions played. 
- Payoff: specifies for given action combination the corresponding utility for player. 
- n-person normal-form games in (N,A,u) tuple 
    - N is number of players 
    - A actions available for each players 
    - u, Utility function, combination of action payoff 



Game theory studies the  multi agent decision making problem where it focus on individuals actions in given scenario. 
- Assumptions:
    - Utility function(pay off) has the agent's preferences. 
    - each player tries to maximize its pay off 
    - each player consider other players action while defining its own game strategy. 
- Expected Utility for mixed strategy games 
    - Pure Strategy: utility u_i for agent i for selecting action a_i = u_i(a_i, a_-i)
    - Mixed strategy: Agent i plays strategy s_i which is a probability distribution over k possible actions.
    - Expected utility for mixed strategy
    $u_i(s_i, s_j) = \sum_k \sum_l u_i(a_ik, a_il)p_ik p_il$

## Basic Concept 
### Pareto optimality 
- combination of actions of each players where the join outcome is the maximum. 
- is a solution property. 
- a join strategy profile is pareto dominated by another join action. for all agents 

### Best response 
- from agent's point of view the best response to strategy profile s_i 
- for a given input x of player 1, what input y of player 2 maximizes the latter's utility (u2(x,y))

### strictly dominate
A strictly dominated strategy will never be the best resposne to anything 
### weakly dominates 
- overlaps players dominance 
### Iterated elimination of strictly dominated strategies - IESDS 
rational agents never play strictly dominated actions, hence strictly dominated actions can be eliminated 


# Nash Equilibrium 
- a solution concept based on conditions instead of an algorithm 
- for each agent strategy is a best response 
- Pure NE for each agent is the best best response to other agent. 