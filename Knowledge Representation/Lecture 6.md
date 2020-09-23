# What is an ontology:
An ontology is a formal, explicit specification of a shared conceptualization. 
  - how can we model knowledge of a certain field. 
  - **conceptualization** Conceptualization: Abstract simplify view of the world. 
  - Shared: the explicit method to share conceptualization. 
  - **Formal:**
  - Explicit specification

**Definitions of ontology:**
- An ontology defines that terms used to describe and represent an area of knowledge 
- an otology: define the basic terms and relations, that forms the vocabulary of a top area as well al the rule for combining terms and relations to infer extensions to the vocabulary
- The goal of an ontology = knowledge sharing and reused communication between people and software agent. 

**Ontology Elements:**
- Class: a name and a set of properties that describe a certain set of individuals in the domain: person, name, birthday id
- Instances: the members of the sets defined by classes: example: person45, name=frank, birthday=10102020
-  Property(Relation) l assent facts about the instance: person45 is -father-of person256

Example of Ontology: Movie ontology

-Class: 
   - movies:
       - Horror
       - Crime
       - Scifi
         - a
         - b   
   - Director:
     - Name
     - birthday 
   - Actor:
     - Name
     - DOB
- properties:
  - title
  - budget,
  - debut showing
- Instances:
  - Tom cruise
  - Titanic 

### What's inside on ontology?
 Class + class hierarchy
 instances 
 slots/values
 inheritance

## Property Types
- **Symetric Property:** If type(p, Symmertric Property)and p(x,y) then p (y,x). example IsMarriedTo. 
- **Asymmetric Property** if type (p, Asymmetric) and p(x,y) then p(y,x) is inconsistent. 
- **Transitive Property** If type (p, transitive) and p(x,y) and P(y,z) then P(x,z)
- **Functional Property** if type (p, functional) and p(x,y) and p(x,z) and then y = z 
- **Inverse Property** if type(p, inverse) and p(x,y) and p(z,y) then x = z
- **Reflexive Property** if type (p, reflexive) then ∀x P(x,x). all sets are subset of its own subset
- **Reflexive Property** if type (p, irreflexive) and p(x,x) then p(x,x) in inconsistent. 
- **Inverse** InverseOf(p,q) then P(x,y then q(y,x). parentOf, childOf. 

# Description Logic
a family of knowledge representation formalisms that represent knowledge about an application domain as a hierarchy of concepts and a description of the properties of the objects.   

- Concepts and roles
- Complex expression: C U D, LC, ∀x.C, 
- There are axioms and define terminology. C ⊆ D
- There are axioms to assert statement about the world. such as C or P(a,b) -> called Abox
- Semantics and Inference allows to calculate hierarchies and other important ontology requirements. 

## ALC: Syntax
The simplest description logic, small extention of propotional. 
- concepts: logic, class, types
- role name: propertyies 
ALC - > Concept name and relation names. Complex concept descriptons are built from atomic terms by means of constructors: 
* C | atomic Concept
* ⊤ | universal concepts | thing
* ⊥ | bottom concepts    | nothing
* ¬C| complement         | not
* C ⊓ D | intersection   | or
* C ⊔ D | union          | and 
* ∃r.C  | existenctial   | some
* ∀r.C  | universal      | only 

## Mathematical mean (interpretation)
- Interpretation of a concept (class, type) C. C<sup>I</sup> all individuals X that belongs to C 
Example: Human<sub>I</sub> = {paul, jane}. 
- Interpretation of a role(property). P<sup>I</sup> = all paris of individuals (X,Y) such that X has property P with as value Y. Example: Love<sup>I</sup> = {(paul, jane),(jane, yellow_car)}
- An interpretioan is a pair, I = (∆<sup>I<sup>, •<sup>I</sup>), where ∆<sup>I<sup> in a domain of individual (non-empty) and •<sup>I</sup> is an interpretation function. 
  - A<sup>I</sup> ⊆ ∆<sup>I<sup>: concept names to subjects of ∆<sup>I<sup>. 
