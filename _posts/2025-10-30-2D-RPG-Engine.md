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

### Mapping

The engine offers 10 layers for each of the 10 height levels. It support free camera movement & zoom. Tweaking
of several opacity values and layer highlighting. It allows to toggle to show the colliders, script elements, the grid
and highlighters such as position, nametags and gizmos.

<div align="center">
  <video width="700" controls>
    <source src="/assets/img/2D-RPG-Engine/2d-engine-videos-layers-and-toggles.mp4" type="video/mp4">
  </video>
</div>

### Painting

The engine allows you to paint on on a given tile map, to create the original Pokemon game flare of tile based maps.
Additionally now, objects can now also be placed off-grid giving more flexibilit to the user and creating more flare.
Apart from the basics tools of select, move, brush, copy etc. the engine works with a 2 camera view system where one
points to the map and the other to the space where all the object/tile palletes are saved. The engine also features auto 
tiling for water and wall tiles.

<div align="center">
  <video width="700" controls>
    <source src="/assets/img/2D-RPG-Engine/2d-engine-videos-painting.mp4" type="video/mp4">
  </video>
</div>

### Collision & MD Follower Pathing

### Scripting

### Events

### Persistence

