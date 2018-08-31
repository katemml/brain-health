# brain-health
NLP research on Alzheimer Disease

# Contents

### Chapter 0 --- Introduction 
### Chapter 1 --- Entity Type Annotation Instructions  
**1.1 Entity**  
**1.2 Case**   
**1.3 Clause**     
**1.4 Adverbial**    
	          	         1.4.1 Certain  
	          	         1.4.2 Emphasis  
	          	         1.4.3 Fuzzy   
**1.5 Nmod**  
1.5.1 Color  
1.5.2 Order  
1.5.3 Size  
1.5.4 Quantity    
**1.6 Predicates**  
1.6.1 Motion  
1.6.2 State  
**1.7 Thematic**  
1.7.1 Directional  
1.7.2 Locative  
1.7.3 Temporal   
1.7.4 Causal  
1.7.5 Manner    


### Chapter 2 --- Entity Attribute Annotation Instructions  
2.1 Abstract  
2.2 Disfluency   
2.3 External  
2.4 Opinion   
2.5 Possessive  
2.6 Subset


### Chapter 3 --- Relation Annotation Instructions

3.1 Attribute relation.   
3.2 Agent and Theme Relation.   
3.3 Adverbial Relation.   



### Chapter 4 --- Special Case Handle.     


## Chapter 0 Introduction
 We let potential patients with Alzheimer’s disease depict a picture called ‘[circus procession](https://www.google.com/search?biw=1200&bih=1240&tbm=isch&sa=1&ei=I3mIW_f0DPKFggfS8KrYBQ&q=circus+procession&oq=circus+proces&gs_l=img.1.0.0j0i24k1.3044.9644.0.11188.14.12.0.2.2.0.49.404.12.12.0....0...1c.1.64.img..0.8.191....0.PZkd_14cnKA)’ and record their answers. The annotation of the transcripts creates a valuable corpus, which can be used as training data for natural language processing research on diagnosis of  the disease. In our annotation, a sentence is annotated to identify mentions of some real-world entities (things) and their types, and a relation between two. Named entity recognition and information extraction tasks are accomplished. The main tasks of this annotation are: entity type labeling, entity attribute labeling and relation labeling. Each aspect is discussed in detail below. 


## Chapter 1 Entity Type Annotation Instructions

### 1.1-1.3 Entity & Clause
Entities are classified into two general types---known and unknown. Known entities are things that constantly appear in each transcript. For example, elephants, clown and tricycle. A clause is an entity with modifier as a phrase around it. For example, a person who…

### 1.4 Adverbial
Before assuming a modifier is merely adverbial, we first decide if the adverb belongs to any thematic type listed. (See 1.7). Adverbial elements are often:   
1.	Temporally related(modifiers of events): treasures are just lying around, **waiting to be found**    
2.	Intentional (modifiers of propositions):  
Probably, likely -> **fuzzy**    
Must -> **certain**.     
Very, clearly, really, definitely, absolutely -> **emphasis**    
3.	Focus-sensitive: only, even   
4.	Sentential (evaluative, attitudinal):fortunately, legally, frankly speaking, clauses beginning with given that, despite, except for or if. 

### 1.5 Nmod
Modifiers are said to modify entities and can be removed without affecting the grammar of the sentence. Because we already have the entity type ‘adverbial’, we primarily focus on adjectives. Most common types of adjectives appeared are **Color / Order / Size / Quantity**.  
Examples of the ‘**Order**’ adjectives: first, the other, another….   
**Note**: sometimes compound nouns can function as modifier as well. Ex: a polka dot dress.   


### 1.6 Predicate
The two types of predicates we pay special attention to are **Motion** and **State** predicates. For motion verbs, this [paper](http://elies.rediris.es/elies11/cap61.htm ) is good reference. However, the most common ones in the texts are ‘march, ride, walk’. And [here](https://www.gingersoftware.com/content/grammar-rules/verbs/stative-verbs/) is a list of state verbs.   
**Attention: We treat have/hold/dressed up as normal predicates.**

### 1.7 Thematic
####1.7.1 Directional
Directional modifiers show motion along some path. For example: step **forward**, walk **along** the river. 

#### 1.7.2 Locative
Locative modifiers indicate where some action takes place. Both physical location and abstract locations are marked as locative. 

#### 1.7.3 Temporal
Temporal words show when an action takes place. Also included in this category are adverbs of frequency: **always, often**, adverbs of duration: **for a year**. 


#### 1.7.4 Causal
Causal adverbials specify the reason for an action. 
 
 
#### 1.7.5 Manner
Manner modifiers indicate how an action is performed. For example: walk **together**, sing **beautifully**, ran **quickly**. 








