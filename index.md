## Milestones

#### Phrase I
 * ~~Modify the Eco Server Code, to create new "Factory Like" for purpose of modular.  In this case "IAIEngine", pull request purpose~~
 * ~~Create a new "Default AI Engine" that is the "Current Eco AI"~~

#### Phase II
 * ~~Implement Behavior Tree AI~~
 * Implement Base AI Sensory/Behavioral Component System
 * Implement Neural Network
 * Implement Base Universal Systematic Code Structure
 * Implement Base Personality Traits
 * Implement Base Food Chain
 
#### Phase III
 * New Behavior Tree Editor in Angular2
 * Neural Network Editor in Angular2
 * All XML to Compiled Code Compiler 
 * * Behavior Tree
 * * Neural Network 
 * * Personality Traits
 * * Food Chains 
 * Universal Systematic Code Editor (Config editor) in Angular2
 
#### Phase IV
* Create Sight Sensory Component 
* Create Smell Sensory Component
* Create Hearing Sensory Component
* Create Touch Sensory Component
* Create Taste Sensory Component
* Create Pain Sensory Component
* Create Balance / Acceleration Sensory Component
* Create Temperature Sensory Component
* Create Light Sensory Component
* Create Growth Behavior Component

#### Phase V
* Optimization Improvements
* Implementation of All Animals
* Implementation of All Trees
* Final Touchups

## Introduction

The concept is to combine a combination of a few AI techniques adapted that takes the best of each and builds a system that can be fully functional.  This is broken into three parts.  The techinques mostly used is behavioral tree AI

##### System Design

* Editing
* Compilation & Optimization
* Simulation

##### Techniques Adapted:
 * Behavioral Tree AI
 * Sensory/Behavioral System
 * Neural Network (Basic)
 * Universal Systematic AI
 * Personality Traits
 * Food Chain

## Techniques

### Behavioral Tree AI
This AI technique is used the most, and if your not entirely sure of how behavior tree AI works you should go to [AIGameDev](http://aigamedev.com/open/article/bt-overview/) and get some basic understanding of Behavior Tree AI and how it works.  It's simular to how Decision Making AI works, but much more complex and more logic friendly.  

How it is used in the designing of the AI system is that it will be utilitizing all of the decision making logics.  Each "tree" made up will be a specific logical choice that a specific creature or non-playable character (npc) can interact/function.  These are automatically grouped by the "Universal Systematic AI", which will be explained a little more below.


### Sensory/Behavioral Component System
This is not really an AI technique but it is a technique regardless.  The concept behind this is that it behaves as the input/output that can be translated into choices based on the creature/non-playable character (npc).  

Each NPC will have a central "Brain" that forms as a Neural Network and communicates between the different sensory parts of the NPC.  Yes this requires specification of where each sensory component must be assosicated with, and what sensory do they have.

Each component will be used to determine what the creature actually does.  This information is feed to the neural network which is considered part of the input/output of what a creature does, and these will determine the different 'behavioral' insights of what they should do.  Below will provide basic what it's input to the neural network provides.  Some will are obvious.

The following sensory components are listed below:
* Sight Sensory Component 
* Smell Sensory Component
* Hearing Sensory Component
* Touch Sensory Component
* Taste Sensory Component
* **Pain Sensory Component**: Provides input whether the NPC is hurt, harmed
* **Balance / Acceleration Sensory Component**: Provides input whether the NPC is balanced and if they are moving to fast or to slow
* **Temperature Sensory Component**: Provides input whether the NPC is cold, warm, hot and based on this input we can provide it instructions of what it should do when it is cold, warm or hot
* **Light Sensory Component**: Provides input whether the NPC likes to be in the dark, light, but not just the NPC but plants as well.  Are they getting enough sun light?  To much light?  All this input can provide expected output of what to do.
* **Gravity Sensory Component**: Provides input whether the NPC can feel the gravitiational pull.  Mostly great for avion animals, or if the NPC is out in space.  What should it do when it senses that it is loosing it's gravitational pull.  OR are they getting close to the ground?  What actions should it do this input is fed to provide expected output in what to do when gravity affects them.
* **Echolocation Sensory Component**:  Provides input for sonar based sensory.  These are great for like batlike creatures
* **Electroreception Sensory Component**:  Provides input for detecting electrical fields.  Species like sharks, fishes and rays all have abilities to sens changes in their eletric fields.  This information can provide input and expect output of what they should do.
* **Magnetoreception Sensory Component**:  Provides input for detecting magentic fields, this is used mostly in birds. 
* **Infrared Sensory Component**: Provides input for detecting heat, used mostly in snakes or reptiles.  So this would require body like tempature of Players giving heat.  Same with other NPC etc.

Keep in mind that not all of these sensory components would be implemented right away.  They would be as we need them.  But the nice thing is having these input broken into sensory components allow a concept of plug and play.  Add a new bird, attach all of their sensory components they need, and those inputs will automatically feed the neural network what it should do when specific inputs are met.  The outputs would determine a specific behavior that should be done when that output occurs.

The following behavioral components are listed below:
* **Growth Behavior Component**:  Provides Instructions on how an NPC should grow, this can be either for animals/plants etc.

Will add more behavioral components later

### Neural Network (Basic)
To keep it simple, the neural network behaves an interpreter on how to take the sensory components and translate it to specific output behaviors.  Not to be confused with "Machine Learning" as that is mostly what neural network is for.  But in this case we use it to determine specific correct behavioral output expected.

### Universal Systematic AI
This is a system that I have been expermenting over the years (since 2007).   This all theoretical and hopefully becomes useful.  To keep it as simple as possible, the theory is to be able to provide a data structure that acts like a DNA blueprint for a specific NPC.  

Each NPC would consist of a Universal Code (Header) that acts like the DNA of a NPC, along with a sub-header that is different depending on what the Systematic Code is.

#### Universal Code Header

* Version = 8 bits (1 byte)
* Identity Code = 64 bits (8 bytes) - an identity serial that represents this universal code, this would be the unique id of the creature in the world)
* Systematic Code = 8 bits (1 byte) - This determines what type of object the universal code is, such as organism, chemical substance, object, group
* [@see Systematic Header based on Systematic Code]

