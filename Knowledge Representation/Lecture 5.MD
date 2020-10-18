# Ontologies & Logics for Ontologies

Problem with CNF: 
- hard to construct and quite hard to read. 
- Becaome very big, even for small problems. 

What can be more usable by peole and still usable by computers?  
Ans: `Ontologies` and `Description Logic`
**Ontology:** a way to organize knowledge that is useful for people. 
- Conceptualization: chairs, class, room, tables, 
- shared: shared with others.
- formal: so that computer can understand 
- explicit: specification explicit.   
**Description Logic:** a logic tht allows omputres to reason with ontologies. 
## What is an ontology?
- ontology defines the terms used to describe and represent an area of knowledge. 
- Defines `terms` and `relations`
- forms vocabulary of a topic area. 
- `rules` of combining `terms` and `relations`. 
- to `infer` extensions to the vocabulary. 
- Goal: knowledge sharing 
    - communicate between people. 
    - interoperability between software agent. 
## Ontology Elements
- **Class:** a name and set of properties that describe a certain set of individuals in the domain. 
- **Instances:** The members of the sets defined by classes. 
- **Property(relation):** assert facts about the instances.

## Real life examples
- handcrafted:
    - music, biomedical.
- Automatic: 
    - ranging from lightweight: UNSPC, Open directory. 
    - ranging form small (metar) to large 

## Operators for Ontologies
### Class Axioms
- **Equivalent class:** calss contain the same individuals and have the same definition. 
- **Complement class:** the complement of a class contains all individuals that are not in the class. 
- **Disjoint** classes do not contain the same individuals
- **Union** contains all individuals that belong to the classes of the union. 
- **intersection** contains individuals that each belong to both classes.
### Class Restrictions 
Example: NobelPrizeWinners is exactly the class of all Persons who have won a NobelPrice.  NPW ≡ P ∩ ∃<sub>won</sub>NP.  

Example: `NobelPrizeWinners` is the subset of all `Person` who were `nominatedFor` a `NobelPrize`.  NPW ⊆ P ∩ ∃<sub>won</sub>NP.
  