# Data-Logic-Fractal Framework for Classifying Astronomical Bodies

> **Status**: Active RFC (Request for Comments)

> **Version**: 0.1.0

> **Author**: BurningHot687

> **Feedback**: Please open a GitHub issue or pull request to suggest changes or submit edge cases

## Overview
The Data-Logic-Fractal (DLF) framework is a hierarchical classification system that uses a self-similar classification to organize astronomical bodies. It is meant to mark a clean delineation between the internal state and external state of an object.

## Part 1: Planets
The IAU definition of a planet has caused major controversy among the general public and several astronomers. Therefore, we will use a different definition for a planet.
### Geophysical vs Dynamic Definition
To maximize usability and ease-of-switching, there will be two definitions. We will now define a **Dromot**.

### Dromot Definition
A dromot is any celestial body that is between $10^{21} \text{kg}$ and $13 \text{Jupiter masses}$ exactly. This definition is arbitrary; however, this is due to the need for classification in a pragmatic stance. The lower limit represents the approximate lower bound for hydrostatic equilibrium and the upper limit represents the mass limit for deuterium fusion. To illustrate: Pluto, Earth, Venus, and Jupiter are all dromots. The name was based off of *dromos*, which was chosen because it was somewhat synonymous with *planetes*.

### Dromot Prefixes
To provide more clarity, there are prefixes to which you can include before dromot.
1. **Auto**dromot: A dromot which does not orbit a stellar object (star, pseudostar, etc). This includes rogue planets and JuMBOs.
2. **Stellar** dromot: A dromot which orbits a stellar object.
3. **Sol**dromot: A dromot which orbits Sol (the Sun).
4. **Exo**dromot: A dromot which orbits a stellar object within the Milky Way but *not* Sol.
5. **Extro**dromot: A dromot which orbits a stellar object outside the Milky Way (e.g. a star or pseudostar in the Andromeda galaxy, or intergalactic bodies).
6. **Sub**dromot: A dromot orbiting a dominant body where the barycenter is within the dominant body (e.g. a satellite).
7. **Bary**dromot: A dromot orbiting a dominant body where the barycenter is outside the dominant body (e.g. Pluto and Charon).

### Planet Definition
Under this new definition of dromots, we may now define a **Planet** as a dromot that satisfies **two** dominance equations.

1. **Margot's Planetary Discriminant ($\Pi$)**: The body must be massive enough to clear its orbital zone within the lifetime of its host star [[1]](#1-margot-2015).
$$\Pi = \frac{M_p}{M_{\text{Clear}}} > 1$$

Where the required clearing mass ($M_{\text{Clear}}$) is calculated using the star's mass ($M_\star$) and the planet's semi-major axis ($a$):
$$M_{\text{Clear}} = 3 \times 10^{-4} \cdot M_\star^{5/8} \cdot \left( \frac{a}{1 \text{ AU}} \right)^{9/8}$$

2. **Soter's Planetary Discriminant ($\mu$)**: The body must dynamically dominate the other objects sharing its orbital zone by a factor of at least 100 [[2]](#2-soter-2006).
$$\mu = \frac{M}{m} > 100$$

Where $M$ is the mass of the candidate body and $m$ is the total collective mass of all other bodies that cross or share its orbital zone (excluding its own satellites).

### Pseudoplanet Definition
An astronomical body is classified as a **Pseudoplanet** if it is a dromot that satisfies only **one** of the two planetary dominance criteria. This classification is primarily applied in two scenarios:

1. **Observational Limitation**: The body satisfies Margot's criterion ($\Pi > 1$), but Soter's criterion ($\mu > 100$) cannot be calculated due to a lack of observational data regarding local debris (e.g., most unmapped exoplanetary systems).
2. **Environmental Boundary**: The body possesses the physical mass required to clear an orbit over time ($\Pi > 1$), but currently resides in a highly dense debris field that prevents it from satisfying the environmental census ($\mu < 100$).

## References

#### <a name="1-margot-2015"></a>[1] Margot, J.-L. (2015)
A Quantitative Criterion for Defining Planets. *The Astronomical Journal*, 150(6), 185.
* [View Source on IOPscience](https://iopscience.iop.org/article/10.1088/0004-6256/150/6/185)
* [View Free Preprint on arXiv](https://arxiv.org/abs/1507.06300)
* [View Record on NASA ADS](https://ui.adsabs.harvard.edu/abs/2015AJ....150..185M)

#### <a name="2-soter-2006"></a>[2] Soter, S. (2006)
What is a planet? *The Astronomical Journal*, 132(6), 2513–2519.
* [View Source on IOPscience](https://iopscience.iop.org/article/10.1086/508861)
* [View Free Preprint on arXiv](https://arxiv.org/abs/astro-ph/0608359)
