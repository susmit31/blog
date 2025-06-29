+++
title = "Manifolds, Connections, Topologies - Let's Bake a Cake! (REPOST)"
date = 2025-06-26T22:05:59+06:00
tags = ['mathematics', 'differential geometry', 'topology']
draft = false
+++

## Topology in Cakeland
The first issue you run into when you're trying to learn topology and differential geometry, if you've never taken a class in "advanced" maths before, is the fact that it's studded with definitions, often with no clear motivation. Now of course this wasn't the case when these ideas were being worked out, they just didn't make things up as they pleased. In this series of articles, we'll take a step back from rigorous mathematics and try to come up with intuitive notions that best convey these ideas. 
## Gen. Topology, Brig. Connection, Maj. Manifold
Today we'll give a big picture overview of topologies, manifolds, and connections. Intended audience includes those who've already had some exposure to these but can't quite internalise the ideas and tie them together with a concrete example. If you have no idea at all about any of these things, you might still try reading, but I wouldn't encourage you to, at least before you've had some proper exposure from any book or lecture.

## Let's Bake!
### Step 0: The Baking Powder
One of the most primitive notions in maths is that of a set. What is a set? I can try to say that it’s a “collection of elements”, but then I haven’t really solved the problem - in defining one undefined idea, set, I’ve brought in another undefined idea, collection. How do you define a collection? You’ll probably just fall back to the concept of a set, saying “it’s a set of objects” (or use some other English synonym of set, e.g. aggregate) - a circular definition. Indeed, this motivates us to take sets for granted as basic entities like numbers. Assume you’ve got a bowl of flour. It has probably several thousands of flour particles. This is a set of flour particles. Each particle within the bowl is an element of the set. Keep the image at the back of your mind, we’ll need it for the rest of this article.

### Step 1: Making a Dough
A set in and of itself isn’t probably that interesting - there is nothing notable going on between the elements. If we turn the bowl upside down, the flour particles will start falling, each following a separate, isolated path. To start talking about continuity and stuff like that, we need to somehow define neighbourhoods. How do we define neighbourhoods in the bowl of flour? We can add water to the bowl to make a dough - this “connects” different elements (flour particles) of the set. Now when you turn the bowl upside down, the entire thing falls together as a dough. A topology on a set does just this - it defines neighbourhoods within that set. It adds water to the bowl of flour to make dough out of it. A set with a topology is known as a topological space. In short, a topological space is a pair (set, topology). So our dough is a topological space.

### Step 2: Filling Up "Holes" In The Dough
What shape does a dough have? It doesn’t have a definite shape, it’s malleable. However, when you give a dough a particular shape, unless you’ve added too much water, the dough will stay in that shape until you change the shape again. So in a topological space, we can talk about continuity, but there is no notion of shape. In differential geometry we’re interested about the shape of space, so we’re interested in equipping our sets with a notion of shape. How do we do it? Let’s start with a 1-dimensional curved space. How do we detect whether a curve, y(x), is straight? We take its derivative - that tells us how the slope changes as a at different points in space. If the derivative is constant, there is no change in the slope, and hence the “curve” is straight. So we need to somehow differentiate on this dough. But if you took your calc classes seriously, you’ll have noticed that we only know how to do calculus on an n-dimensional Euclidean space. What do we do for arbitrary spaces?

### Step 3: Making The Dough "Shapable"
Well if we can map that arbitrary space into an n-dimensional Euclidean space, Rn, we can do calculus easily. We take the the dough, "deform" it into an n-D Euclid, do calculus, and then go back to the dough. So when we have a continuous map from the topological space to Rn and back, we can talk about differentiability on the space. This is an important quality to have, and so we give a special name to those topological spaces that have such a structure - we call them manifolds. The functions we use to map the manifold into Rn comprise an atlas. So in other words, a manifold is a triple of (set, topology, atlas). This merely means that we now know how to do calculus on the dough. It's "shape-giveable", loosely speaking. But we haven't exactly given it a definite shape yet. However we choose to deform it, the structure (set, topology, atlas) doesn't get changed. We have to add a new level of structure that differs based on the exact shape of the dough, i.e. that exactly describes the shape of the dough. 

### Step 4: Shaping the Dough
To encode mathematically notion of curvature in a manifold, notice that in Rn we have the same unit vectors everywhere. On the other hand, on a curved surface like the earth, we can define locally flat coordinate systems, but each such region will have unit vectors pointing in different directions. So we notice that how the unit vectors on a manifold change can tell us the shape of the manifold. How do we measure their change? We differentiate them. The derivative of the unit vectors at each point in the manifold define the connection component functions on that manifold. For different choices of these functions, we get different derivative fields, and hence different shapes. So when we fix a particular connection on the manifold, we thus also fix its shape. So the dough isn't malleable anymore. We've put it into the oven and baked a cake out of it. The quadruple (set, topology, atlas, connection) is thus a cake.

## Your Topology Cake is Now Ready To Be Served!
Before you head off to enjoy the freshly baked cake, let's summarise. We started with powder - which is just a set. We added water (equip with a topology) in it to make dough - a topological space. We make sure the dough looks okay (equip with a continuous atlas) - a manifold. And finally we mould it into a nice shape and put it into an oven (equip with a connection) to fix its shape and get a cake.

I hope this has been helpful. Thanks for reading, goodbye!

(Editing notes: This is an [old post](https://susmitislam.wordpress.com/2021/04/25/a-wannabe-topologists-apology-lets-bake-a-cake/) written in 2021 and retrieved from my then-blog.)
