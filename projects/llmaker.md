---
layout: post
title: LLMaker
---

{% include image.html url="https://github.com/gallorob/llmaker" image="projects/llmaker/llmaker_gui.png" %}

## tl;dr:
LLMaker is a mixed-initiative tool that lets users design video game levels for [Dungeon Despair](https://github.com/gallorob/dungeon-despair) using large langauge models to parse edit commands and stable diffusion models to generate graphical assets.

## LLMaking the LLMaker

LLMaker is my ongoing project for my PhD thesis focusing on the impact of using LLMs in mixed-initiative co-creation. It's written in Python with PyQt6 for the GUI elements. Its releases can be installed on Windows, MacOS, and Debian-based Linux distros.

I started developing the application at the beginning of my PhD. LLMaker assists designers to create levels for the videogame [Dungeon Despair](https://github.com/gallorob/dungeon-despair), which I built alongside the application itself. The game is a reverse dungeon crawler inspired by Darkest Dungeon and built with pygame. The domain of Dungeon Despair is shared between the tool and the game itself, and is essentially a collection of PyDantic game objects and Python methods to manipulate them. These functions all have the `@AILibFunction` decorator from [`gptfunctionutil`](https://pypi.org/project/gptfunctionutil/) to be easily integrated in a tool calling pipeline.

In LLMaker, users are free to request edits to be made to the level (within domain constraints) or just ask questions about the level and converse with the LLM. The interface has a level minimap, an encounter preview, and a chat area.

The interaction loop is as follows:
1. The user sends a message;
2. The LLM processes the message and calls the right tools to execute the changes requested;
3. The backend system updates the level accordingly;
4. The LLM summarizes the changes back to the user;
5. The interface is updated to reflect the level changes.
If the change to the level cannot be completed, a functional error message is returned to the LLM, which can then either retry the change or just let the user know that the edit failed.

Graphical assets are 2D images generated using stable diffusion. The model currently implemented is a Stable Diffusion 1.5 model finetuned on RPG assets, and two different LoRAs are loaded to generate sprites and backdrops in the style of Darkest Dungeon. 

<!-- While originally I was using GPT 3.5 Turbo as a language model, at some point I switched to open source models hosted locally.  -->

## The Research Bit

### Publications
> [R. Gallotta, A. Liapis and G. Yannakakis, "Consistent Game Content Creation via Function Calling for Large Language Models," _2024 IEEE Conference on Games (CoG)_, Milan, Italy, 2024, pp. 1-4, doi: 10.1109/CoG60054.2024.10645599.](https://ieeexplore.ieee.org/abstract/document/10645599)
```bibtex
@inproceedings{gallotta2024consistent,
    author    = {Gallotta, Roberto and Liapis, Antonios and Yannakakis, Georgios N.},
    title     = {Consistent Game Content Creation via Function Calling for Large Language Models},
    year      = {2024},
    doi       = {10.1109/CoG60054.2024.10645599},
    booktitle = {Proceedings of the IEEE Conference on Games (CoG)},
    pages     = {1-4}
}
```

> [R. Gallotta, A. Liapis and G. Yannakakis, "LLMaker: A Game Level Design Interface Using (Only) Natural Language," _2024 IEEE Conference on Games (CoG)_, Milan, Italy, 2024, pp. 1-2, doi: 10.1109/CoG60054.2024.10645626.](https://ieeexplore.ieee.org/abstract/document/10645626)
```bibtex
@inproceedings{gallotta2024llmaker,
    author    = {Gallotta, Roberto and Liapis, Antonios and Yannakakis, Georgios},
    title     = {LLMaker: A Game Level Design Interface Using (Only) Natural Language}, 
    year      = {2024},
    doi       = {10.1109/CoG60054.2024.10645626},
    booktitle = {2024 IEEE Conference on Games (CoG)}, 
    pages     = {1-2},
}
```

> [Gallotta, R., Liapis, A., & Yannakakis, G.N. (2025). FREYR: A Framework for Recognizing and Executing Your Requests. _ArXiv_, abs/2501.12423.](https://arxiv.org/abs/2501.12423)
```bibtex
@article{gallotta2025freyr,
    author  = {Roberto Gallotta and Antonios Liapis and Georgios N. Yannakakis},
    title   = {FREYR: A Framework for Recognizing and Executing Your Requests}, 
    year    = {2025},
    journal = {ArXiv preprint arXiv:2501.12423},
}
```

> [Gallotta, R., Liapis, A., Yannakakis, G.N. (2025). The Importance of Context in Image Generation: A Case Study for Video Game Sprites. In: Machado, P., Johnson, C., Santos, I. (eds) _Artificial Intelligence in Music, Sound, Art and Design. EvoMUSART 2025_. Lecture Notes in Computer Science, vol 15611. Springer, Cham. https://doi.org/10.1007/978-3-031-90167-6_5](https://link.springer.com/chapter/10.1007/978-3-031-90167-6_5)
```bibtex
@inproceedings{gallotta2025importance,
author    = {Gallotta, Roberto and Liapis, Antonios and Yannakakis, Georgios N.},
editor    = {Machado, Penousal and Johnson, Colin and Santos, Iria},
title     = {The Importance of Context in Image Generation: A Case Study for Video Game Sprites},
year      = {2025},
doi       = {10.1007/978-3-031-90167-6_5},
booktitle = {Proceedings of the Artificial Intelligence in Music, Sound, Art and Design (EvoMUSART) Conference},
pages     = {66--81},
publisher = {Springer Nature Switzerland},
}
```
