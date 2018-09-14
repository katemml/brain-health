# brain-health
NLP research on Alzheimer Disease

# Contents

### Chapter 0 --- Introduction 
### Chapter 1 --- Entity Type Annotation Instructions  
**1.1 Entity**  

**1.2 Nmod**  
1.2.1 Color  
1.2.2 Order  
1.2.3 Size  
1.2.4 Quantity  

**1.3 Predicates**  
1.3.1 Motion    

**1.4 Xmod**    
	          	 1.4.1 Certain  
	          	 1.4.2 Emphasis  
	          	 1.4.3 Fuzzy  
				 1.4.4 Case    
 

 
### Chapter 2 --- Entity Attribute Annotation Instructions  
2.1 Abstract  
2.2 Disfluency   
2.3 External  
2.4 Opinion   
2.5 Possessive  
2.6 Subset


### Chapter 3 --- Relation Annotation Instructions
**3.1 Core Argument**   
agent, theme, dative  
**3.2 Thematic Roles**  
3.2.1 ADV   
3.2.2 DIR  
3.2.3 LOC  
3.2.4 TMP  
3.2.5 CAU  
3.2.6 MNR  
3.2.7 PRP    
**3.3 Noun**   
attribute
**3.4 Disclosure**   
more



### Chapter 4 --- Special Case Handling.     


## Chapter 0 Introduction
 We let potential patients with Alzheimer’s disease depict a picture called ‘[circus procession](https://www.google.com/search?biw=1200&bih=1240&tbm=isch&sa=1&ei=I3mIW_f0DPKFggfS8KrYBQ&q=circus+procession&oq=circus+proces&gs_l=img.1.0.0j0i24k1.3044.9644.0.11188.14.12.0.2.2.0.49.404.12.12.0....0...1c.1.64.img..0.8.191....0.PZkd_14cnKA)’ and record their answers. The annotation of the transcripts creates a valuable corpus, which can be used as training data for natural language processing research on diagnosis of  the disease. In our annotation, a sentence is annotated to identify mentions of some real-world entities (things) and their types, and a relation between two. Named entity recognition and information extraction tasks are accomplished. The main tasks of this annotation are: entity type labeling, entity attribute labeling and relation labeling. Each aspect is discussed in detail below. 


## Chapter 1 Entity Type Annotation Instructions

### 1.1 Entity 
Entities are real life objects in the picture, commonly noun phrases. We omit articles in our annotation. Entities are classified into two general types---known and unknown. Known entities are things that constantly appear in each transcript. For example, elephants, clown and tricycle. 

### 1.2 Nmod
Modifiers are said to modify entities and can be removed without affecting the grammar of the sentence. Nmod is the class of adjective modifiers. Most common types of adjectives appeared are **Color / Order / Size / Quantity**.  
Examples of the ‘**Order**’ adjectives: first, the other, another….   
**Note**: sometimes compound nouns can function as modifier as well. Ex: a polka dot dress.    


### 1.3 Predicate
Predicate is the part of a sentence that tells what the subject does. We only annotate one word which is the verb. We omit the auxiliary verbs(am, is are). One type of predicates we pay special attention to is **Motion**. For motion verbs, this [paper](http://elies.rediris.es/elies11/cap61.htm ) is good reference. However, the most common ones in the texts are ‘march, ride, walk’.   
**Attention: We treat have/hold/dressed up as normal predicates.**  

### 1.4 Xmod
Xmod is the class of adverbial modifiers  
1.	Temporally related(modifiers of events): treasures are just lying around, **waiting to be found**    
2.	Intentional (modifiers of propositions):  
Probably, likely -> **fuzzy**    
Must -> **certain**.     
Very, clearly, really, definitely, absolutely -> **emphasis**    
3.	Focus-sensitive: only, even   
4.	Sentential (evaluative, attitudinal):fortunately, legally, frankly speaking, clauses beginning with given that, despite, except for or if. 
5. Case  



## Chapter 2 Entity Attribute Annotation Instruction   
We define the following attribute types : Abstract, Disfluency, External, Opinion, Possessive, Subset  

#### 2.1 Abstract
Commmonly appeared examples: something, one
#### 2.2 Disfluency
Fragments of words, interruptions, incomplete sentences, filters and discourse markers. 
#### 2.3 External
#### 2.4 Opinion
1. subjective adjectives (fancy, bored, beautiful, normal,etc)
2. descriptive clauses that contain the word "like" (dressed up in a human -> human is opinion, dressed up like a millionaire)
3. sentences with hint words at the front (In my experience, as far as i can see, it is obvious that, etc)  

#### 2.5 Possessive
Show ownership by adding an apostrophe, an 's' or both.
#### 2.6 Subset


## Chapter 3 Relation Annotation Instructions     
### 3.1 Core Argument
Entity – Predicate – Entity (- Entity)  
-Agent and Theme Relation  
Ex: the elephant has a hat  
~~~
R1   agent  Arg1:has Arg2:elephant	  
R2   theme  Arg1:has Arg2:hat	  
~~~
-Dative Relation  
refers to indirect object of a verb  
Ex: I gave him a book  
~~~
R1  agent  Arg1:gave Arg2:I  
R2  theme  Arg1:gave Arg2:book  
R3  dative  Arg1:I Arg2:him  
~~~

### 3.2 Thematic Roles
#### 3.2.1 (DIR)Directional
Directional relations show motion along some path. For example: step **forward**, walk **along** the river. 

#### 3.2.2 (LOC)Locative
Locative relations indicate where some action takes place. Both physical location and abstract locations are marked as locative. 

#### 3.2.3 (TMP)Temporal
Temporal words show when an action takes place. Also included in this category are adverbs of frequency: **always, often**, adverbs of duration: **for a year**. 


#### 3.2.4 (CAU)Causal
Causal adverbials specify the reason for an action. Canonical cause clauses start with 'because'. 
 
 
#### 3.2.5 (MNR)Manner
Manner relations indicate how an action is performed. For example: walk **together**, sing **beautifully**, ran **quickly**. 

#### 3.2.6 (PRP)Purpose  
Explains the motivation for some action. Clauses beginning with 'in order to' and 'so that' are common purpose clause.

#### 3.2.7 (ADV)Adverbial
Usually between Xmod and predicates. 

### 3.3 Noun   
Nmod- Entity  
-Attribute relation  
Nmod is **Attribute** of Entity    
Ex: little parade  
~~~
R1   attr   Arg1:parade Arg2:little  
~~~
**! We treat “with” as attributes**  
Ex: a clown with makeup. (Makeup is attr of clown)  





## Chapter 4 Special Cases
1. Treat compound nouns as a single entity  
Ex: Polka dot, Straw hat  
2. One is holding a fan or umbrella -> treat as two entities.   
3. We do not annotate anything that is not related to the picture.   



