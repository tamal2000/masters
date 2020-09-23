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

Pseudo code: (DPLL)  

```
DPLL(pa){
    if (pa makes alpah false) return false:
    if (pa makes alpah true) return true: 

    choose p in alpha;
    if (dpll(pa U {p = False}))
        return true: 
    else return (depll(pa {p = True}))
}
```




