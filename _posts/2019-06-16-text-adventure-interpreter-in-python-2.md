---
layout: post
title:  "Text Adventure Interpreter in Python - 2"
date:   2019-06-16
categories: [python, game]
---
The hope for this week is to set up the basic command line interface and parser for the game file. The game will only be accepting a few commands for navigating (`go north, south, east, west`) and interacting with objects (mostly `pick up` and `use` items). The game file will be structured as a JSON file indicating the map, the description of different rooms, as well as which objects are to be interacted with.

### 0. The Project Structure

The project structure is going to be relatively simple. The entry point of the program will be a file called `taip.py`, which is just 

### 1. The Command Line

The command line handles user inputs and is essentially a very simple prompt that takes commands and manipulates the internal representation of the game and its status accordingly. it's very easy to start the interface and also since the limited number of commands we need to implement, it's relatively easy to write. 

> starting the prompt: `command.py`

```python
if True:
    print("hey")

```