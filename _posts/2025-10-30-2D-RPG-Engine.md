---
layout: post
title: 2D RPG Engine
subtitle: Written in java
cover-img: /assets/img/2D-RPG-Engine/background-meadow.png
# cover-img: /assets/img/2D-RPG-Engine/test.png
thumbnail-img: /assets/img/thumb.png
share-img: /assets/img/path.jpg
tags: [Project, Java]
# author: Ricardo Kraft
---

## Intro

This is by far my biggest private project I have been working on. I used this project mainly to learn how to code 
and additionally build something fun for me. With the engine I currently building my own Pokemon game clone. As 
bases I took mostly assets from the older Pokemon Games such as 
[Pokemon Heartgold & Soulsilver](https://en.wikipedia.org/wiki/Pok%C3%A9mon_HeartGold_and_SoulSilver) for 
the [Nintendo DS](https://en.wikipedia.org/wiki/Nintendo_DS) and openly available assets made by fans of the game.

The purpose of this post is not to about the game but about the engine and what it can do.

## Features

There are a bunch of features this engines already provides. I am gonna go ahead and highlight a few of these I consider
worth mentioning.

### Windows

The engine has two parallel threads each running one of the two windows used for building the game. The UI thread
controls the left editor window and offer several tweaking options and tooling while the game thread controls the right 
window which represents the game's state with its map, characters in-game UI, loading, saving, etc. . 
For the left window I use [javafx](https://openjfx.io/) and for the right window an early version [OpenGL](https://www.khronos.org/opengl/) 
for rendering.

![Alt text](/assets/img/2D-RPG-Engine/windows.png)

### Painting

- Painting with grid and without
- Palette
- Auto tiling
- Layers, Grid
  
<div align="center">
  <video width="700" controls>
    <source src="/assets/img/2D-RPG-Engine/test-battle.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
</div>


### Collision

### Scripting

### Events

### Persistence