#### Systematic: Organism Genetic Code Header
Everything between "Domain Code" to "Sub-Species Code" can be explained by going to [Taxonomy_(biology)](https://en.wikipedia.org/wiki/Taxonomy_(biology)) page on wikipedia.  Having understanding of these classifications can better understand HOW specific creatures will behave etc.  Yes that means a bunch of different patterns can be different for each organism.

* Version = 8 bits (1 byte)
* Domain Code = 8 bits (1 byte)
* Kingdom Code = 8 bits (1 byte)
* Phylum Code = 8 bits (1 byte)
* Class Code = 16 bits (2 byte)
* Order Code = 16 bits (2 byte)
* Family Code = 16 bits (2 byte)
* Subfamily Code = 16 bits (2 byte)
* Genus Code = 16 bits (2 byte)
* Species Code = 16 bits (2 byte)
* Sub-Species Code = 16 bits (2 bytes)
* XX Chromosome Code (Identity) = 64 bits (8 bytes) [Father] - *The father's identity code*
* XY Chromosome Code (Identity) = 64 bits (8 bytes) [Mother] - *The mother's identity code*

#### Systematic: Neural Machine Code Header
*This is currently not part of the current phase plans, but this is included as it will eventually as a mod, unless you guys like the idea of having drones/droids for end-game stuff*

* Version = 8 bits (1 byte)
* Machine Code = 8 bits (1 byte) - *Machine Code represents the type of machine it is (mainframe, drone, droid)*
* Neural Network Code = 64 bits (8 bytes) - *Neural Network Code represents the parent of the code, such if it is a mainframe it has no code therefore 0, otherwise drone/droid will be linked to the mainframe's identtiy code*
* Neural Code = 8 bits (1 byte) - *Neural Code is simular to the DNA Code, the code basically the unique pattern of how the machine thinks, this gives each mainframe different types of personalities, these are simple bitflags of what the Machine can and cannot do*

***Note: The organism genetic code of each value is a unique representation based on an static list that would be managed of course as needed.  @see below: Taxonomy List below***


#### Taxonomy List
##### Domain Codes
```
None = 0
Archaea = 1
Bacteria = 2
Eukaryota = 3
```

##### Kingdom Codes
```
None = 0
Bacteria = 1
Protozoa = 2
Chromista = 3
Plantae = 4
Fungi = 5
Animalia = 6
```

This list below will adjust based on the creatures in ECO currently resides

##### Phylum Codes
```
None = 0
Chordata = 1
```

##### Class Codes
```
None = 0
Mammalia = 1
```

##### Order Codes
```
None = 0
Carnivora = 1
Artiodactyla = 2
```

##### Suborder Codes
```
None = 0
Caniformia = 1
Ruminantia = 2
```

##### Family Codes
```
None = 0
Canis = 1
Cervidae = 2
```

##### Subfamily Codes
```
None = 0
Cervinae = 1
```

##### Genus Codes
```
None = 0
Canidae = 1
Cervus = 2
```

##### Species Codes
```
None = 0
C_lupus = 1
C_canadensis = 2
```

##### Subspecies Codes
```
None = 0
C_l_labradorius = 1
```

##### Organism Codes of ECO (Wolf and Elk for now)

###### Wolf
```
Domain:			Eukaryota (3)
Kingdom:		Animalia (6)
Phylum:			Chordata (1)
Class:			Mammalia (1)
Order:			Carnivora (1)
Family:			Canidae (1)
Genus:			Canis (1)
Species:		C. lupus (1)
Subspecies:		C. l. labradorius (1)
```

###### Elk
```
Domain:			Eukaryota (3)
Kingdom:		Animalia (6)
Phylum:			Chordata (1)
Class:			Mammalia (1)
Order:			Ruminantia (2)
Family:			Cervidae (2)
Subfamily:		Cervinae (1)
Genus:			Cervus (2)
Species:		C. canadensis (2)
Subspecies:		None (0)
```

Based on these information we can create specific behavioral structure that would make up this pattern.

### Personality Traits
There would be specific personality traits that would form basic instructions of how a specific npc should behave.  Should I hunt?  Am I hunted?  Do I run from those who hunt me?  Am I fearless?  Do I like this?  Do I like that?  What I hate?  What is my favorite food?  Etc.  All of these will determine specific behavioral markups that would be simply injected into a specific systematic code.  

### Food Chain
Based on specific creatures we can categorize them in specific food chains, the concept of predator will be based on this.  Think of it this way.  Fox are often hunted by coyotes (not in ECO currently) but they will often kill them.  

So if a organism is higher in the food chain it can and will probably run away.  Now it also depends on the type of creature it is.  For example wolves are scared of humans in general, they wouldn't go after a human normally.   There is often whereas if your alone by yourself and the pack of wolves out pack you, they will and might go after you.  But ultimately this will be based on the personality of the individual wolf as well as a pack personality traits.

#### Example of the data above:
Wolves would consist the 5 primary senses,  their genetic systematic markup code signifies that they have heighten senses in sight, smell, hearing, taste and touch.  They would also contain senses in pain, temperature, balance/acceletration, and gravity senses.  Now how we would interprate that information is based on the Systematic Code of Wolf.

First of all we know that wolves are animals, and it's from the phylum of Chordata which means "with a cord", thus spine/backbone, some fishes are part of this phylum but not all of them.  It is part of the class "Mammalia" which to be blunt "Mammal" thus their youngs are given birth from the womb.  They are from the order of Carnivora, this order specification we can actually use to determine that this is a meat-eating organism.  This doesn't mean it has predatory insincts or anything.  The suborder Caniformia, means that the organism has a long snout, such as the wolf does have.  We can consider this "Long snout" concept as heighten sense of smell.  The Canidae specifics lineage of carnivorans that includes domestic dogs, wolves, foxes, jackals, dingoes, and many other extant and extinct dog-like mammals.  Where the Genus is Canis, containing multiple extant species, such as wolves, dogs and coyotes. Species of this genus are distinguished by their moderate to large size, their massive, well-developed skulls and dentition, long legs, and comparatively short ears and tails.

We can formulate a base personality traits for the wolf by the specific systematic code pattern.  For example.  With the Carnivora order we can know that we can include all personality traits that makes the creature effectively a meat eating organism.  Now it does not provide the specific instructions of how they should hunt, but it will give them the concept that they like meat.

With the species group we can determie what the type of food the "C. lupus" likes, well we know they like meat in general, but we also know that they would go after organisms that are lower in the food chain.  

## Editing

Behavioral tree works best with hierarchy specific like nodes.  So XML would be the best language that would allow editing behavior trees easily.  

Other configurations would work best with JSON


## Compilation and Optimization
The Behavioral tree would be compiled into auto-generated C# code using CodeDom which help provide optimziation.  

## Simulation
Compiled behavioral tree would simply be instructed by the simulation.  Each creature would have a set of referenced instructions in memory and only loads those actual conditions/actions as they come rather than loading all instructions into memory for each creature.  This allows not to load all behavioral instructions for each creature in the world.  Think of it this way, once the input/output pattern is found, it will then grab the behavioral instructions and process them, once done it will release it from memory.  However there is caching involved, so it will only release it after *n* amount of time.  So if a specific instruction is used multiple times within a call it will reuse it until it no longer needs to.



## Other Notes
The core system of the AI will be a factory like system for modular purposes.   This is mainly for the purpose of being able to switch/change AI engines for backwards compatability

**Last updated on 6/8/2017 @ 11:13AM PST**