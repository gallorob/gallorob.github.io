---
layout: post
title: 'Space Engineers AI Spaceship Generator'
---

Lorem ipsum.

{% include image.html url="https://github.com/GoodAI/space-engineers-ai-spaceship-generator" image="projects/pcgsepy/pcgsepy_webui.jpg" %}

## The Research Bit
The AI Spaceship Generator consists of several components, allowing it to generate both functional and aesthetically-pleasing spaceships for Space Engineers. The basis is a rule-based procedural content generation algorithm that generates working ships, which is combined with an evolutionary algorithm that optimises their appearance, resulting in a novel hybrid evolutionary algorithm. The basic heuristics for the evolutionary algorithm to optimise were derived by analysing the properties of spaceships available on the Space Engineers’ Steam Workshop page.

This is then combined with a novel algorithm that finds a diverse set of spaceships, making more choices available. Finally, we have built a graphical interface for these algorithms so that you can influence the spaceship generator’s choices, alongside another novel algorithm that tries to tune the system to better follow the your ideas.

Starting from an initial population of vessels, you can select a spaceship to "evolve" - the underlying evolutionary algorithm then "mutates" this, creating new spaceships with similar properties (shape, size, etc.). This process can be repeated to continuously generate new spaceships.

### Publications
> [Gallotta, R., Arulkumaran, K., & Soros, L. B. (2022). Evolving Spaceships with a Hybrid L-system Constrained Optimisation Evolutionary Algorithm. In _Genetic and Evolutionary Computation Conference Companion_.](https://dl.acm.org/doi/abs/10.1145/3520304.3528775)
```bibtex
@inproceedings{gallotta2022evolving,
    author      = {Gallotta, Roberto and Arulkumaran, Kai and Soros, L. B.},
    title       = {Evolving spaceships with a hybrid L-system constrained optimisation evolutionary algorithm},
    year        = {2022},
    publisher   = {Association for Computing Machinery},
    doi         = {10.1145/3520304.3528775},
    booktitle   = {Proceedings of the Genetic and Evolutionary Computation Conference (GECCO) Companion},
    pages       = {711–714}
}
```

> [Gallotta, R., Arulkumaran, K., & Soros, L. B. (2022). Surrogate Infeasible Fitness Acquirement FI-2Pop for Procedural Content Generation. In _IEEE Conference on Games_.](https://ieeexplore.ieee.org/document/9893592)
```bibtex
@inproceedings{gallotta2022surrogate,
    author    = {Gallotta, Roberto and Arulkumaran, Kai and Soros, L. B.},
    title     = {Surrogate Infeasible Fitness Acquirement FI-2Pop for Procedural Content Generation}, 
    year      = {2022},
    volume    = {},
    number    = {},
    doi       = {10.1109/CoG51982.2022.9893592},
    booktitle = {Proceedings of the IEEE Conference on Games (CoG)}, 
    pages     = {500-503}
}
```

> [R. Gallotta, K. Arulkumaran and L. B. Soros, "Preference-Learning Emitters for Mixed-Initiative Quality-Diversity Algorithms," in _IEEE Transactions on Games_, vol. 16, no. 2, pp. 303-316, June 2024, doi: 10.1109/TG.2023.3264457.](https://ieeexplore.ieee.org/document/10094001)
```bibtex
@article{gallotta2024preferencelearning,
    author  = {Gallotta, Roberto and Arulkumaran, Kai and Soros, L. B.},
    title   = {Preference-Learning Emitters for Mixed-Initiative Quality-Diversity Algorithms}, 
    year    = {2024},
    journal = {IEEE Transactions on Games}, 
    volume  = {16},
    number  = {2},
    doi     = {10.1109/TG.2023.3264457},
    pages   = {303-316}
}
```