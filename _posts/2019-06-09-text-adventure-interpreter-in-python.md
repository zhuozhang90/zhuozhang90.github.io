---
layout: post
title:  "Text Adventure Interpreter in Python - 1"
date:   2019-06-09
categories: [python, game]
---

This is a project I'm working on as the final project for one of the classes for school. The idea came from old-school text adventures but this project is not going to be a full-featured interpreter but instead I'll only implement some basic functionalities like parsing the game file, save/restore, score keeping as well as an optional voice input.

I have been following Thorsten Ball's "[Interpreter in Go](https://interpreterbook.com/)" book and the chapters about parsing input really made me wonder if I could implement something similar for other text-based tools. My initial thoughts are to do something about natural languages but I guess text adventures can also be seen as natural language based projects.

Below is a list of components I plan to implement for this interpreter. As I mentioned earlier I'm only going to write the basic components and leave the rest for maybe the future. There are many interpreters for different formats of text adventures that can be found on the [IFDB](https://ifdb.tads.org/) website.

- reading game files with a parser
- internal representation of the game map
- player navigation in the map
- object interaction
- score keeping
- save/restore with a save file
- (optional) voice input that parses natural language
- (optional) test files

Since I'll only have about 9 weeks to finish the project I might not even implement all of the non-optional components like score keeping or save/restore. The point of the whole project is to teach myself how parsers work and data structures. Efficiency is also not a priority as I'll be using vanilla Python libraries and collections as much as possible and won't be spending too much time optimizing speed.

I also plan to make this project as modular as I can if time permits. This will make it easier to expand the project if anyone plans to do so in the future, or if any components can be reused for other projects.
