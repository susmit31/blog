+++
title = 'Lie, Exterior, Covariant and All That: Differential Geometry Redux'
date = 2026-06-11T20:47:48+06:00
draft = false
tags = ['maths','differential topology', 'differential geometry', 'yang-mills', 'general relativity']
+++
## TL; DR
> "Definitions are not made in a vacuum, they have a historical context and reason, often being made in response to some mathematical or scientific problem, or because someone sees a clever way of generalizing earlier results...inextricably linked to the reasoning used in theorems; often alternate definitions are tried and dropped when it is realized that they don’t have quite the right properties" - *Michael Nielsen*.

The quote above by the prominent quantum physicist Michael Nielsen captures well my frustration about much of advanced mathematical books / lectures. Differential geometry is hard. Some people make it even harder by throwing a bunch of abstract yet precise definitions that in the end magically gives us what we want. In the spirit of some of my previous posts, I try to give a mathematically accurate yet conceptual tour of the subject that would better elucidate your formal studies of the subject. The unifying question we'll try to answer is one that kept bugging me no matter how many times I came back to studying DG - why do we have so many *different concepts of differentiation of the same fields* in differential geometry? We'll see that in trying to answer this, we'll have shed light on much of the landscape of differential geometry. When you're done with this, I hope you'll better appreciate the esoteric axiomatic treatments. (P.S.: The title of the post is a gentle hat-tipping to one of my favourite vector calc books when I was younger called *Div, Grad, Curl and All That* by Schey.) 

## Prerequisites
The most important prerequisite is *NOT being a mathematician*. 

That said, I'd add a disclaimer before the rest of the prereqs - this is *not* a differential geometry primer. I give an intuitive yet mostly mathematically correct view of the mathematical landscape of DG, but you'll be able to get the most of it *only if* you come in familiar enough with the specific ideas. What do I mean by "familiar enough"? That is, you should have at least at some point in your life seen the exact definitions and formulas I'm talking about, because I'm too lazy to write them down in LaTeX. And I also hope you have seen a little bit of graph theory. Rather than laying out the rest of the prereqs, I *leave it as an exercise* for you to figure out whether you have the prereqs through the following litmus test.

**Litmus test**: What do we mean by a topological manifold? What additional structures do we need to equip a set with to call it a manifold? What is a diffeomorphism? What is the rank of the Riemann tensor? What sorts of objects (and how many of them) do you need to put into it to get a number? What are the natural objects over which integration on manifolds can be defined? Why does the Lie bracket tell you whether two vector fields can form a coordinate grid?

You don't need to know the answers off the top of your head, but if you can look it up and it makes sense, then you're ready for the ride ahead. I'll probably give a bird's eye view of each of these anyway, but with the heads up out of our way, we now dive right in.

## Smooth Manifold = Dough
Let's start with a set (of points). We'll call them "vertices" for the time being, for reasons that will become clearer in a moment. What is a topology on this set? It is a collection of "open sets", i.e. a declaration of which points are neighbours to which points. So this collection of open sets gives us a relation with which we can join two vertices if they are related under this relation. By joining up vertices that belong to the same open subsets of the original set, we've now transformed our original set of points into an unweighted, directed *graph* (in the sense of graph theory, as in *connected graphs*, for example). Because it's unweighted, and because it's a graph, it doesn't really matter at what angles the edges are drawn, or what their lengths are. In other words, it has *unbounded malleability*, in a way. So we'll take an extremely malleable object as our *prototypical topological space - a dough*. So remember,

$$
\text{Topological space = set + neighbourhoods = dough}
$$

This becomes a *topological manifold* when one can come up with an *atlas with continuous and bijective charts*. Now the chart transition maps, maps that tell us how to go from one chart to another when we have an overlap, are maps from a Euclidean space to another Euclidean space, and so we can do (potentially multivariable) calculus on them plain and simple. When these chart transition maps are also *smooth*, i.e. infinitely differentiable, we have a *smooth (topological) manifold*. Now our dough naturally looks smooth, and as an exercise you can make some dough and come up with an atlas for it if you're feeling adventurous. Let's call it Mr. Dough, with a big-D, to differentiate with the dough that we called a topological space. So

