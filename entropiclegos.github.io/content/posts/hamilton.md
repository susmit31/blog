+++
title = 'Lights, Hamilton, Action! - A Brief Look into How Optics Guided Schroedinger'
date = 2025-11-27T02:44:50Z
draft = false
tags = ['physics', 'optico-mechanical analogy', 'quantum mechanics']
+++

## TL; DR
> "\[Hamilton\] had understood, in 1830, how and in what limits the geometrical optics was an approximation of wave optics... he made in 1830 the surprising remark that the formalisms of optics and could be unified, and (prophetic vision) that the Newtonian mechanics corresponds to the same limit or approximation, as geometrical optics compared to wave optics." - J.L. Basdevant, *Variational Principles in Physics*

Any beginner in physics who has learnt some quantum mechanics inevitably is struck by a sense of sheer amazement at how Schroedinger came up with his eponymous wave equation that describes nonrelativistic quantum-scale phenomena. Schroedinger, of course, didn't receive his equation in a dream, contrary to the indirect allusion of many texts. Interestingly, much of the groundwork was laid by Sir William Rowan Hamilton, who, based on similarities between optics and what's now called the Hamilton-Jacobi formulation of classical mechanics, suspected that classical mechanics must be the short-wavelength "geometrical" limit of some overarching wave mechanics theory. This is where Schroedinger started, and as you'll see, this is the much more logical way to motivate quantum mechanics from a theoretical standpoint.

## Prerequisites
I assume the reader is familiar with Lagrangian and Hamiltonian mechanics. It would help if you're familiar with some classical electrodynamics and optics, the Bohr atomic model and de Broglie waves, too. And of course, I assume you've at least at some point in your life *wondered* how Schroedinger's equation arose. You don't need to know all these beforehand to understand the big picture, but these are the topics I won't expand upon and you'll have to look these up if you're not familiar with them.

## In The Beginning, There Was Light
Refraction and Snell's law is familiar to even the greenest individuals in optics given that it's taught in schools, so I start here. The first thing to notice is the similarity between motion of a particle at the interface between two regions of constant potential and the phenomenon of refraction. I first noticed this while working out massive particle and photon orbits in Schwarzschild geometry, but this generalises extremely well, as you'll see in what follows. You can easily show using principles of energy and momentum conservation that such motion follows the following "law":

$$
v_1 \sin \theta_1 = v_2 \sin \theta_2
$$

which is of course *very* similar to Snell's law for refraction at an interface between two homogeneous, isotropic dielectrics:

$$
n_1 \sin \theta_1 = n_2 \sin \theta_2
\implies \frac{\sin \theta_1}{v_1} = \frac{\sin \theta_2}{v_2} 
$$

Despite being very different phenomena, there's a remarkable similarity between the two motions. (We could also apply this line of reasoning to understand curved spaces, but that's a matter for another day.) This alone is fascinating enough on its own right, since this "Snell's law" for particles allows you to easily draw particle trajectories in all sorts of potential fields by chopping it up into fine slices of constant potential. And perhaps that is what led Hamilton to pursue this beautiful route of unification. But we'll look at another way in which the modern reader might be led to this so-called *optical-mechanical analogy*. 

