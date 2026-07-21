---
layout: post
title:  "Magnetism II - Biot-Savart, Ampere, and Loop de Loops"
date:   2026-07-19 22:11:19 -0400
seo_title: Vybhav Velamoor Tchaikovsky First Piano Concerto Score Music Analysis
mathjax: true
---

In the last post, we discussed what happens to charged particles when they're released in a magnetic field, but that isn't all that useful if we don't know where magnetic fields come from! In this post, we'll deal with just that question, and then discuss a couple fun problems. 

Just as charges were affected by magnetic fields only when they were moving, charges create magnetic fields only when they move and create a current. 

It turns out that a current creates a magnetic field in the following fashion, known as the Biot-Savart Law:

$$d\bf{B} = \dfrac{\mu_{0}I}{4 \pi} \dfrac{d\bf{l} \times e_{0}}{\bf{r}^2}$$

This is definitely more involved than the equation for the electric field, so to get a feel for it it's probably best to begin with an example: the magnetic field of an infinite wire.

![image]({{site.baseurl}}/images/magnetism-ii/infinite_wire.png)


Notice the $\frac{1}{2\pi R}$ term in the denominator. That is precisely the circumference of a circle of radius R centered around that point, which is suspiciously similar to the $\dfrac{1}{4\pi R^2}$ term found in Couloumb's law, which corresponds with the area of a Gaussian surface. Perhaps we could say something about the sum magnetic field along a path in terms of the enclosed current, just as we found the sum of the electric field through a surface (the electrix flux) in terms of the enclosed charge?

Before we analyze this result, I should mention that we can say something about the sum of the magnetic flux through any closed surface, called Gauss' law for magnetism, which states that $\oint \bf{B} \cdot d\bf{A} = 0$ at all times. Imagining field lines as "holding" flux, note that the field lines of any individual current don't stop or end anywhere. Thus, any flux line entering a surface also leaves it. (This isn't the most rigorous proof; I think something more formal would require vector calculus above my current level)


Now let's turn our attention back to the sum around a loop: Ampere's Law:

$$\oint \bf{B} \cdot d \bf{l} = \mu_{0} I$$

I here is the current piercing the surface enclosed by the loop. Which surface should we pick though? There are an infinite number of surfaces bounded by any given loop. Well, in the case of static currents, a current may not terminate in the middle of nowhere (as that would violate the conservation of charge). Assuming all current carrying wires are infinite, there are two options. A current could penetrate all possible surfaces, or penetrate only a select few.  Suppose a current were to penetrate one surface but not another. Well, since the wire is infinite, this would imply that the current turns around before then. This then creates a corresponding negative contribution to the enclosed current, and so, the amount of current penetrating the surface is unchanged. 

Keep in mind that this argument works only for infinite wires. For finite or semi-infinite wires, this is not necessarily true. It turns out that we'll need to modify Ampere's law for this case, but that's a topic for another time.



It's not too difficult to show that this holds in the simple case of a singular current and a circular loop. $\oint \bf{B} \cdot d\bf{r}$ is just $2 \pi RB$, as the field is always azimuthal (i.e. perpendicular). Since $B = \dfrac{\mu_{0}I}{2 \pi R},$ $2 \pi RB = \mu_{0}I$ 

We now must establish that the choice of loop does not matter, and that outside currents do not affect the integral, as shown in the two diagrams below. (If we establish that the choice of loop does not matter, superposition gives us that the law holds for arbitrary number of currents inside)

To show the loop does not matter, we set up the full integral in polar coordinates, and the R terms end up cancelling, giving us the same result as the circular loop. To show that outside loops don't matter, we note that $\oint d\varphi$ ends up being zero when the current is outside the loop, as shown in the diagram

![image]({{site.baseurl}}/images/magnetism-ii/ampere_derivation_1.png)
![image]({{site.baseurl}}/images/magnetism-ii/ampere_derivation_2.png)

To end, we'll return to Biot-Savart and deal with a fun question, the magnetic field due to a loop de loop wire (If you object that the wire is finite and causes a changing electric field, suppose that a wire connects the two endpoints. This creates no B field at the origin and avoids said problem).

![image]({{site.baseurl}}/images/magnetism-ii/problem_statement.png)

We'll start by assuming that the wire always points in the azimuthal direction. This obviously isn't correct—otherwise the radius wouldn't increase—but it's a good enough approximation to start, and actually gives us a nice analytic answer.

![image]({{site.baseurl}}/images/magnetism-ii/loop_simple.png)

Now, we account for the slope of the curve. Assuming the radius increases linearly with distance, we write down an equation for the loop in polar coordinates. Letting $k = \dfrac{b-a}{2 \pi N}$

$$r = a + k \theta$$


To find the angle, we're going to need to find the slope at any given point in time, which will allow us to get the angle between it and the perpendicular. So, we convert to rectangular:

$$x = rcos(\theta) = acos(\theta)+ k\theta cos(\theta)$$

$$y = rsin(\theta) = asin(\theta)+ k\theta sin(\theta)$$


Then differentiate each with respect to theta, and then divide to find our slope.
$$\dfrac{dx}{d\theta} = -asin(\theta) + k(cos(\theta) - \theta sin(\theta))$$

$$\dfrac{dy}{d\theta} = acos(\theta) + k(sin(\theta) + \theta cos(\theta))$$

$$\dfrac{dy}{dx} = \dfrac{\frac{dy}{d\theta}}{\frac{dx}{d\theta}} = \dfrac{acos(\theta) + k(sin(\theta) + \theta cos(\theta))}{-asin(\theta) + k(cos(\theta) - \theta sin(\theta))}$$


We're almost there! We need to find the angle between the tangent line at a given point (whose slope we have just found), and the perpendicular from the origin to that point. As shown in the diagram this works out to be $$\theta  - tan^{-1}(\frac{dy}{dx}) - 90^{\circ}$$

![image]({{site.baseurl}}/images/magnetism-ii/loop_hard.png)

We know keep the same integral as before, adding in a term of $cos(\varphi)$ (cosine because this is the angle from 90)

The final calculation can be found in this [desmos graph](https://www.desmos.com/calculator/5zmn880cfv):


I hope you enjoyed, and thank you so much for reading!

