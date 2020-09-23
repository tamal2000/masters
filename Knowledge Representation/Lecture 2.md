# Lecture 2: SAT solving with Davis Putnam algorithm

Open questions from Lecture 1:  

- What does is mean if 'S' is inconsistences.  

- What would it mean if 'S' is a tautology.  

**Truth Table:**

- Very expensive.
- For N variables, there will be 2<sup>N</sup> combination.

**SAT**

- SAT are NP-Complete 
- Hence the solver takes exponential time to resolve. 
- However, modern SAT solver can solve it quite efficiently.  

## DPLL
Davis, Logemann and Loveland developed DLL.  
this was developed on David Putman's ordinal algorithm and now combined known as DPLL.  

Pseudo code: (DPLL)  Return true is alpha is satisfiable.  

```
DPLL(pa){
    if (pa makes alpah false) return false:
    if (pa makes alpah true) return true: 

    choose p in alpha;
    if (DPLL(pa U {p = False}))
        return true: 
    else return (DPLL(pa {p = True}))
}
```

**Terms**
- **Variables:** simple letters which makes the statments 
- **Clause:** one of the disjunction from the big disjunction. 
- **Literal:** a variable or its negation, 
- **Unit Clause:** A clause with length 1. 
- **Pure Literal:** a literal is pure if no negation is present in CNF or vise versa. 
- **Empty Clause:** is False (disjunction: at least one of these must be true)
- **Empty Set of Clause:**  is True (at )


## David Putnam Procedure 
#### Simplyfy
1. simply the formula, find easy cases and assign values and try to resolve and repeat. 
2. If no easy case, pick a literal and its truth value
#### Split 
3. the process stop: 
    1. if it satisfy all the caluses 
    2. if it fails 
#### Backtrack 
4. If the process fails, may be because of wrong truth value in step 2, so we try with opposit, hence its call backtrack. 


### Simplification: 
- If cluase contains P v ¬P, the variable can be removed. `tautology`
- if `pure literals` it can be set to be true
- if `unit cluase` the literal can be set as true 

## DPLL 2 pseudo code
```
dpll_2(α, literal){
    remove clauses from α containing literal 
    shorten clauses from α containing ¬literal
    
    if (α contains no clauses) return true; 
    if (α contains empty clause return false;

    choose P in α;
    if (dpll_2(α, ¬P))return true; return dpll_2(α, P);
}
```

#### Improvement
- Branch immidiately on unit literals. If literal L does not appear negated in formula F, then setting
L true preserves satisfiability of F. 


### Split 
- RAND: pick a random literal
- DLCS (Dynamic Largest Combined Sum)
- DLIS (Dynamic Largest Individual Sum)
- JW Heuristic J(I)= ∑2<sup>-|w|</sup>




