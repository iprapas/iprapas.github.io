+++
date = "2020-05-29"
draft = false
title = "Easiest way to use Python virtual environments"
toc = true
categories = ["Software Development", "Best practices", "Beginner"]
tags = ["python", "virtualenv"]
+++

**Disclaimer**: I know what your are thinking "That title is a clickbait". I feel a little bit bad about it. But on second thought, I don't have regrets. 

It is the easiest way I know and I dare you to leave a comment if you know a better way.

## What are virtual environments

Instead of adding new python packages to your system installation, you add them to a virtual installation site-packages.

## Why should I use them?

It is best practice to develop different projects with isolated packages. If that doesn't convince you, think about the case where you have to install different versions of a library, because of different dependencies.

Personal note: For me, the most useful case is using python in an environment where I don't have sudo privileges. Virtual environments let me install almost every python library I need. When this is not enough, I suggest to have a look into containers (Docker). Maybe in a future post, I'll talk about them.

## Let's dive in 

My preferred method is to use `virtualenv` and `virtualenvwrapper`. I initially found about them in [pyimagesearch](https://www.pyimagesearch.com/), which is a very nice site about practical computer vision.

### Step 1 (Installation)

First, thing you have to do is install virtualenv and virtualenvwrapper in your system-wide python installation.

```python
pip install virtualenv virtualenvwrapper
``` 

### Step 2 (Installation)

Now you need to make your shell aware of the existence of these libraries. Add the following lines to your `~/.bashrc`:

```bash
export WORKON_HOME=$HOME/.virtualenvs
export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python3
source /usr/local/bin/virtualenvwrapper.sh
```

For the changes to be available you have to:
1. Either restart the terminal (which will load ~/.bashrc)
2. Or source the changes (preferraby)

```bash 
source ~/.bashrc
```

## Usage

Setup is over! You can go ahead and use virtual environments.

Make a new virtual environment with `mkvirtualenv`

```bash
mkvirtualenv myenv
```

Your terminal has now a prefix `(myenv)`. This means that if you install something with pip, it will be installed in that virtual environment and not in the system-wide installation. 

To change virtual envs, we use the command `workon`. E.g.
```bash
# create a new env
mkvirtualenv myenv1
# change back to the previous
workon myenv
```

Here is a screenshot of my output running these commands.

![screenshot](/blog/python-virtualenv/screenshot.png)

Notice the prefix of the terminal changing from nothing $\rightarrow$ (myenv) $\rightarrow$ (myenv1) $\rightarrow$ (myenv).

That's all! Now you know how to use virtual envs to better isolate your python projects. To learn more, visit the [virtualenvwrapper documentation](https://virtualenvwrapper.readthedocs.io/).



