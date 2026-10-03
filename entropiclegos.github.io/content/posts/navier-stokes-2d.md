+++
title = 'In Another Dimension I Would Be Yours: Navier-Stokes Existence, Uniqueness and Regularity in 2D'
date = 2026-09-29T20:42:37+06:00
tags = ['mathematical-physics', 'maths', 'millennium-prize', 'differential-equations']
draft = false
+++

## TL;DR
OpenAI has taken the world by storm and by now, everyone and their grandmother knows that the 3D Navier-Stokes problem, unsolved for a century by human beings, has been solved by a silicon-based ghost. The upshot is that it is possible to develop a finite-time singularity in an initially smooth fluid flow acted upon by a smooth and bounded external force everywhere. In other words, the equation may produce a blowup of the fluid even when there should have been none. What fewer people and their grandmothers know is that the same problem, in 2 spatial dimensions, gives a drastically different behaviour -- well-behaved initial conditions always lead to well-behaved fluid flow. In today's post, we explore what the mathematical theories of partial differential equations and functional analysis have to say about 2D fluid dynamics, the difference between the 3D and the 2D Euler (Navier-Stokes) equations, and why a wacky effect called "vortex-stretching" leads to finite-time blowup in 3D, but not in 2D.

## Pre-Requisites
Though like all my other posts, this is going to be mostly a high-level conceptual review of some highly technical literature which I myself have yet to fully work out, I still need you to go into this knowing quite a bit of stuff. The list below may be incomplete, but I consider these to be essential before diving in, and so you may look them up before proceeding further. More on prerequisites and further reading [below](#further-reading).
1. I assume you are familiar with the incompressible Navier-Stokes and Euler equations from fluid dynamics, know what each of the terms mean, and have seen them in the vorticity formulation.
2. Are familiar with basic functional analysis concepts, such as $L^p$-*norms, Lipschitz* and *Log-Lipschitz continuity*, maybe a little familiarity with *Sobolev spaces* etc.
3. Are familiar with some basic results on the existence, uniqueness and boundedness of solutions for differential equations.
4. Are familiar with basic tensor operations and notations, e.g. index gymnastics, summation convention, Kronecker delta, $\epsilon_{ijk}$ etc. I may switch back and forth from vector and tensor notations depending on ease of typing.

## Act 1: Navier-Stokes and Euler in 2D
For the sake of completeness and beautification (and perhaps establishing notation), I'll include the Navier-Stokes equations in their full 3D form for once, before embarking on our full journey. 

$$
\begin{aligned}
\boxed{ -\vec{\nabla} p + \mu \nabla^2\vec{v} + f_{\text{ext}}=\rho \frac{D \vec{v}}{Dt} = \rho\left[\partial_t \vec{v} + (\vec{v}\cdot\vec{\nabla})\vec{v}\right]}\\
\end{aligned}
$$

along with the incompressibility condition
$$
\mathbb{\nabla}\cdot{\mathbb{v}}=0
$$

 We'll for the time being focus solely on the Euler equation, i.e. where the viscosity $\mu = 0$, with $f_{ext} = 0$:

$$
\partial_t\vec{v} + (\vec{v}\cdot\vec{\nabla})\vec{v} + \nabla p = 0
$$

Taking the curl of this equation, and recalling that the vorticity field of the fluid is defined $\vec{\omega} := \nabla \times \vec{v}$, we obtain the **Euler equations in vorticity form**:
$$
\partial_t \vec{\omega} + (\vec{v}\cdot\nabla) \vec{\omega} = (\vec{\omega}\cdot\nabla) \vec{v}
$$ 

or more compactly, using the material derivative $\frac{D}{Dt} := \partial_t + v^i \partial_i$ and the Einstein summation convention,
$$
 \textit{\textbf{Euler equations: vorticity form}}
$$

$$
 \boxed{
	\frac{D\vec{\omega}}{Dt} = (\omega^i\partial_i) \vec{v}
} \text{  } (1)
$$

where the vorticity, in tensor notation, can be written
$$
\omega^k := (\nabla\times\vec{v})^k= \epsilon^{ijk}\partial_i v_j
$$

I'll also remind you that since we're working in Euclidean space, vectors and their dual covectors have identical components, and so in this case, upstairs and downstairs indices mean the same thing and are just used as notational devices for keeping track of what is to be summed over. 

Now, let's see how we interpret eqn. 1. The term on the left hand side gives the material derivative of the vorticity, so it tells us the rate of change of the vorticity *for a particular fluid particle*. The right hand side can be rearranged as
$$
\omega^i\partial_i v^j = (\partial_i v^j) \omega^i
$$

which in matrix notation becomes
$$
(\partial v)^T\mathbb{\omega}
$$

In other words, the right hand side of the Euler equation is a linear transformation of the vorticity "vector", which due to the left hand side equals the rate of change of the vorticity of any fluid particle. This is called the *vortex-stretching* term, since this is what contributes to the growth of vorticity. Note that since the viscosity term in Navier-Stokes is only a diffusion term, it alone cannot contribute to the growth of the vorticity, even if $\mu \neq 0$, so that the vortex-stretching term is the sole determinant of growth of vorticity.  

## Act 2: The Magic of 2D
It's a simple exercise to show that for 2-dimensional flows, the vortex-stretching term becomes identically zero, so the evolution of vorticity is then

$$
\frac{D\omega}{Dt} = 0
$$

where we've dropped the vector notation since for 2D flows, vorticity is of the form $\vec{\omega} = \omega \hat{k}$, i.e. the vorticity, if it's nonzero, always points along the z-axis. This implies that **vorticity is conserved along particle trajectories for 2D flows**. This means that the $L^\infty$-norm under the flow map is also conserved,

$$
\lVert\omega(t)\rVert_{\infty} = \lVert\omega_0\rVert_\infty
$$

, i.e., 2D Euler flows can at best rearrange vorticites without changing them. So we seem to have found a good reason to expect that an initially smooth 2D Euler flow will not blow up in finite time. Since 2D Navier-Stokes simply adds a diffusion term which will merely act to smooth out the distribution even further, we also heuristically expect that this will continue to apply to the full 2D Navier-Stokes equations with a nonzero diffusion term. Now is it sufficient for guaranteeing unique solutions, i.e. given two particles starting at the same point in the flow, can we guarantee that they will move in the same way at all times?

## Act 3: Yudovich Theory Ensures Existence and Uniqueness
For there to be unique particle trajectory for a unique starting position and a velocity field, we want there to be some sort of a bound on how velocities on nearby points can differ. As long as nearby points cannot differ by too much, they also cannot diverge by too much as the flow goes on. For example, you'll recall from ODE theory that if the solution exhibits Lipschitz continuity,
$$
\lvert u(x,t) - u(y,t) \rvert \leq L(t) \lvert x - y \rvert
$$

then it is unique, for some function of time $L(t)$. So to settle the question of uniqueness, we'll have to see what sort of continuity the Euler solution embodies.

 First up, note that since $\partial_i v^i = 0$ due to incompressibility, we have that $\vec{v} = \nabla\times\vec{\psi}$ for some $\vec{\psi}$. This is called a *stream function*. Again, since the flow itself is 2D, the stream function can effectively be treated as a scalar since it always points the same way. This allows us to write down a Poisson-equation for the stream function where the vorticity acts as a source term, which in turn gives a Biot-Savart solution for the velocity field:

 $$
u(x) = \frac{1}{2\pi}\int \frac{(x-y)^\perp}{\lvert x-y \rvert ^2} \omega(y) dy
 $$

 This, for $\omega \in L^\infty$, ends up yielding

$$
\lvert u(x) - u(y) \rvert \lesssim \lvert x-y \rvert \times(1 - \log \lvert x - y \rvert)
$$

This sort of continuity is called *Log-Lipschitz continuity*, which is a weaker version of continuity than *Lipschitz*. So we don't have Lipschitz continuity after all. But can we still retain uniqueness? Turns out even log-Lipschitz is sufficient to guarantee uniqueness. **So particles moving along a 2D Euler flow will always have a uniquely determined trajectory.**

## Act 4: Smoothness in 2D
We've already done most of the groundwork. Now all that is left is to finish things up by demonstrating that a runaway growth of the vorticity and the velocity fields is impossible under Euler flow. To show this, we must show that the partial derivatives of these fields are bounded, which we now proceed to do.

First up, we formally introduce the flow map, which we had alluded to previously:
$$
X(a, t) := \text{position of a particle at time t, which was  initially at position a}\newline
X(a, 0) = a
$$

 so that 

$$
\dot{X} = v(X(a,t), t)\text{ }\text{ ----------- }(2)\newline
$$

Now since $D_t \omega = 0$ in our 2D flow, we have
$$
\omega(X(a,t),t) = \omega_0(a)
$$

and

$$
\omega(x,t) = \omega_0 (X^{-1}(x,t))\newline
\implies \omega = \omega_0 \circ X^{-1}\newline
\implies \nabla\omega = \nabla (\omega_0 \circ X^{-1})\newline
\implies \nabla\omega = (DX^{-1}(x,t))^T\text{ }\nabla \omega_0(X^{-1}(x,t))\newline
$$

which finally yields the bounds
$$
 \lvert \nabla\omega \rvert \lesssim \lvert DX^{-1}\rvert \lvert \nabla\omega_0\rvert
$$

where the notation $DF$ is taken to mean "the Jacobian matrix of F". The above bound implies that whether $\nabla \omega$ blows up at a later time depends on the Jacobian of the flow map. Recall that the flow map's dynamics is given by eqn. (2) above, so we next turn to see whether we can find a bound for its Jacobian from there:

$$
\dot{X} = v(X, t)
$$

Now we differentiate both sides with respect to the initial position $a$. From the LHS we get
$$
 \partial_a (\dot{X}) = \frac{d}{dt}(\partial_a X) = \frac{d}{dt}(DX)
$$

and from the RHS, using multivariable chain rule,

$$
\partial_a v(X(a,t),t) = \nabla v(X,t) DX.
$$

So we get

$$
\frac{d}{dt} DX = \nabla v(X,t) DX \newline
\implies \frac{d}{dt} \lvert DX \rvert \lesssim \lvert \nabla v \rvert \lvert DX \rvert
$$

So physically, this bound means that the velocity gradients determine the deformation map's Jacobian determinant, and previously we saw that this determinant in turn determined the vorticity gradients. So we've found a feedback loop between the velocity and the vorticity gradients, and showing that one of them is bounded would then suffice to conclude that the fields themselves don't blow up over finite time. Since we already know that $\lVert \omega(t)\rVert_\infty =M$ for some constant $M$, we'd like to have, say, $\lVert\nabla v\rVert_\infty \lesssim \lVert\omega\rVert_\infty$. But the Biot-Savart kernel actually yields a more logarithmic dependence between the gradients:

$$
\lVert \nabla v \rVert_\infty \lesssim C\left[1 + \log (1 + \lVert\nabla \omega\rVert_\infty) \right]
$$ 

so even if there is an enormously fast-varying vorticity gradient, $\nabla v$ varies at best logarithmically. That's further good news -- runaway explosion seems even less likely now. Finally, if we can put a finite bound on $\lVert\nabla\omega\rVert_\infty$, we'll be done. We start with $D_t \omega = 0$ and take its gradient:

$$
\partial_t \nabla\omega + u^i \partial_i \nabla\omega + (\nabla v)^T (\nabla \omega) = 0 \newline
\implies D_t \nabla\omega = -(\nabla v)^T (\nabla\omega) \newline
\implies D_t |\nabla\omega| \lesssim |\nabla v| |\nabla\omega| \newline
$$

$$
\implies \frac{d}{dt}\lVert\nabla\omega\rVert_\infty \lesssim \lVert\nabla v\rVert_\infty \lVert \nabla\omega \rVert_\infty\newline
$$

$$
\implies \frac{d}{dt}\lVert\nabla\omega\rVert_\infty \lesssim C \lVert\nabla\omega\rVert_\infty \left[1 + \log (1 + \lVert\nabla\omega\rVert_\infty)\right] 
$$

The last inequality places the bound on $\lVert\nabla\omega\rVert_\infty$ at:

$$
\lVert\nabla\omega(t)\rVert_\infty \lesssim \exp (C_1 e^{C_2 t}) < \infty \text{ }\text{ }\forall t
$$

So **runaway growth is impossible for a 2D Euler flow**. 

This is something to revel at. Although we've seen a relatively restricted version of the full, much harder 3D problem, this is no small feat. We started with the fact that there was no vortex-stretching in 2D, which led to our key equation $D_t \omega = 0$, which we've used repeatedly throughout our above uniqueness and regularity arguments. And at the end, we've managed to see how this suffices to put a strictly finite bound onto the gradients, thereby ensuring the absence of a finite-time blowup. The full 2D Navier-Stokes proof, by the way, is very similar, and as we've already argued heuristically before, the viscosity term adds diffusion to the vorticity and the velocity fields, so that its effect is smoothing them out, and as such the full 2D NS equation has no mechanism for runaway blowup either. 

## Further Reading
Much of the argument I've taken from the [Second Course in PDEs](https://math.stanford.edu/~ryzhik/STANFORD/STANF272-15/notes-272-15.pdf) Stanford math lecture notes. Specifically, 2D Euler is dealt with in chapter 6. Good overviews on functional analysis and PDE theory can be found in the *Function Spaces* and the *Partial Differential Equations* chapters of *Princeton Companion to Mathematics*. General fluid dynamics references I've read don't cover this, and at any rate this is strictly speaking a maths topic anyway. But my favourite resources for the physics are *Acheson's Elementary Fluid Dynamics*, [David Tong's lecture notes](https://davidtong.org/teaching/fluid-mechanics/), and *Feynman Lectures volume 2*, chapters 39-42. After reading these physics-oriented fluid dynamics texts, Chapter 1 of *Majda and Bertozzi's Vorticity and Incompressible Flow* will set you up with a more mathematical approach and prepare you to take on the aforementioned chapter 6 of the Stanford notes. Good luck and goodbye for now!
