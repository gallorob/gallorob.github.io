---
layout: default
title:  A weirdly succint guide to JupyterLab
---

# Jupyter Lab or: how I learned to stop writing scripts and love notebooks

As a Python programmer, the first thing you're taught is how to write scripts. And sure, they're cool and all, but sometimes you *really* just need something better. Something more interactive. Something that isn't a REPL in a debugger.

Well, Jupyter will scratch that itch. No, not the planet, the [Project Jupyter](https://jupyter.org/).

But how does one set up an environment that closely resembles a professional IDE (like PyCharm) whilst taking advantage of the beauty that is developing on notebooks? Sure, Visual Studio Code supports notebooks, but really: why install *more* software when your browser of choice will do just fine?

This short (very, very short) guide will show you how I set up my own Jupyter environment to program with ease.

## The basics

First of all, you'll need to install Jupyter Lab. The simplest way to do this is by first creating a Conda environment
```
conda create -n jlab python=3.7
```
, activating it
```
conda activate jlab
```
, installing Jupyter Lab,
```
conda install -c conda-forge jupyterlab
```
and testing it by launching it
```
jupyter lab
```
And honestly, that already covers like 50% of the guide.

## The extensions

"But wait", I hear you asking "This doesn't look like an IDE at all!". Well, first of all, of course it doesn't if you don't change the style to the Dark Theme. Secondly, that's what extensions are for! I suggest you first enable them by clicking `Enable` in the `Extension Manager` tab on the left.

After that, close the browser tab with Jupyter Lab and peruse some fine selections of extensions on [GitHub](https://github.com/mauhai/awesome-jupyterlab) or look them up on your Search Engine of choice.

Personally, I installed these:
```
conda install -c conda-forge jupyterlab-git ipywidgets theme-darcula jupyterlab-spellchecker jupyterlab-drawio jupyterlab_code_formatter jupyterlab-lsp python-lsp-server jupyterlab-notifications
pip install aquirdturtle_collapsible_headings
```

Basically, at the end of all this you will have:
- Git integration
- The Darcula theme (which is *obviously* superior to any other theme)
- A spellchecker and code autocompletion
- A code formatter
- Draw.io tab to create diagrams on the fly (or comics if you have enough patience and artistic skills)

But wait, we're not done yet!

For `jupyterlab_code_formatter`, you can enable the option to automatically format a file when saving: go to `Settings -> Advanced Settings Editor -> Jupyterlab Code Formatter` and add this to the `User Preferences`:
```
{
    "formatOnSave": true
}
```

For `python-lsp-server`, you can have continuous hinting enabled: go to `Settings -> Advanced Settings Editor -> Code Completion` and add this to the `User Preferences`:
```
{
    "continuousHinting": true
}
```

Now you're done!

{% include static_image.html image="posts/jlab/screen.png" alt="final result" %}

## But I like scripts too!

If you feel like you can't write scripts with Jupyter Lab, you're wrong.

If you think you can't write a Python package or library with Jupyter Lab, you're only partially incorrect. Here's the deal, just install your package in develop mode (usually something like `python setup.py develop`): this will allow you to see changes to your script code in real time (although sometimes this doesn't work and you need to restart the Kernel 🤷‍♂️).

## Make it look professional

If you are lazy like me, you may be bothered by having to type in the shell everytime the same commands just to get the browser tab open. Well, as for everything else in life, laziness yields innovation.

If you are on a Windows machine (if not, adapt the following commands to your OS) you can create a `.bat` file with the following commands:
```
call conda activate jlab
cd /move/to/to/your/project/path
call jupyter lab
```
and save it somewhere. Then you'll just need to double-click it and *voilà*, laziness prevails!

## But I hate my browser

Fair enough, then you may be interested in [Jupyter Lab Desktop](https://github.com/jupyterlab/jupyterlab-desktop). It works great, as long as you point it to the right Python executable.


## Meh, not really *that* cool

Sure, not everyone will like notebooks. Just like not everyone will like scripts.

If you don't like them both, well... Check [OpenCodeBlocks](https://github.com/MathisFederico/OpenCodeBlocks) out? Dunno, looks interesting to me.