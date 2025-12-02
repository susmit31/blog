+++
title = 'Lights, Hamilton, Action! - Part 2: A Better Way of Understanding Tunnelling'
date = 2025-11-30T21:33:37+06:00
tags = ['physics', 'quantum', 'action', 'Optico-Mechanical Analogy']
draft = false
+++
## TL; DR
> "Our dynamics (including its Einsteinian form) has lagged behind optics; it is still at the stage of geometric optics" - *L. de Broglie*, in his PhD thesis *Research on the Theory of Quanta*.

Last time, following the footsteps of Hamilton, we showed that classical mechanics is mathematically equivalent to geometric optics and naturally extended the particle theory of matter to *wave theory of matter*, for which

$$
\boxed{\lim_{\lambda \rightarrow 0} \text{Wave Mechanics = Classical Mechanics} }
$$

and thus saw how **Hamilton "predicted" quantum mechanics a hundred years prior to its advent**. As in geometrical optics, we forget about the details of the wave picture when the wavelengths are very small compared to the scales of motion. This allows us to simply describe classical particle trajectories, at the expense of the ability to explain phenomena like diffraction, interference, and importantly, attenuation. In this episode, we show how the quantum phenomenon of tunnelling is naturally understood as the attenuation of matter-waves. 

## Prerequisites
I assume the reader is familiar with quantum tunnelling and optical attenuation at a basic level. And, of course, I assume you've read the [previous episode](https://susmit31.github.io/entropic-legos/posts/hamilton/).

## Classical Mechanics = JPGfied Wave Mechanics
By now, you should be comfortable with the fact that both in optics and in mechanics we have a *wave equation* that describes the shape and propagation (and evolution) of waves that looks like:

$$
\nabla^2\Psi + k^2\Psi = 0
$$

where $k = n\omega / c$ is the so-called *wave number*, with $n$ being the refractive index (which in the case of mechanics is effectively $n = \sqrt{2m(E-V)} = p$, the classical momentum). Given this, with certain simplifying assumptions such as $\lambda \rightarrow 0$, we obtain the **eikonal equation** which describes geometric optics and classical mechanics:

$$
|\nabla S|^2 = n^2
$$

So by ignoring the details of the theory that describe phenomena at significant wavelnegths, we obtain the *geometric limit*. In other words, **classical mechanics is a lossy compression of the (more accurate) theory of wave mechanics**, just like JPEG images are lossy compressions of arrays of pixels. So much like any other lossy compression, we retain the big picture, but quite a few significant details are lost that can be noticed when we "zoom in". The "big picture" that we retain are the Snell's law and Fermat's law and their mechanical equivalents. The details that we lose are the phenomena which are naturally only explainable in the wave picture, and thus where the wavelengths cannot be ignored. These include diffraction, interference, attenuation and so on. Diffraction and interference gave us some of the most foundational experimental evidences that pointed to the wave nature of matter. Attenuation receives much less attention (pun unintendedly intended), despite being an important concept in signal analysis and applied optics. The quantum phenomenon of attenuation of matter waves, despite sounding unfamiliar, is one of the terms from QM that successfully made it to pop culture. That's because nowadays, it's called **quantum tunnelling**.

## What is Quantum Tunnelling?
You're all familiar with the principle of energy conservation. $E = \frac{P^2}{2m} + V(x)$ is always conserved (under time-translational symmetries of a system, to be pedantic). Since the first term is always $\ge 0$, it follows that the classical particle can never be found at values of $x$ such that $V(x) > E$. This is known as the *classically forbidden region*. Classical mechanics strictly prohibits particle trajectories from moving into such territories.

Let's see what quantum mechanics has to say about this. As usual, we operate using the optical-mechanical analogy framework, which is much more intuitive (and insightful) than the typical "shut up and solve your Schroedinger's" approach.

Our starting point will firstly be to calculate the refractive index $n$. At once, we run into a problem. Since $V > E$, we have $n = \sqrt{2m(E-V)} = i\sqrt{2m(V-E)}$.*The refractive index is imaginary in the classically forbidden region!* What would that even mean?

Well, the geometric-optical concept of the refractive index is about the Snell's law and it tells us the angle by which rays are deflected, so an imaginary refractive index, first and foremost, tells us that the Snell law is no longer applicable - we can no longer simply say how much the trajectory will "bend", or if there even is a well-defined trajectory to speak of. What *can* we infer, then?

Fortunately, the realm of complex refractive indices is a well-known topic in optics. Let's define the complex refractive index as
$$
\mathcal{N} = n + i\kappa.
$$

So the concept of a classically forbidden region, where the effective refractive index becomes imaginary, becomes manageable. Then the dispersion relation for a plane-wave solution to the wave equation becomes
$$
\mathbf{k} = \frac{{\omega}\mathcal{N}}{c}\hat{k}
$$
where $\hat{k}$ is a unit vector in the direction of propagation. The plane wave solution then becomes

$$
\Phi = \Phi_0 \exp{i(\mathbf{k}\cdot\mathbf{r} - \omega t)}\newline
\implies \Phi = \Phi_0 \exp{(-\kappa \hat{k}\cdot\mathbf{r})}\cdot\exp[{i(\mathbf{k_{\text{vac}}}\cdot\mathbf{r} - \omega t)}]\newline
\implies \Phi = \Phi_{\text{new}}\exp[{i(\mathbf{k_{\text{vac}}}\cdot\mathbf{r} - \omega t)}]
$$
where

$$
\mathbf{k_\{\text{vac}}} \equiv \frac{\omega n}{c} \hat{k}
$$

This is an attenuating wave with a decaying amplitude
$$
\Phi_\{\text{new}}(\mathbf{r}) = \Phi_0 \exp{(-\kappa \hat{k}\cdot\mathbf{r})}
$$

Note that the imaginary part of our complex refractive index, $\kappa$, is the only thing that determines the attenuation, while the real part $n$ determines the phase velocity $v_{\ph} = c / n$ of the wave in the "medium". Now, since the decay of the amplitude in the classically forbidden region is determined by $\kappa$, the imaginary part of $\mathcal{N}$, and as we've seen, in the context of tunnelling we're dealing with a purely imaginary effective refractive index, then it follows that the decaying wavefunction in the forbidden region looks like:

$$ 
\Phi_\{\text{new}}(\mathbf{r}) = \Phi_0 \exp{(-\frac{\sqrt{2m(V-E)}}{\hbar} \hat{k}\cdot\mathbf{r})}
$$

What does this mean *physically*?

This means firstly that

$$
\boxed{\text{for a purely imaginary refractive index, the amplitude}}\newline
\boxed{\text{ in the classically forbidden region is nonzero,}}
$$

and second, this nonzero amplitude decays the further we go from the "interface". For light waves, this decaying of the transmitted wave is intuitively clear. For matter waves, this is **quantum tunnelling**. This doesn't certainly substitute for a formal calculation, but notice the simplicity and insightfulness of the argument as opposed to the "shut up and solve Schroedinger's" approach espoused in typical QM texts.

## Remarks
I'll end this article with my future plans for this series. Since we have already shown how we go from classical-to-quantum, in the next (few) articles I hope (in shaa Allah) to talk a little bit about the JWKB (or semiclassical) approximation, Dirac's Lagrangian formulation of QM, and Feynman's path integral formulation of QM. If the ending feels abrupt, it is, since it's getting quite late and my fingers are not used to typing this much at a stretch, plus I didn't have a clear plan for today's article anyway other than the fact that I wanted to show how tunnelling is nothing magical. Sayonara.
