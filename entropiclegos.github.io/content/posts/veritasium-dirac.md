+++
title = "Footnotes to Veritasium - Klein-Gordon, Dirac, and More!"
date = 2025-12-11T20:29:40+06:00
draft = false
tags = ['quantum mechanics', 'physics', 'relativity']
+++

## TL;DR
> "God is a mathematician of a very high order and He used advanced mathematics in constructing the universe." - *Paul A.M. Dirac*.

Veritasium recently released a video on the basic wave equation describing spin-1/2 fermions, AKA the Dirac equation,
$$
\boxed{(i\hbar\gamma^\mu\partial_\mu - m)\Psi = 0}
$$
which to me is the one of the most beautiful equations in all of physics, second only to perhaps the Einstein field equations (or perhaps Hamilton's principle). In this post we add some technical meat that Veritasium glossed over, left unmentioned, or I thought deserves a bit more space(time), to the best of my knowledge (keeping in mind, of course, the wise words - *"The equation is smarter than I am"*).

## What's Wrong With Klein-Gordon (and -Fock)?
First we write down the KG(F) equation:
$$
\partial^\nu\partial_\nu\Psi + \mu^2\Psi = 0
$$

simply because I think there's a certain elegance to equations of physics written in covariant notation. Now onto the meaty stuff.

### KG was also "Schroedinger's Equation" in a sense
Schroedinger himself had come up with this equation when he was trying out different wave equations for explaining matter-waves, a year before Klein, Gordon and Fock. He abandoned this since it failed to predict the correct energy levels for the Hydrogen atom, and went on to work in the nonrelativistic limit, where he came up with his eponymous equation.

### Problems with Klein-Gordon: The Probability 4-Current
Most problems associated with the KG equation can be traced back to one key equation called the continuity equation. Any probabilistic theory of matter must respect some sort of a continuity equation, which simply says that the change in the probability density over time must be due to the "probability-fluid" flowing out of that region. The derivation is quite simple and here I simply write the four-current for the KG equation:

$$
J_\mu = \frac{\hbar}{m} \text{Im}(\psi^*\partial_\mu\psi)
$$

The root of all problems turns out to be the first-order partial appearing in this equation, which results in negative values for $J_0$ under certain conditions, so $J_0$ cannot be a probability density, something which must be $\ge 0$. We don't have this issue for the spatial components of $J_\mu$ since they represent the probability*current*, and hence is a 3-vector representing the flow of probability density - so it can be negative just fine. So we want a relativistic wave equation that is first-order in $\partial_0$. Since in relativity, Lorentz-invariance (note for the Pedant: the Dirac equation also encodes translational invariance, and so we say that it's invariant under the $(\frac{1}{2},0)\oplus(0, \frac{1}{2})$ representation of the Poincare group) mixes up time and space, Lorentz-invariance also requires the spatial derivatives to be of the same order as the time derivative. Note that the Schroedinger equation meets the first criterion (first-order in $\partial_t$) but not the second (second-order in $\partial_i$). The KG equation meets the second (spatial and temporal derivatives are of the same order), but not the first.

### How the 4-Current Leads to the Dirac Equation
This partial derivative, the "root of all problems", can ironically be alleviated precisely by taking the *square-root* of the energy equation, which provides an equation first-order in time (and space). This is exactly what the Dirac equation is! (To be pedantic, exactly taking the square root without expanding it in matrix space gives us the *Salpeter equation*, which is a *pseudo-differential* equation.) In the video, Derek (name of the guy from Veritasium, not an affectionate nickname for Dirac lol) probably outlines its historical origins when he shows Dirac working out the Dirac matrices aka Gamma matrices, which requires a bit of trial-and-error. Specifically, Derek says that according to Dirac, he all of a sudden had the idea to try out $4\times 4$ matrices. This gives off the impression that it was arbitrary, but it was not. Let's first write down the gamma matrices in terms of the alpha and beta matrices shown in the video:

$$
\alpha^i \equiv \gamma^0\gamma^i\newline
\beta \equiv \gamma^0
$$

In this notation, their anticommutator (clifford algebra) can be succinctly written as

$$
[\gamma^\mu, \gamma^\nu]_+ = 2\eta^{\mu\nu}𝟙
$$