$$
\text{Smooth manifold = topological space + smooth transition maps = Mr. Dough}
$$

So Mr. Dough is what mathematicians would call a smooth manifold.

## Mr. Dough Is A Symbol
So you already know that Mr Dough is like the Bat-Man - it's meant to be a symbol. It's no specific dough. All smooth doughs connected by a diffeomorphism are Mr Dough. In other words, you can bend, twist, grow and shrink Mr Dough any way you please, as long as you do it smoothly. Mathematicians would call this *diffeomorphism invariance*. Mr Dough is thus a symbol of diffeomorphism invariance. Or, more poetically, Mr Dough is a symbol of boundless malleability. This boundless malleability means two things:

1. There's no concept of distance between points. Any (nonzero) distance is just as good as any other (nonzero) distance, by virtue of being smooth. If there's no particular concept of distance, there's also no particular way of measuring angles, since you can grow and shrink the angle as you please while preserving diffeomorphism invariance.
2. There's no concept of parallelism. This I'll expand on a little later.

## Smack That (Bundle)
Now assign your quantity of interest to each point on Mr Dough. This is a field. Depending on what you assigned, you may have a scalar, vector, tensor or a spinor field, or something even more exotic. But in general, they'll belong to some vector space, and this results in what's called a *vector bundle*. In physics-land, they're just better called fields, so I will call them fields from now on. To go back to the question we started with, how do we differentiate such structures defined on Mr Dough and how do all our familiar notions of differentiation (specifically, Lie, exterior, and covariant) correspond to such differentiating?

## What IS Differentiation?
Basically we take a look at the fields at very closely separated points and take the difference between them. Here's the problem - in this dough, there's no exact notion of "very closely separated" - we'd need a metric for that. A bare manifold has the notion of closeness built-in, yes, but it's only qualitative. You can replace this "very closely separated" with a oft-dreaded epsilon-delta definition if you wish to, doesn't change a thing - I can just blow up the epsilons and deltas without changing Mr Dough. 

This is a general problem while defining operations on a smooth manifold. We must define it in a way that respects diffeomorphism invariance. So as we do our bendings and twistings and growings and shrinkings, these operations should not change what they spit out. In absence of a metric, the plain old "take two infinitesimally separated points and take the difference between the fields defined in these two" recipe fails. So we need a way to come up with a specific notion of "closely separated" in the absence of a metric. 

There's yet another deeper issue. The problem of comparing vectors from different vector spaces. How do we know how which vectors defined at two different tangent spaces correspond to each other? How do we take the difference between the field values at two closely separated points, once we have settled on a notion of "close separation"?

How do we solve these issues? How do we define a derivative that survives the malleability of Mr Dough?

## (Para-)Metrising without (Really) Metrising
There's one very simple recipe if we have a bare smooth manifold to take differences between closely separated points. We just draw a bunch of integral curves, assign some parametrisation to them, and that allows us to define "closely separated" operationally as two points lying on the same integral curve separated by an infinitesimal parameter distance. As long as we don't have a metric, there's no specific preferred integral curves or parametrisation of choice, so there's no specific notion of closely separated. This is the stage on which Lie derivatives operate. 

With the parametrising integral curves projected on Mr Dough, we can define a *flow* generated by these integral curves. They *guide* our differentiation project in its entirety. Firstly, they give us a canonical and quantitative notion of closeness. Remember the second problem we had in the last section - we have no out-of-the-box way of telling how two vectors taken out of two different tangent spaces of Mr Dough are the same. This flow gives us a way. We simply draw the integral curves of the vector field we're looking to differentiate, and drag the points on the curve along the parametrising integral curves for an infinitesimal parameter distance. This *Lie dragged* vector field gives us the second piece of the puzzle - sameness across tangent spaces.

## Not Gonna Lie: How to Lie
So how do we take the Lie derivative of a vector field $v$?

