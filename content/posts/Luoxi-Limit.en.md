---
title: "😅Everyone's Doing Advanced Quantum Egyptology While I Just Want Earth to Blow Up?"
date: 2022-09-07T10:00:00+08:00
draft: false
math: true
tags: ["Planetary Physics", "Centrifugal Force", "Gravitational Binding", "Roche Limit", "Popular Science"]
categories: ["Physics Notes"]
---

In a rotating reference frame, centrifugal force pushes objects away from the rotation axis. So can we build a toy model within basic physics to calculate how fast Earth needs to spin to destroy itself? This article constructs a simple model computable with physics competition knowledge—the Luoxi Limit.

<!--more-->

## Model Description

Consider a rotating celestial body in vacuum. Assume its shape deforms from a uniform sphere of radius $R$ into a **uniform oblate spheroid** with its short axis aligned with the rotation axis. The body is a homogeneous fluid with constant density and constant total volume.

![Image](https://pic4.zhimg.com/80/v2-351e3e048a5d82e96e21957e1073c45b.png)

Typically, celestial bodies form from interstellar dust colliding and coalescing into gravitationally bound structures. Due to conservation of angular momentum throughout the process, the final body inevitably has some spin angular velocity. The interplay of gravity and rotation causes the body to flatten along the rotation axis—Earth itself has a larger equatorial radius and smaller polar radius.

## Computing the Centrifugal Potential Energy

Let the angular velocity be $\omega$, eccentricity $e$, and density $\rho$.

The centrifugal potential energy of a volume element dV is $-\frac{1}{2}\rho \cdot dV\omega^{2}(x^{2} + y^{2})$.

Using the ellipsoidal volume integral formula:

$$\int_{\Omega} x^{2} \mathrm{dV} = \frac{4\pi}{15}a^{3}bc$$

where the integration domain is a general ellipsoid $\{(x,y,z):\frac{x^{2}}{a^{2}} + \frac{y^{2}}{b^{2}} + \frac{z^{2}}{c^{2}} \leq 1\}$.

The centrifugal potential energy is then:

$$W_{s} = -\frac{4\pi}{15}\rho\omega^{2}a^{4}b$$

The constant volume constraint:

$$\frac{4\pi}{3}R^{3} = \frac{4\pi}{3}a^{2}b = \frac{4\pi}{3}a^{3}\sqrt{1 - e^{2}}$$

$$\Rightarrow \quad a = R(1 - e^{2})^{-1/6}$$

Thus:

$$W_{s} = -\frac{4\pi}{15}\rho\omega^{2}R^{5}(1 - e^{2})^{-1/3}$$

## Computing the Gravitational Self-Energy

The gravitational self-energy of a uniform rotating ellipsoid is:

$$W_{g} = -\frac{3}{5}\frac{GM^{2}}{R}f(e)$$

where $f(e)$ is the ellipsoidal shape factor (a function of eccentricity $e$), and $f(0)=1$ corresponds to a sphere.

For $e \ll 1$ (Earth's eccentricity is about 0.0034):

$$f(e) \approx 1 - \frac{2}{15}e^{2} + \mathcal{O}(e^{4})$$

## The Luoxi Limit

The total mechanical energy of the system is:

$$E_{total} = W_{s} + W_{g} + \frac{1}{2}I\omega^{2}$$

where $\frac{1}{2}I\omega^{2}$ is the rotational kinetic energy and $I = \frac{2}{5}MR^{2}$ is the moment of inertia (sphere approximation).

The stability condition for the body is that $E_{total}$ as a function of $e$ has a minimum at $e=0$:

$$\left. \frac{\partial^{2} E_{total}}{\partial e^{2}} \right|_{e=0} \geq 0$$

This yields the critical angular velocity:

$$\omega_{c} \approx \sqrt{\frac{4\pi}{5}G\rho}$$

Considering the escape condition from the stellar surface, when centrifugal force equals gravitational force on surface material:

$$\omega^{2}R \approx \frac{GM}{R^{2}} = \frac{4\pi}{3}G\rho R$$

$$\Rightarrow \quad \omega_{c} \approx \sqrt{\frac{4\pi}{3}G\rho}$$

Comparing the two—they're of the same order! This confirms that a body indeed breaks apart when the centrifugal force on its outer layers exceeds gravity.

## Earth's Demolition Time

Plugging in Earth's parameters: $\rho \approx 5.5 \times 10^{3}$ kg/m³, $G = 6.67 \times 10^{-11}$.

$$\omega_{c} \approx \sqrt{\frac{4\pi}{3} \times 6.67 \times 10^{-11} \times 5.5 \times 10^{3}} \approx 1.24 \times 10^{-3} \text{ rad/s}$$

Critical period:

$$T_{c} = \frac{2\pi}{\omega_{c}} \approx 1.4 \text{ hours}$$

Earth's current rotation period is 24 hours. So—if Earth spins about **17 times** faster (one revolution every ~1.4 hours), surface material would be flung off.

> Conclusion: Earth won't destroy itself from spinning too fast any time soon. Students can rest easy and focus on their qualifying exams.
