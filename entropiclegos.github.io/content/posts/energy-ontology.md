+++
title = 'Everywhere Yet Nowhere: The Ontological Status of Energy'
date = 2025-06-20T18:37:18+06:00
draft = false
+++
# Energy is Everywhere. Or Is It?
We love energy. Our civilisation is built on energy. Each phase in the history of the human civilisation is marked by inventing some radically more efficient way to extract energy from some "stored form". From eating fruits and veggies storing energy obtained from the sun to burning the carcasses of them to smashing subatomic particles off of each other, we've certainly come a long way. We can extract energy "hidden" in even the remotest corner of the smallest conceivable energy storage - an atom. And with all this energy we power our homes, our offices, our factories, and most importantly, our electronic appliances, including the one we're reading/writing this post on. But *what exactly* is energy? 

## Energy: No-fluff Edition
I'll cut straight to the chase and give you the most rigorous definitions of energy in physics. This is how we define it in physics. Anything we call "energy" somehow or the other circles back to one of the following equivalent formulations.

### Version 1: FTC Energy
This formulation of energy, which I call *FTC energy*, is the very first formulation of energy that you encounter in your science education. What you exactly encountered first, of course, will vary; but all those are equivalent restatements of the same definition, which is really derived from the **fundamental theorem of calculus**, or more specifically, **the fundamental theorem of line integrals**. Here's the definition.

> **Energy is a quantity conserved during motion under a conservative force field (i.e. one that is the gradient of a scalar field), in accordance with the fundamental theorem of line integrals.**

Here's how we express this mathematically:

$$
\boxed{
\forall \mathbf{F} \in \R^3: \mathbf{F} = \nabla\phi \implies \exists E \in \R: E = K_\mathbf{r} + U (\mathbf{r}), \forall \mathbf{r} \in \R^3
}\\ ,\newline
\text{ }\newline
\boxed{
\text{U}(\mathbf{a}) - \text{U}(\mathbf{b}) \equiv \int_\mathbf{C} \mathbf{F}\cdot\mathbf{dr} \equiv K_\mathbf{b} - K_\mathbf{a}}\text{ ; where}\newline 
\text{ } \newline
\newline \forall \mathbf{a}, \mathbf{b} \in \R^3\\ ; \newline \mathbf{C}: \R \rightarrow \R^3\\ ; \newline \mathbf{C}(0) = \mathbf{a}, \mathbf{C}(1) = \mathbf{b}\\ ; \newline
\text{U}: \R^3 \rightarrow \R
$$

### Version 2: Noetherian Energy
This is a version that is a slightly more advanced but also more general restatement of the definition, that expands the FTC definition to apply to even where traditional concepts of force are no longer meaningful, e.g. in quantum mechanics (QM). It is a special case of Noether's theorem, which says that:

> **For each (continuous) symmetry of the Lagrangian, there is a conserved quantity.**

Noether's theorem, for me, is *one of the most beautiful* theorems in all of physics. For example, if a system's Lagrangian is space-translationally invariant, i.e. moving the system around in space doesn't change the behaviour, then the system conserves a quantity we call linear momentum. If it is rotationally symmetric, then it conserves a quantity we call the angular momentum. And, most importantly for our purposes,

$$
\boxed{
\begin{align*}
\text{\textbf{E}}
&\text{\textbf{nergy} is the \textbf{conserved quantity associated with}}\newline
&\text{\textbf{time-translational invariance} of the Lagrangian.}
\end{align*}
}
$$