1. **What we need**: An auxiliary vector field $u$, that parametrises the manifold.
2. **What we do**: Let $v$ flow infinitesimally along the integral curves of $u$ to generate a Lie-dragged version of $v$. Take the difference between the Lie-dragged field and $v$ at the point of interest. That is the derivative of $v$ along the flow lines of $u$, $\mathcal{L}_u v$.
3. **What we get**: A *directional* derivative

Note that Mr Dough is still that cute-as-a-button, malleable-as-hell piece of gooey deliciousness that we had before. We haven't hardened him up, we haven't made a cookie out of him. We can choose the parametrising field as per our need and redo the whole shtick and "malleably differentiate". It's our same old smooth manifold without any additional structure. This is why, strictly speaking, Lie derivatives belong to differential *topology*, rather than differential *geometry*, since we don't need any metric.

But we do need to bring in that auxiliary parametrising field, one that sets up sign posts on the manifold and defines a direction of differentiation.

What if we don't want to bring that in? Can we still differentiate? (Playing "*Tony Stark was able to build this IN A CAVE! With a box of SCRAPS!*" in my head rn lol)

## Differentiating on a Manifold, "In a Cave, With a Box of Scraps" - The Exterior Derivative
This is like the Mark-I Iron Man suit - not the most aesthetically pleasing, but it gets the bare minimum job done best utilising what it has. I assume you already know about forms and Stokes' theorem. If you do, you also know how the exterior derivative is defined. Most likely you're saying either "it's the only operation definable on forms that preserves antisymmetry and the Leibniz rule" or "it's just taking an antisymmetric componentwise partial derivative". They would be correct computationally, but they completely bypass the proper geometric picture it tries to convey.

The right picture to have in mind is in terms of Stokes' theorem. The exterior derivative tells us to look around the point in question, and sum up the values of the field on the faces of an infinitesimal parallelepiped around that point. Dividing by the volume of the parallelepiped, we get a notion of how the field is changing around the point in question. Recall that our familiar operations from vector calculus of gradient, divergence, and curl all either directly or through Hodge duality are manifestations of exterior differentiation. The gradient is, in fact, a case where both the Lie derivative and the exterior derivative answer the exact same question, and so there's no surprise that the gradient of a scalar field evaluated at some vector field is the same as its Lie derivative along that field. Divergence captures a notion of diverging from (or converging to) the point in question, while curl captures a notion of rotation around the point in question. While the exact amount of diverging or rotating would change with diffeomorphisms, the fact that a field diverges (or converges) or rotates (or not) doesn't change with such transformations. As you can see, the exterior derivative captures diffeomorphism-invariant properties of change of the field by taking a 360-degree view around the point.

So in summary, for exterior differentiation:

1. **What we need**: A bare smooth manifold. Plug-and-play, no setup required.
2. **What we do**: Computationally the most straightforward way is taking an antisymmetric componentwise partial derivative. 
3. **What we get**: A 360-degree sum-up of how things are changing around any point on the manifold.

After the dust settles, we'll still have our same old Mr Dough. Thus the exterior derivative, like its Lie cousin, is also a tool from the realm of differential topology.

What if we don't want a 360-degree overview? What if we want to look at a specific direction and say "how much does my field change if I move by some amount in different directions?"

Well, the exterior derivative no longer fits the bill, for obvious reasons, since it takes a panoramic view. Neither does Lie, because we'd need different parametrising fields to look at different directions, and even then, there's no correspondence between the parameter distances of two separate parametrisations. It turns out that there's simply no way out for Mr Dough here. He must toughen up.

## Putting the Dough in the Oven
Once again, eyes on the prize - what are we looking to answer right now? We want to take any field defined on the manifold, go to any point on the manifold, and then differentiate the field in the direction of our choosing. For this, we need something to tell us how to compare vectors from two different tangent spaces - those of neighbouring points. Let's say we're going from point $p$ to point $q$. We need something to tell us that as we transport ourselves from $p$ to $q$, $v \in T_pM$ is to be identified with some $v' \in T_qM$. We say that $v'$ is the *parallel transported* version of $v$ as we go from $T_pM$ to $T_qM$.

