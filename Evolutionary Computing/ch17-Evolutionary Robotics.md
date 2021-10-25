# Evolutionary Robotics

## Intro, Basics, various perspectives 
- active vs passive: active has agency, exhibits behaviour, living matter.
- agent: active/autonomous entities
- Operate in an environment 
- Evaluation and selection are based on what agents do 
- reproduction can be asynchronous 
- Controller: sensons -> actuator mapping 
- phenotype = neural network controller with fixed structure and evolvable connection weights 
- Genotype = vector of connection weights 
## Reality gap
- transferring the controller to hardware usually fails because of behaviour/performance is different and ttypically much worse 
## Noveltty search 
- Ignore the goal 
- encourage diverse behavour instead of best best behaviour 
## MAP elites
- Define behaviour characterisation with N dimentions 
- Transform behaviour space into discrete bins 
- A Lot of experiments MxN clubs in discretised space 
- Draw a behaviour - performance map 
- use this map to speed up search later 

## Evolving robots in real-time and real-space 
- Triangle of Life:1 Conception - birth (morphogenesis) -> 2 Delivery - Infancy (learning loop) -> Fertility (mature life) survive, mating, learning task execution. 
- EvoSphere: the world of robot evolution. 
- Phenotyeps are moduler robots, genotypes specify the arrangement, evolution of a population of genotypes selection and reproduction in pc, all robots are build on real world, fitness is measured in the real world
- Autonomous robot evolutions project: 2018 -2022: same genetic code, physical and digital 
- Wetware -evolution -> Software -> evolution -> Hardware (evolution of things in materio) 
