# Overview
- Game Theory: Introduction 
- Examples of interesting games 
- Strategic Games: Basic Concepts 
- Analyzing Games 1: Basic Concepts
- Analyzing Games 2: Nash Equilibrium 
- Nash equilibrium: Amplification 
- Further Examples of Nash Equilibria 

# Game Theory: Introduction 
## Ingredients of games 
- Games as entertainments or challenge or model 
- Player: one or multiple 
- Rules for action to take 
- Maximize playoff to win 
- competition and collaboration 
## Non-Cooperative 
- Selfish and self-enforcing 
- no coordinated action in group  
## Cooperative 
- coordinated actions in group 
- Non-transferable utility: playoff of each player increases 
- Transferable utility: Need fairway to divide in group to maximize each goals. 

# Example of Interesting Games 
1. Children Dividing pie  (inverse game theory)
    Lets say there are three children. The first child cut the pie in three equal sizes. The second child decides the best to pieces and trim the best piece util he thinks the best two pieces are same. Now the last child decide which piece to take and rest follows. For the trimmed piece the same process will be done again. for three child the number of expected rotation is 3^3^3. Ref: https://arxiv.org/abs/1604.03655   
2. Prisoner's dilemma  
    |  | Quiet | Confess|
    |--|:-----:|:------:|
    |**Quiet**| -1, -1| -12, 0 | 
    |**Confess** |0, -12 | -8, -8 |   

    **Solution:** both confess   

3. Penalty kicks   

4. Ice cream time   
Utility:  
u<sub>1</sub>(x,y) = x + (y - x)/2 = (x + y)/2  
u<sub>2</sub>(x,y) = 1 - y + (y - x)/2 = 1 - (x + y)/2 

5. Partnership game
6. Selfish routing in congestion games 
7. Tragedy of the Commons 
8. Ultimatum game with impatient players 

# Game Theory And Strategic Agent 
Multi-agent decision problem. each agent has an effect on other. 
- Agent's `preferences` encoded as `Utility Function`
- self-interest: strive to maximize own playoff
- Rational behaviors: reason about the actions of other agent. 

## Interaction:
- Simultaneous: players makes moves simultaneously, without knowing other players activity. Rock-paper, bidding 
- Sequential Games: Sequence of successive moves by players who can see other players moves. Chess, card games, 
- Model of games 
    - Sequential 
    - Repeated: 
## Normal-Form Game 
A n-person normal form game is a tuple (n, A, u):  
- N: number of players 
- A: Actions available in the games 
- u: Utility function. u:A -> R<sup>n</sup>
## Normal-form Mixed games 
Players: simultaneous moves, immediate payoffs, playoffs are combination of action payed. 
Playoff Matrix: Specifics for given action combination a and u 
## Utility Function (Neumann and Morgenstern)
preference relation on the outcomes of the games.
- u({(O1: p1), (02,p2)...,}) = \Sum piu(oj)

## Matrix games: 
for two agents, a strategic game can ge plotted in a payoff matrix.
- Rows: actions of agent 1 
- Col: actions of agent 2 
- each cell: playoffs(u1, u2) of two agents for each possible join action.

## Actions space: 
- Continues action space:

## Strategies: 
- Pure: single action 
- Mixed: randomy selct single action. use randomness to outsmart opponent. 
- Strategy profile: s = (s1, s2, s3) 

### Expected Utility: for mixed strategy 
u<sub>i</sub>(s<sub>i<s/ub>, s<sub>j</sub>) = Sum_k Sum_l u<sub>i(a_jk,a_jl)P_ikP_jl 

 