Note that parallel transport is *not* diffeomorphism-invariant. As Mr Dough twists and bends, this *canonical* scheme of forming a *connection* between neighbouring tangent spaces changes. As such, this canonical scheme of parallel transporting is called a *connection*. Imagine Mr Dough endowed with some parallel transport structure and bend and twist him in different ways, you see that the parallel transported vector from $p$ to $q$ rocks and rolls with diffeomorphisms. Anyway, in practice, parallel transporting any vector can be done once we have specified how to parallel transport each of the basis vectors in the direction of each basis vector, so we have an expression like $\nabla_{\partial_\alpha}\partial_\beta \equiv \Gamma^\mu_{\alpha\beta}\partial_\mu$, where the coefficients $\Gamma^\mu_{\alpha\beta}$ are called the *connection coefficients* or *Christoffel symbols*.

Once we've settled on a way to define parallel transport, our Mr Dough no longer remains. He's now become a rough, tough chunk of dough that's still a little malleable, but the malleability is constrained by the connection. He's now Mr Hardening Dough. He's not yet Mr Cookie, but he's no longer Mr Dough, too.

$$
\text{Mr Hardening Dough = Smooth Mfd + Connection}
$$

It's hardening, but not yet completely hardened. This partial solidification thanks to the parallel transport aparatus has three *huge* implications.

1. We now have a notion of *curvature*. This is why curvature is always defined on manifolds with connections, even in the absence of a metric. We parallel transport a vector on a loop and come back to the same point. If we're not left with our starting vector, the manifold is curved, by an amount proportional to the deviation.
2. We now have a canonical notion of differentiation, called *covariant differentiation*. We simply take the difference 

$$F(q) - \text{PT}_{p\to q}(F(p)) $$
 
Where $\text{PT}_{p\to q}$ denotes parallel transporting from $p$ to $q$, for some field $F$. 

3. We have a notion of *straight lines* or *geodesics* on the manifold. These are lines whose tangent at all points along its length coincides with its parallel transported version.

So to sum up the covariant derivative,
1. **What we need**: Smooth manifold *with* a connection. A bare smooth manifold will no longer suffice.
2. **What we do**: Use the Christoffel symbols defined above and differentiate. What you end up with is an expression like $\nabla_u v = u^\mu (\partial_\mu v^\nu + \Gamma^\nu_{\mu\beta}v^\beta)$
2. **What we get**: Covariant derivatives, curvature tensor, geodesics.

This ends our tour of the derivative zoo. We're ready to write down the answer to the question we started with:

> The reason differential geometry contains several derivatives is that "taking differences at nearby points" is not a well-defined operation on a general manifold. Each derivative solves this problem differently, by supplying a different notion of comparison.

 So far, we've repeatedly emphasised the fact that our ideas are completely metric-independent. We've been working on a manifold where we don't care how to measure angles between (and thus lengths of) vectors. We may or may not know how to, the ideas discussed so far just don't care for the most part. The partial solidification done by the connection is fine, but it cannot equip the manifold with a completely rigid structure.

## Mr Dough becomes Mr Cookie: The Metric as the Oven
The metric completely solidifies Mr Dough. Irrespective of a connection being there, the metric also *induces* a preferred connection, called the *Levi-Civita connection*. How does it do so?

Remember how the connection defined straight lines? Given two points, if a line joining them is such that the tangent is *autoparallelly transported*, it is straight under that connection. Now the metric gives us a way to measure distances, and that means we can measure all the lines joining any two points. And we generally expect that the straight line joining the two points will also be the shortest one (except for pseudo-Riemannian manifolds, where we expect the converse). So a metric naturally picks out a notion of straightness, which we can use to define a canonical connection - the Levi-Civita connection. 

Now in general relativity, this is all we ever work with, and so it's easy to come away with the misconception that the connection comes secondary to the metric. It doesn't. They're completely independent concepts. This gets clarified when you encounter Yang-Mills theories and see that the connection is one of the most important concepts in our Standard Model.

## Call it a Day
I'm tired. I'll add stuff later if I think something up or edit if something feels off. Hope the big picture comes across as nicely as I intended. This has been borne of countless hours of viewing lectures and working through materials on GR, DG, QFT, Yang-Mills and so on. I'll namedrop some of my favourites when I feel like it. G'night.