Firstly, you might be familiar with *Fermat's principle of least time* governing the motion of light rays, which gives one of the ways to arrive at Snell's law (the other being by solving Maxwell's equations with the appropriate boundary values):

$$
 \delta \int \frac{n(\vec{r})}{c} ds(\vec{r}) = \delta \int dt = 0
$$

Secondly, governing massive particle motion in relativistic mechanics we have the *principle of maximal proper time*:

$$
\delta \int d\tau = 0
$$

or equivalently, the *principle of "least" action*, with the relativistic action given by:

$$
S := – \int m d\tau
$$

While the exact meaning of the time measured in both contexts is different, it would be reasonable to have a hunch about at least a hint of a deeper similarity. The hunch, obviously, turns out to be true, but it will unfold in rather unexpected ways.

## Waves vs Rays: A First Showdown
Before proceeding, we need to see what I consider a rather beautiful conception: the **eikonal equation for light rays**(eikonal is just the Greek word for "related to icons or images", so named because the formation of images by refracting and reflecting surfaces is explained with this theory):

$$
\boxed{\text{Eikonal equation for light}}
$$
$$ \nabla R(\vec{r}) = n(\vec{r}) \hat{u}
$$

where the function $R(\vec{r})$ gives, through its contours, the wavefronts of the light wave, $n(\vec{r})$ is the index of refraction, and $\hat{u}$ is the direction of propagation. $R$ is called the *eikonal function*. This isn't the full wave equation for electromagnetic waves, of course, which is a 2nd-order, 1st-degree PDE of the form:

$$
\boxed{\text{EM Wave equation}} \quad \nabla^2 E_i = \frac{1}{c^2} \partial^2_t E_i 
$$

We obtain the Eikonal equation by working with a trial solution:

$$
\vec{E} = \vec{E_0} e^{(ik_0R - i\omega t)}
$$

and then taking the short wavelength limit.(For the details, I'll refer you to chapter 9 of the excellent [https://optics.byu.edu/textbook](optics textbook) from Brigham Young University, made available by them for free.) 

Two things you should be asking yourself whenever you see an approxumation are

1. Under what conditions is the approximation valid?
2. What do we lose by working with the approximation, and what do we retain?

I've already told you the answer of question 1. The answer to the first part od question 2 is that we lose the ability to explain diffraction and interference, for example - the phenomena which depend on wavelength. These are not important for monochromatic light moving over really long distances, where the wavelength is constant and much smaller than the scales of motion. 

What about the second part of question 2? We retain a core theory of rays travelling in straight lines so long as the index of refraction doesn't change (see any similarities with Newton's first law?). We can, for example, use the eikonal equation to immediately arrive at Snell's law. And of course, much of the ray optics you learnt in high school (the lens equation and all that stuff) is based on this ray theory of light, i.e. the eikonal equation.

To summarise, we write the following quip:
> Light is an EM wave described by the EM wave equation, but in the short-wavelength limit, we can replace the waves with a simpler ray theory, described by the eikonal equation.

## Hamilton's Eikonal Equation for Mechanics
When I first learnt Hamilton-Jacobi theory more than 10 years back during my first exposure to analytical mechanics, I found it to be not much more than an obscure theoretical curiosity. It's a formulation of mechanics where the *action* takes centre stage through the central equation

$$
\boxed{\text{Hamilton-Jacobi equation}} \quad H + \frac{\partial S}{\partial t} = 0
$$

The conjugate momenta are given by

$$
p_k = \frac{\partial S}{\partial q_k}
$$

Of course, this immediately gives in the Cartesian coordinates the following result:

$$
\nabla S = p \hat{p} = \sqrt{(2m (E - V)) \hat{p}}
$$

Do you see where we're going? This is virtually identical to the eikonal equation for light. So we write,

$$
\boxed{\text{Eikonal equation for matter}}\quad \nabla S = \sqrt{(2m (E-V)) \hat{p}}
$$

where the action $S$ now plays the role of the *eikonal function*, and $\sqrt{(2m (E-V))}$ gives the effective "refractive index" for the wave represented by this. This contains everything you need to describe particle motion in Newtonian physics. 

The wave speed can be calculated by setting the differential of the wavefront to be zero:

$$
dS = 0
$$

which can be solved for a time-independent Hamiltonian, where the Hamilton-Jacobi equation can be integrated to give
$$
 S = S_0 - Et
$$

and so

$$
dS = \nabla S_0 \cdot d\vec{r} - E dt = 0 \implies \vec{u}\cdot\vec{p} = E
$$

since the wave's velocity $\vec{u}$ is parallel to the particle momentum $\vec{p}$, this means:

$$
u = \frac{E}{p}
$$

Now the natural question that **Hamilton** asked in 1830, nearly a century before Schroedinger wrote down his wave equation, or nearly 70 years before anything quantum was ever heard of,

> If the eikonal equation for light is the short-wavelength limit of the more accurate wave theory, then is classical mechanics, which gives an eikonal equation for matter, the short-wavelength limit of some deeper wave theory describing matter?

The answer, however, would take a hundred years more.

## Hamilton's Vision Realised: The Schroedinger Equation
By the 1900s, evidence started to pour in that showed that matter might, like Hamilton suspected, perhaps. In 1926, Schroedinger published a series of papers called *Quantization as an Eigenvalue Problem*. Here he put forth a wave equation synthesising the ideas of Hamilton and de Broglie's ad-hoc *matter waves* hypothesis to explain the Bohr atomic model. 

How did he arrive at this? We pick up where Hamilton left off: we try to find a wave equation which gives the matter eikonal in the short-wavelength limit. 

Firstly, it'd tremendously help if we used the following restructured EM wave equation guiding our analogy, let's call it the time-independent EM wave equation:

$$
\nabla^2 E_i + \frac{n^2 \omega^2}{c^2} E_i = 0
$$

Now start working backwards. We know that the eikonal equation for matter gives the action $S$ to be equivalent to the wavefronts of light waves. So similar to the monochromatic light wave ansatz, we choose the following to represent matter waves that solve the as of yet undwtermined matter wave equation:

$$
\psi = \psi_0 e^{iS/\kappa}
$$

where \kappa is a constant. Recall that for a time-independent Hamiltonian, the Hamilton-Jacobi equation can be integrated to give

$$
 S = S_0 - Et
$$

which means the wave can also be written

$$
\psi = \psi_0 e^{[i(S_0/\kappa - E t/\kappa)]}
$$

Comparing this with the EM wave solution, we get the following equivalent quantities:

$$
\frac{E}{\kappa} \cong \omega
$$

Now using $u = E / p$ and $\omega = 2\pi c / \lambda n$, we get

$$
\lambda = \frac{\kappa}{p}
$$

this is of course the famous de Broglie wavelength. So Hamilton's formalism has led us to this identification, which we now use to finalise our time-independent wave equation, where we replace $\omega$ by $pu/\kappa$ and recall that the wave velocity, $u$, must be indetifies with the EM wave velocity, $c/n$:

$$
\nabla^2 \psi + \frac{n^2}{\kappa^2} \psi = 0.
$$

Recalling that $n = \sqrt{(2m (E-V))}$, we arrive at the *matter wave equation* envisioned by Hamilton:

$$
\boxed{\text{Hamilton's matter wave equation}}
$$
$$
\nabla^2 \psi + \frac{2m(E-V)}{\kappa^2} \psi = 0
$$

Sir Hamilton didn't derive this, of course, but it was a relatively straightforward completion of his rudimentary concepts. We now know the constant $\kappa$ is just $\hbar$, the reduces Planck constant. So we see that Hamilton was indeed right to speculate that

$$
\boxed{\lim_{\lambda \rightarrow 0} \text{wave mechanics} = \text{classical mechanics}}
$$

i.e., classical mechanics is the eikonal limit of the more correct wave description of matter.

## Further Reading
The literature on this topic is pretty advanced compared to typical undergrad stuff, but you can find it in most graduate-level analytical mechanics books. My favourite is *The Variational Principles of Mechanics* by *Lanczos*. Other resources I've frequently referred to included, you can check out the following list of resources to dive deeper.

1. The Variational Principles of Mechanics - C. Lanczos.
2. Theoretical Physics Vol. 2 (Analytical Mechanics) and Theoretical Physics Vol. 3 (Quantum Mechanics) - W. Nolting.
3. Modern Classical Mechanics - Helliwell and Sahakian.
4. Variational Principles in Physics - Basdevant.
4. Analytical Mechanics for Relativity and Quantum Mechanics - Johns.
4. Principles of Optics - Born and Wolf
5. The Physics of Optics - Peatross and Ware.

