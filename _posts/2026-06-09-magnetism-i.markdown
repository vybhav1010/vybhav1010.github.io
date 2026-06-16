---
layout: post
title:  "Magnetism I - Lorentz, Cyclotrons, and DC Motors"
date:   2026-06-09 22:11:19 -0400
seo_title: Vybhav Velamoor Tchaikovsky First Piano Concerto Score Music Analysis
mathjax: true
---

I'm currently working through [R. Shankar's Fundamentals of Physics II](https://oyc.yale.edu/physics/phys-201), and I'm planning on making a series of posts detailing what I've learned, of which this is the first. We'll discuss magnetic fields and some of their applications. Without further ado, let's jump in!


Similar to the electric case, calculating magnetic forces is a two step process. First, we must find the magnetic field $\bf{B}$, at a certain point in space, and then we must compute the force F on that object. From there,  it is possible (in theory at least) to calculate the full trajectory of that particle. In this post, we will deal purely with the second stage of this process, the force on a particle with a known $\bf{B}$ field. This is given by:


$$\bf{F} = q\bf{v} × \bf{B}$$




This is a rather strange formula. The first thing of note is that this force depends on the velocity. Neither the gravitational force nor the electric force had this property; both depended only on the mass and charge of the particle respectively. Secondly, the force always acts perpendicular to the velocity of the object. This means that $F · d\bf{v}$ is always zero, and thus no work is done by the magnetic force on the particle. We can therefore deduce that a particle affected only by the magnetic field moves with constant velocity. If the field is uniform, we may also say that the particle undergoes uniform circular motion. Suppose we put a particle of charge q in a magnetic field of magnitude $B$, and give it a velocity $\bf{v}$. Then, the force will "follow" the particle, keeping the acceleration radially inward. If $\bf{B}$ is uniform, the acceleration is uniform, and so the particle undergoes uniform circular motion. 

![image]({{site.baseurl}}/images/magnetism-i/orbit.png)


We can solve this equation to find the frequency of the orbit. We have:

$$qvB = \frac{mv^2}{R} \\

v=\frac{qBR}{m}=\frac{2πR}{T} = ωR \\

ω = \frac{qB}{m}$$


This is called the cyclotron frequency, and it is key that it is independent of both the radius of the orbit and the speed of the orbit, a consequence of the curious factor of v present in the formula for the magnetic force. In fact, we can use this fact to construct our very own particle accelerator, called the [cyclotron](https://en.wikipedia.org/wiki/Cyclotron).  Take two plates charged to +Q and -Q, and establish a $\bf{B}$ field outside the plates as shown in the picture. Now, place a charge q near the positive plate. It will fall towards the negative plate, picking up speed. Once it passes through, the $E$ field will drop to zero (by to Gauss' law). So, the particle completes half a cyclotron orbit. We must now swap the polarities of the plates, and while difficult, we can do this autonomously due to the constancy of $ω$. The particle then falls through again and again until it is ready to be launched. 

![image]({{site.baseurl}}/images/magnetism-i/cyclotron.png)

We've been considering a particle acting under the presence of only a magnetic field, but electric fields can act on it as well. We write the combined force as:

$$\bf{F} = q(\bf{E} + \bf{v} × \bf{B})$$,

known as the Lorentz force. 

Now that we've analyzed the motion of individual charged particles in a magnetic field, the natural next step is to analyze currents. We do this by writing our current in terms of the motion of individual charged particles. Suppose a conductor has n charge carriers per unit volume, each of charge q. Then, the current will be:

$$I = nqvA$$,

where $A$ is the cross-sectional area of the conductor, and $v$ is the drift speed. Each individual charge $q$ experiences a force of $q\bf{v} × \bf{B}$.  We'll zoom in to a specific spot on the conductor, add up all the individual Lorentz forces, relate that sum to the current, then sum up the contributions from every point on the conductor.

Immediately though, we run into a major issue: $I$ is a scalar. As a result, we don't have anything with which to take a cross product with $\bf{B}$.  To solve this, we introduce a new vector, the length vector $\bf{l}$ which points in the direction the current flows.  

Now, we can zoom into a spot on our conductor. If we pick just a point though, there are no charges to be found! So, we zoom into a little strip $d\bf{l}$. Since the cross-sectional area is $A$, this has volume $A\vert d\bf{l} \vert$. The number of charges $q$ present is $nA\vert d\bf{l}\vert$, each moving with velocity $\bf{v}$. The force on each is $q\bf{v} × \bf{B}$, so the total force, $d\bf{F}$ is $nqA\vert dl\vert\bf{v} × \bf{B}$.  But, we've defined our $\bf{l}$ vector to be in the same direction as our velocity vector (the direction of the current). So, we may instead take the magnitude of $\bf{v}$ (the drift speed), and replace $\vert \bf{l} \vert$ with $d\bf{l}$ the vector. Our final expression is:

$$d\bf{F} = nqvAd\bf{l} × \bf{B} = Id\bf{l} × \bf{B}.$$ 


To find the total force on a wire, we integrate this expression. If the wire is completely straight (and $\bf{B}$ uniform), we have:

$$F = Il × \bf{B}$$

![image]({{site.baseurl}}/images/magnetism-i/wire.png)


Suppose we have a rectangular loop of current in a uniform magnetic field. Because each side has an opposing side which carries current in the opposite direction, the net force on it is zero. However, the  net torque on the loop about the center of the loop is not zero if the loop is not perfectly perpendicular to the field. We define a new vector 𝜇 (the magnetic moment), perpendicular to the plane of the loop (direction is determined by curling the right hand in the direction of the current), whose magnitude is the $IA$, where $I$ is the current and $A$ is the area of the loop. In the case of the loop, it's not difficult to verify that the torque is equal to $𝜇 × \bf{B}$, so the loop reaches a stable equilibrium when $𝜇$ is aligned with $\bf{B}$ (The result holds more generally as well).


![image]({{site.baseurl}}/images/magnetism-i/loop.png)

We can use this torque to create what is known as the [DC motor](https://en.wikipedia.org/wiki/DC_motor).  We begin by establishing a uniform magnetic field (either through a bar magnet, or something else), and placing a current loop, driven by an external battery in this field. If we leave it alone, it will rotate until $𝜇$ is aligned with $\bf{B}$.  But, we want our motor to rotate in perpetuity. To reverse the direction of the torque, we must reverse the direction of the current, thus reversing the direction of $𝜇$. This is difficult though, we can't simply swap the wires in the battery each time the loop makes a turn. The solution is a device known as a commutator. We hook up the wires of the loop onto a springloaded disk, cut in the middle. Each is connected loosely to metallic brushes from the positive and negative terminals respectively. After a half revolution, the brushes will be connected to the other semicircular disk. The current will then switch, as we wished.

We'll discuss the origin of these magnetic fields from moving charges to complete our discussion in the next post.


Thank you for reading!
