# brain-health
NLP research on Alzheimer Disease

# Contents

### Chapter 0 --- Introduction 
### Chapter 1 --- Entity Type Annotation Instructions  
**1.1 Mention**  

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
2.3 Opinion   
2.4 Possessive  
2.5 Subset


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
**3.4 Discourse**   
more



### Chapter 4 --- Special Case Handling.     


## Chapter 0 Introduction
 We let potential patients with Alzheimer’s disease depict a picture called ‘[circus procession](https://www.google.com/search?biw=1200&bih=1240&tbm=isch&sa=1&ei=I3mIW_f0DPKFggfS8KrYBQ&q=circus+procession&oq=circus+proces&gs_l=img.1.0.0j0i24k1.3044.9644.0.11188.14.12.0.2.2.0.49.404.12.12.0....0...1c.1.64.img..0.8.191....0.PZkd_14cnKA)’ and record their answers. The annotation of the transcripts creates a valuable corpus, which can be used as training data for natural language processing research on diagnosis of  the disease. In our annotation, a sentence is annotated to identify mentions of some real-world entities (things) and their types, and a relation between two. Named entity recognition and information extraction tasks are accomplished. The main tasks of this annotation are: entity type labeling, entity attribute labeling and relation labeling. Each aspect is discussed in detail below. 


## Chapter 1 Entity Type Annotation Instructions

### 1.1 Mention 
Mentions are real life objects appeared in the picture, commonly noun phrases. We omit articles in our annotation. Mentions are classified into two general types---known and unknown. Known mentions are things that constantly appear in each transcript.   
Here is the list of known mentions:   

* copyright 
* picture 
* title  
* clown.   
* elephant_l  
* elephant_r    
* man_l   
* man_m    
* man_r    
* men   
* cane    
* fan      
* flag   
* tricycle     


Example for unknown mentions: 
```
necktie, stripe, umbrella    
```
If the mention in the text refer to the same thing in the known mentions list above, we annotate them as known mention. 
Ex:
```
minstrels, soldiers > men
bicycle > tricycle
```

Note, coreference occurs when two or more expressions in the text refer to the same person or thing.  See 3.3.2 Coreference relation. 
Example: 
```
hats with feathers on them 
> Here 'hats' and 'them' are coreferenced. 
```   
Nouns like 'background, lefthand side, front' are not considered as mentions. 


### 1.2 Nmod
Modifiers are said to modify entities and can be removed without affecting the grammar of the sentence. Most common types of Nmods appeared are **Color / Order / Size / Quantity**.  

Examples of the ‘**Order**’ adjectives:   
```
the first man, the other elephant
> Here 'first' and 'other' are 'Order' Nmods.      
```

- Besides numbers, some descriptive phrases can also be '**Quantity**' modifiers.
```
a bouquet of flowers.
> 'a bouquet of' is 'Quantity' Nmods.
```

- Sometimes compound nouns can function as modifier as well.  
Ex:  
```
 a polka dot dress    
 > Here 'polka dot' is Nmod.
``` 
- Other examples of Nmod
```
striped pant, a variety of characters, diamond shape pattern, side leg
> Here 'striped', 'a variety of', 'diamond shape', 'side' are Nmods.
```

### 1.3 Predicate
Predicate is the part of a sentence that tells what the subject does. We only annotate one word which is usually the verb. We omit the auxiliary verbs(am, is are). One type of predicates we pay special attention to is **Motion**. For motion verbs, this [paper](http://elies.rediris.es/elies11/cap61.htm ) is good reference.  
Examples of motion predicates:
```
march, ride, walk, go, wave, peddle, operate, drive, follow, dance
``` 
Examples of normal predicates:  
```
have, hold, carry, dressed up, stand 
```

### 1.4 Xmod
Xmod is the class of any other types of modifiers including adverbials. 

1.	Intentional (modifiers of propositions): 

 **- Fuzzy**:    
```
  probably, likely, it could be
```  
   **- Certain**:  
```
  must
```    
   **- Emphasis** :  
```
  very, clearly, really, definitely, absolutely, pretty
```   
2.	Focus-sensitive: 
```
only, even  
``` 
3.	Sentential (evaluative, attitudinal):
``` 
fortunately, legally, frankly speaking, clauses beginning with given that, despite, except for or if. 
```
4. Case  
Prepositions that have thematic role. 
```
walk on two legs, have a hat on, a tail coming out 
> Here 'on' and 'out' are Cases.
```

Other examples of Xmod:   
```
in the background, on the lefthand side, in front, at the back
```


## Chapter 2 Entity Attribute Annotation Instruction   
We define the following attribute types : Abstract, Disfluency, External, Opinion, Possessive, Subset  

#### 2.1 Abstract
```
something, one
```
- If we got information about this abstract mention from its context, for example
```
One elephant is riding the tricycle and the other one is walking behind him.
> Here 'one' is annotated as the known mention 'Elephant_R', with attribute 'abstract'.
```

If we don't get any information about the mention from the context, for example
```
The clown is holding something in the hand.
> Here 'something' is annotated as an unknown mention.
```

- Colors can also have abstract attribute when it refers to the clothes, for instance
```
the elephant with blue on
> Here 'blue' has attribute 'Abstract'. 
```


#### 2.2 Disfluency
Fragments of words, interruptions, incomplete sentences, filters and discourse markers. 
```
...and both of them, one of them got stripes and has a necktie on
> 'both of them' is disfluency.

One clown is carrying a flag or maybe two flags...
> the front 'flag' is disfluency. 
```

Words like 'Um','ah','like' are not considered as disfluency. Only the meaningful mentions are considered.


#### 2.3 Opinion
1. subjective adjectives or nouns

Examples of adjectives: 
```
fancy, bored, beautiful, normal looking, different
```
Examples of nouns:
```
the baby elephant, the father elephant
> Here 'baby' and 'father' are 'Opinion' Nmods.
```
2. descriptive clauses that contain the word "like" 
```
dressed up in a human, dressed up like a millionaire
> Here human (millionaire) is opinion.
```

3. sentences with hint words at the front 
```
In my experience, as far as i can see, it is obvious that
```

#### 2.4 Possessive
Show ownership by adding an apostrophe, an 's' or both.
```
The left elephant wears a beanie on his head.
> Here 'his' is annotated as the known mention 'Elephant_L' and has attribute 'possesive'.
```
#### 2.5 Subset
```
one of them
```


## Chapter 3 Relation Annotation Instructions     
### 3.1 Core Argument
Entity – Predicate – Mention (- Mention)  
-Agent and Theme Relation  
Ex: I see the elephant riding a bike.      
<img src="https://user-images.githubusercontent.com/35633621/46171353-484d0b80-c26e-11e8-8b1b-cb423b27e5a5.png" alt="alt text" width="260" height="40">

-Dative Relation  
refers to indirect object of a verb  
Ex: I gave him a book.   
<img src=https://user-images.githubusercontent.com/35633621/46169532-69f7c400-c269-11e8-9c18-744c7ab2f542.png alt="alt text" width="260" height="50">

* Handling sentences in passive voice.      
Ex: The photo was taken in early 1900s.   
<img src=https://user-images.githubusercontent.com/35633621/46169510-5c423e80-c269-11e8-9578-30d21bdb944e.png alt="alt text" width="260" height="50">




### 3.2 Thematic Roles
#### 3.2.1 (DIR)Directional
Directional relations show motion along some path. 

#### 3.2.2 (LOC)Locative
Locative relations indicate where some action takes place. Both physical location and abstract locations are marked as locative. 

#### 3.2.3 (TMP)Temporal
Temporal words show when an action takes place. Also included in this category are adverbs of frequency: **always, often**, adverbs of duration: **for a year**. 


#### 3.2.4 (CAU)Causal
Causal adverbials specify the reason for an action. Canonical cause clauses start with 'because'. 
 
 
#### 3.2.5 (MNR)Manner
Manner relations indicate how an action is performed. 
#### 3.2.6 (PRP)Purpose  
Explains the motivation for some action. Clauses beginning with 'in order to' and 'so that' are common purpose clause.

#### 3.2.7 (ADV)Adverbial
Usually between Xmod and predicates. 

Examples in this section:  
<img src=https://user-images.githubusercontent.com/35633621/46171112-9dd4e880-c26d-11e8-8df8-8419ead136e9.png alt="alt text" width="330" height="480">

### 3.3 Noun   
Nmod- Mention  
#### 3.3.1 'Attribute' relation  
Nmod is **Attribute** of Entity    
Ex: two women    

**! We treat “with” as attributes**  

Examples in this section:  
<img src=https://user-images.githubusercontent.com/35633621/46169517-5fd5c580-c269-11e8-98fd-dd576a118be6.png alt="alt text" width="320" height="90">


#### 3.3.2 'Coreference' relation
Coreference occurs between several mentions when they all refer to the same object. 
Example:
<img src=https://user-images.githubusercontent.com/35633621/46169841-2a7da780-c26a-11e8-9998-63f2931736b4.png alt="alt text" width="300" height="48">   


### 3.4 Discourse
Mention - Mention
#### 'More' relation
We say there is a 'more' relation when a mention repeatly occurs in one sentence, usually adding more information to the mention.  
Example:  
<img src=https://user-images.githubusercontent.com/35633621/46172663-1047c780-c272-11e8-8ffa-0ca3f5787e02.png alt="alt text" width="330" height="48">




## Chapter 4 Special Cases Handling
- Treat compound nouns as a single mention  
    ```
    polka dot, straw hat, face makeup 
    ```
  
- We do not annotate anything that is not related to the picture.     
- When a sentence appears as imcomplete, we only annotate the 'Mention' in the sentence. 
- Way of handling relative clauses, adverbial clauses:  
	We diregard the connection words (which, that), treat the clause as a separate sentence with the same object, and annotate the relations as usual. 
	```
	I was standing there, waiting for the bus. 
<img src=https://user-images.githubusercontent.com/35633621/46362753-21605200-c63f-11e8-896e-a5807ca5286c.png alt="alt text" width="260" height="50">	```


- Diregard anything after 'I don't know..', 'I cannot describe...'

- Annotations can be made across multiple sentences.
For example:
```
The clown is in the center of the picture. Looks both agitated and bored at the same time.
> 'agitated' and 'bored' in the second sentence are attributes of the 'clown' in the first sentence.
```

- When phrases like 'it says...' appear, we annotate them as LOC relation. For example:
```
The sign says circus procession.
> 'sign' is location of 'circus procession'
```

