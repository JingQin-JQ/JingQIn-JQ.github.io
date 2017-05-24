---
layout: post
title: Build virtual environment
tags: 
- ZSH Study
---
Build a virtual environment for python3.6

Follow instructions from The Hitchhiker’s Guide to Python!
<http://python-guide-pt-br.readthedocs.io/en/latest/dev/virtualenvs/>

#### 1.First step : install virtualenv.

Virtualenv is a tool to create isolated Python environments. I already have it when install another virtual environment for python 2.7 in my Mac.

```
pip install virtualenv
virtualenv --version
```
My virtualenv version is 15.1.0

#### 2.Create a new virtual environment for python 3.6.
I would like to have my new virtual environment under my home directory.
And because I already got a virtual environment for my python 2.7 called venv2, so this time I am going to build a venv3.

*  Install python3

I installed python3.6 by homebrew at ```/usr/bin/```

```
brew install python3
```
* Create the virtual environment 

```
cd ~
virtualenv -p /usr/bin/python3.6 venv3
```
#### 3.Activate the virtual environment.

```
source venv3/bin/activate
```
The name of the current virtual environment will now appear on the left of the prompt:
So I know it’s active.
```
(venv3) ➜  ~
```
#### 4. Install necessary packages.
Here any package that I install using pip will be placed in this venv3.

```
pip install jupyter
```
#### 5.Deactivate venv3
When I am done with my work in venv3, I need to deactivate it.

```
deactivate
```
#### 6.Last part:
The comments to activate venv3 is troublesome. So I change it by add 
```
alias venv3="source ~/venv3/bin/activate
``` 
into 
```~/.zshrc``` by ```vim```.

_BTW: In Vim, type"i" to activate insert mode, type"esc" key followed by ":wq" to quit vim_


Now only type in ```venv3``` will get the virtual environment for python3.6 working!


