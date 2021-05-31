# Language Structure

- Parsing: consists of assigning structure at a sentence level.  
- Parser: A parser produces a syntactic tree for every sentence.  

## Syntax: chapter 12.1-12.4
### Learning Goals 
- What dose a syntactic tree represent? 
- what is a grammar?
- Types of grammars: phrase structure and dependency grammars. 
- What is benchmark? 
- What are Universal Dependencies? What is the motivation to use Universal Dependencies? 

### Slides 
- Representing: how do we represent language in a way that we can transform a text into a quantity by means of algorithmic method. 
- Structure: represent the structure of language for each level of linguistic analysis. 
- Levels of Linguistic Analysis: 
    - Sound - Phonological -> Phonemes -> Morphological -> Morphemes -> Lexical -> Words -> Syntactic -> Syntactic Structures -> Semantic -> representation structure -> pragmatic -> Communicative intentions
- Syntax: The study of sentence structure. 
    - Syntax is used for finding the structure in sentences by determining how the words relate structurally to each other. 
- Properties of Syntactic structure. 
     - Composition of expression: The hierarchical analysis of the subparts of an expression (top down)
     - The relation: syntactic functions or relations, how do words in the expression relate to each other. 
- Views of Syntax
    - Dependency: Focus on functional roles. 
        - dependency tree: syntactic structure represented 
            - words: tree node
            - Dependency: directed arcs between nodes 
            - Functional roles: arc labels 
            - Idea: lexical items linked by binary asymmetric relations called dependencies. 
            - Criteria for Head and Dependents: 
                1. H determines the syntactic category of C; H can replace C 
                2. H determines the semantic category of C: D specify H. 
                3. H is obligatory; D may be optional 
                4. H selects D and dtermines whether D is obligatory. 
                5. The form of D depends on H 
                6. The linear position of D is specified with reference to H 
            - issues:   
                - Syntactic versus semantic criteria
                - Exocentric versus endocentric constructions 
            - tricky cases:
                - complex verb gorups
                - subordinater clauses 
                - Coordination 
                - Prepositional phrases 
                - Punctuation 
            - Graphs 
                - A dependecy structure can be defined as directed graph G 
                    - a set V of notes 
                    - a set A of arcs 
                    - a linear precedence order 
                - Dependency graphs: 
                    - Nodes in V are labelds with word forms 
                    - Arcs in A are labeled with dependency types 
                - Connectedness, Acyclicity and Single Head 
                    - Instuitions: 
                        - syntactic structure is complete(Connectedness). 
                        - syntactic structure is hierarchical (Acyclicity)
                        - Every word has at most one syntactic head(single head)
            - Universal Dependecies (UD)
                - Standardized framework for dependecy annotation 
                - Consistent analysis across typologically different languages. 
    - Constituency: focus on structural categories 
        - Phrase structure trees: 
            - words: terminal nodes 
            - Phrases: internal nodes 
            - Phrase Types: node labels 
            - Constituency treebanks 
                - treebanks with constiuency-based annotation 
                - example: Penn Treebank of English 
            - Tree bank grammer: 
                - CFGs from constituency treebanks. 
                - based on syntactic parsers 
        - Context-free grammars: phrase structure can define defined 
            - finite terminal and non-terminal symbols and rules
            - a distinguished non terminal symbol S for Start 
        - Constituents: have similar internal structure and behavior 
            - situation: similar constituents can replace each other. 
            - movement: words in a constituent move together. 
            - Type: Noun phrase - NP, Verb phase - VP, Prepositional phrase - PP 
    - Treebanks: 
        - syntactically annotated corpora are called treebanks. 
        -  used to train and evaluate syntactic parsers 
        - many corpora have been annotaged with universal sysntactic dependencies. 
    - CoNLL Representation: 
        - Treebanks can be provided in many formats 
        - One of the formats is the conll format where information is presented in rtab separated columsn 
        - CoNLL - Conference on Natural Language Learning is the nsame of the yearly conference 



## Parsing: Chapter 13.1, 14.1-14.41,14.6
### Learning Goals
- A grammar is not a parser. What is grammar? what is a parser?
- Main parsing strategies. 
- What is dependency parsing?
- Transition baed dependency parsing. 
- How are parses evaluated?
- How can error analysis of parsers be performed? 
- Interpret a syntactic tree
- Extract syntactic features from a syntactic tree
- Run a parser and understand the output of the parser. 

### Slides 
- Grammar: is a declarative model (set of rules) which defines a particular language. 
- Parser: is the actual realization of the model implemented into a grammar which assigns a structure to strings by meaning of specific algorithm. 
    - uncovering the syntactic structure of language
    - It involves recognizing higher level units of structure 
    - important prerequisite for building systems capable of understanding language. 
    - syntactic parsing is a structural prediction problem. 
- Structural Ambiguity: like phrase structure parsing, dependency parsing has to deal with ambiguity. by scoring dependency trees and disambiguate by choosing a dependency tre with the highest score.   
- Dependency Trees: 
    - h -> d, h is called `head` and h is called `dependent`. 
    - the arcs from the rooted tree. 
    - input: sentence: x with w0 as root 
    - output: Dependency graph G
- Parsing Approaches 
    - Grammar-based parsing 
        - context-free dependency grammar 
        - Constraint dependency grammar 
    - Data-driven parsing
        - Transition-based model
            - idea: Define a transition system/state machine for mapping a sentence to its dependency graph. 
            - learning: induce a model for predicting the next state transition, given the transition history. 
            - Parsing: Construct the optimal transition sequence, given the induced model
            - characteristics: local training of a model for optimal transitions, greedy search/inference 
        - Graph-based models
            - idea: define a space of candidate dependency graph for a sentence 
            - learning: incudes a model for scoring an entire dependency graph for a sentence
            - parsing: find the highest-scoring dependency graph. 
            - characteristics: global training of a model for optimal graphs, exhausting search/inference

- Dependency Parsing: 
    - Transition-based dependency Parsing. 
    - Transition based parsing: shift-reduce parsing 
    - Transition based parsing: Arc-Eager Parsing 
    - Classifier based parsing
    