where $\eta^{\mu\nu}$ is the Minkowski metric (inverted but that's the same) and 𝟙 is the $n\times n$ dimensional identity matrix. We'll try finding some restrictions on the value $n$ can take, thereby narrowing our search space for the $\gamma^\mu$ matrices that solve this particular anticommutator algebra. First note that the anticommutator implies that 

$$
\text{Tr}(\gamma^0) = 0, \text{and}\newline
(\gamma^0)^2 = 𝟙
$$

so that the $\gamma^\mu$ must be *even-dimensional*. Next, note that in 2D, we have the Pauli matrices we know and love from NRQM spanning $\text{SL}(2,\mathbb{C})$, which we can try out with $\gamma^0 = 𝟙, \gamma^i = \sigma^i$. But this is immediately ruled out due to the anticommutation relation between the Pauli matrices $[\sigma^\mu, \sigma^\nu]_+=2\delta^{\mu\nu}𝟙$, where we get the Kronecker delta instead of the Minkowski metric. So $n=2$ doesn't work. Next we can skip $n=3$ for reasons left as an exercise to the reader. The upshot is that we can solve it in $n=4$ dimensions and that gives us the required first-order relativistic differential wave equation.

### Making KG work: ignoring negative energy and negative probabilities
The negative energy solutions of both Klein-Gordon and Dirac are interpreted as the antiparticle solutions. But it isn't immediately obvious why we should allow them in the first place - it feels unnatural, as it should. We said that the Klein-Gordon equation must be discarded as a relativistic equation for a spinless particle because it leads to negative probability densities. When we work things out, it seems that the negative density arises *when we allow negative energy solutions*. So logically we should ask if we can make KG theory work by simply ignoring its negative energy solutions. If so, KG theory would be perfectly fine as a relativistic theory for describing spinless wave functions. But for one crucial reason we can't simply ignore the negative energy solutions and make it all sunshines and rainbows. 

Here's why. So far we've been writing down the KG and the dirac equations for free particles. In the presence of a potential, the *positive-energy solutions can transition into negative-energy states*, which of course are negative probability states, the source of our problems. This is what leads to the *Klein paradox*.

In other words, the Klein-Gordon equation cannot be salvaged *even if* we take out the negative energy plane wave solutions out of the solution space. What this means is that there simply is *no way of interpreting KG as a consistent single-particle relativistic quantum theory*. 

### Making KG (truly) work: the field interpretation
The only way to salvage KG theory is to interpret the 4-current $J^\mu$, which as we've just seen invariably leads to negative $J^0$ and hence can't be taken as a probability density, to be a *charge density* instead. In other words, the 4-current equation is taken to literally represent a charge-current rather than a probability current. In this case, the KG field $\Psi(\vec{x},t)$ no longer remains a single-particle wavefunction but instead becomes a *quantum field*. We multiply our previous $J^\mu$ by the elementary charge $e$ to arrive at the charge-density of this KG field:

$$
\rho = J^0 = \frac{\hbar}{m}\text{Im}(\Phi^*\partial_t\Phi)\newline
= \frac{i\hbar}{2m} (\Phi^\* \partial_t \Phi - \Phi \partial_t \Phi^\*)
$$

For a complex field $\Phi$, the negative-charge solutions are interpreted as antiparticles. For a real $\Phi$, the charge-density becomes identically zero, and hence they're their own antiparticles.

### How spin emerges out of the Dirac equation
With the level of detail Derek went into in his video, I believe he could have shown this remarkable property of the Dirac equation, which was merely hinted at. The core argument is simple: rotational symmetry of the Dirac particle leads to the conservation of $\vec{J} = \vec{L} + \vec{S}$, where $\vec{L}$ is the angular momentum associated with the motion of the particle. The $\vec{S}$ component, it turns out, is independent of the state of motion and leads to an "intrinsic" angular momentum associated with all Dirac particles, the components of $\vec{S}$ having eigenvalues $\pm \frac{1}{2}$, thus explaining spin-$\frac{1}{2}$ as a necessary consequence of Poincare invariance. Importantly, though, the solutions to the Dirac equations have *separate real estate* for spin-up and spin-down particles and antiparticles. Note that since the $\gamma^\mu$ are $4\times 4$, the solutions of Dirac equation $\Psi$ must also be 4-component complex-valued objects. This is called a Dirac (bi-)spinor, with (for plane wave solutions) the upper two components representing electrons with spin up and down, and the lower two representing positrons with spin up and down, respectively. 

## Concluding Words and Further Reading
I hope I've been able to add some appetizing footnotes to an excellent expository video. For details on the Dirac and Klein-Gordon equation, my favourite resources are the following:
1. At a basic level, I liked the videos from the channel *Physics Explained*.
2. At an intermediate level, the long-form video lectures from the YouTube channel called *Nick Heumann University*, and from *Richard Behiel*'s channel.
3. At a mathematically slightly more advanced (yet remarkably readable) level, lecture notes by Dr. Matthias Lienert. For something a bit more fleshed out physically, I used an old text called *Relativistic Quantum Mechanics: Wave Equations* by *W. Greiner* (but I think I should find more modern recommendations to replace this).
