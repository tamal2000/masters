# Game Theory Basic concept 
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