+++
title = 'Absistence and Other Metaphysical Quandaries'
date = 2025-06-24T23:19:55+06:00
draft = false
tags = ['Metaphysics', 'Philosophy of language']
+++
# How Can Nonexistent Objects "Be"?
I discussed in a previous post the view of Meinong on levels of ontological being. Meinong's idea drew much ridicule at his time ("Meinong's jungle"), but I think Meinong's framework is a very valid approach for doing philosophy especially in "ordinary language", rather than in the strict formalism mathematics and logic, in which such "objects" are immediately dismissed. In what follows I'll put forth my framework to elucidate some of the confusing issues on this front.

## Language As Function Composition
In a post several months ago, I said that I was working on a *"concept-space" framework* for unifying a lot of philosophical problems and trivialising their solutions. This will be one of the first applications of the framework to solve such a problem. Firstly, what is the *concept space*? For the scope of the post, I'll keep the mathematical formalisms to a bare minimum only adding them to the extent that they aid comprehension.

### Introducing the Concept Space 
Very loosely speaking, I'd define it as the *set of all "possible" states of affairs*.What I exactly mean by any of that hasn't been fully fleshed out to the extent I'd like, and at any rate isn't relevant for the matter at hand. I think only an intuitive grasp of the idea will suffice to get the point across for the moment. It will be very hand-wavy, but I think that can be excused for the moment before we get a feel for the framework.

### What Are Words?
Words in our languages, when spoken or written, are *filtering functions*: they take the entire concept space as their input, and their output is a subset of that space (which may be the entire space or an empty set or anything in between - i.e. not necessarily a proper subset). For example: the word "apple" takes in the entirety of the concept space and gives out only those states of affairs that have some resemblance or in some way "include" the concept of an apple (e.g. an apple tree, a man eating two apples, an apple a day keeps the doctor away, Sir Isaac Newton getting bombarded with intergalactic apples etc).

### What About Negations?
What about negating existing words to create new words, such as "non-apple"? What does that do?

Negations give a very clear image in this framework: it's merely the complement of the filtering done by the original word. For example, if "apple" selects the subset $A$ of the concept space $\mathcal{S}$, then "non-apple" selects the subset $B = \mathcal{S} \setminus A$. Note that $A \cap B = \empty$ i.e. $A$ and $B$ are disjoint, and so applying the two "filters" in succession selects no state-of-affairs.

### If Words Are Filters, What Are (Basic) Sentences?
Bigger filters. That's it. There's nothing fancy here. It's just good-ol' function composition. Depending on the grammar of the language being spoken, the sequence of composition might vary (and it may also turn out in some cases to be commutative, but as I said, going into the details of the framework isn't the goal here), but whatever it is, it's one big fat filter made out of tiny little function compositions. 

For example, "an apple" takes the subset filtered out by the function "apple", which you may recall included a state-of-affairs where Sir Isaac is being bombarded with extraterrestrial beings throwing countless apples at him. The application of the "apple" filter is followed, of course, by an application of the "an" filter, which unfortunately eliminates the state-of-affairs where aliens are showering Newton with apples, allowing now only such states-of-affairs where at most one apple is involved. "Colourless green ideas sleep furiously" is also a filter, and so is a "squared circle".The latter, however, selects just the empty subset of the concept-space. Anything that selects an empty subset is meaningless - i.e. doesn't refer.

I won't touch upon the concept of "composite" sentences here, but it's relatively straightforward to implement "AND" and "OR" operations under this framework, and that


## Meinong's Levels of Being Rephrased
Armed with the framework, we're now perfectly equipped to transform Meinong's jungle into Meinong's civilisation. 

1. **Absistence**: the class of objects that Meinong terms as "absisting" are the ones that are described by empty filters, i.e. function compositions that end up selecting the empty subset of the concept space. In other words, they're basically the same as *nothing* at all.
2. **Subsistence**: these are non-empty filters that have no mapping from concept-space to real-space or vice versa.
3. **Existence**: these are non-empty filters that have a mapping from concept-space to real-space or vice versa.

### In Action: 1. Can God Make a Squared Circle?
To answer this we've got to first find out the meaning of "squared circle" with the recipe we've chalked out above. Unfortunately, circle selects a subset of the concept space that has an empty intersection with the filter "squared". So "Can God make a squared circle" translates to "can God make nothing?" He can of course, but so can everybody else. 

### In Action: 2. Can (An Omnipotent) God Make A Rock So Heavy That He Can't Lift It?
Let's break it down into the following steps of filtering. Each step composes a new function, and the newest composed function will be written in boldface.

1. *Rock*: select all instances from the concept space that have a non-zero inner product with the vector representing a rock.
2. ***Heavy** Rock*: filter the preceding subset to keep only "heavy" rocks. How heavy? It seems that completing this filter requires more information, but as a rule of thumb we can probably agree that more or less everyone would say that anything below 5 kilos would be light.
3. *Heavy Rock **Created By God***: For the theist, this filter is basically the identity function - all rocks, heavy or not, were created by God. For the atheist, within the context of the question, he must too concede that this is the identity "filter".
4. *Heavy Rock Created By God **That He Cannot Lift***: Here lies the crux of the issue. For anything to which the concept of "lifting" applies (i.e. "concrete"/existent objects), the omnipotent God can lift it. For anything to which it doesn't, it's meaningless to ask about lifting, since the resulting filter outputs a big fat nothing. So *that He cannot lift* is a filter that selects only the **subsistent/abstract** objects. Since *heavy rocks created by God* are all concrete/existent rather than abstract/subsistent, the final filter returns an empty set. 
