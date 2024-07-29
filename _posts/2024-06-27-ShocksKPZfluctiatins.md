---
title: Shocks and Fluctuation in PushASEP
date: 2024-07-27
tags: ["PushASEP"]
---

## Intro

The *PushASEP* is interacting random walk on a 1D lattice. The interaction to the left and right is different. Moving to the right, particles are blocked from moving to an occupied space. Moving to the left, particle push particles aside when moving to an occupied site.

## KPZ fluctuations 

We, Jhih-Huang Li and I, computed the fluctuation statistics for the PushASEP on the ring. You can find the result here: [Contour Integral Formulas for PushASEP on the Ring](https://arxiv.org/abs/2308.05372).

## Translation invarince

The result for the step initial conditions has an additional parameter $$\gamma$$, compared to the periodic initial conditions. The additional term $$\gamma$$ is due to the fact that the dynamics (in large scale) are translation invariant for the periodic initial conditions and not for step initial conditions. There is a key event for the case with step initial conditions that remove translation invariance, the shock from high vs low density of particles. The average speed of a particle in the system determine by the local density of the particles. The shock becomes a reference point in the large scale regime. Thus, in the result for the step initial conditions, we have a parameter $$\gamma \in \mathbb{T}$$ that transforms the frontier to the reference frame of the shock.

## Burgers Equation

The hydrodynamic limit is the function $$\rho(x,t)$$ of the local density of the particles at positions $$ n = [x L]$$ at time $$T = [ t]$$. The evolution is given by the *Burgers Equation*:

$$
\frac{ d \rho}{dt} +  \frac{d}{dx} \left[ p \rho (1 -\rho) - q \frac{\rho}{1-\rho}\right]= 0
$$

## Numerics

Let's consider the numerical solution of the Burger's equation with step initial conditions. We'll use a Fourier transform (approximation) since the step intial data is not smooth.

### Fourier Transform of Step Initial Data

Let the ring have period one so that solutions are periodic on $$[0,1]$$. For the step initial conditions, take

$$
\rho(x, 0) = \begin{cases} 1, & \quad x \in [1/4, 3/4] \\ 0, & \quad x \notin [1/4, 3/4]\end{cases}
$$

We have a Fourier expansion

$$
\rho(x, 0) = \sum_{k \in \mathbb{Z}} a_k e^{2 \pi i k x}
$$

where the coefficients are given by

$$
a_k = \int_{1/4}^{3/4} e^{2 \pi i k x} dx
$$

{% include utterances.html %}
