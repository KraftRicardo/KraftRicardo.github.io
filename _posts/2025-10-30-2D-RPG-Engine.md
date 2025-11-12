---
layout: post
title: 2D RPG Engine
subtitle: Writing the Tools Myself
cover-img: /assets/img/2D-RPG-Engine/background-meadow.png
# cover-img: /assets/img/2D-RPG-Engine/test.png
thumbnail-img: /assets/img/2D-RPG-Engine/2d-engine-icon.png
share-img: /assets/img/2D-RPG-Engine/2d-engine-icon.png
tags: [Project, Java, Game]
# author: Ricardo Kraft
---

This **2D RPG engine written in Java** is by far my biggest private project so far. I started this project primarily as 
a way to learn programming while building something fun for myself. Using the engine, I’m currently developing a 
Pokémon Fan game. As a foundation, I’ve used assets from older Pokémon titles like [Pokémon HeartGold & SoulSilver](https://en.wikipedia.org/wiki/Pok%C3%A9mon_HeartGold_and_SoulSilver) for the [Nintendo DS](https://en.wikipedia.org/wiki/Nintendo_DS), combined with various open fan-made assets.  

The purpose of this post is not to showcase the game itself, but rather to highlight the **engine**, what it does, and how it works. The engine already includes a wide range of functionality. Below are some of the highlights.

## Windows

The engine runs two parallel threads, each managing one of the two main windows used during development. The **Editor Window (left)** runs on the UI thread, powered by [JavaFX](https://openjfx.io/). It provides access to numerous tools and customization options for editing game content. The **Game Window (right)** runs on a separate game thread and uses an early version of [OpenGL](https://www.khronos.org/opengl/) for rendering. This window displays the active game world, including maps, characters, user interfaces and covers utilities such as input handling and save/load mechanics.  

![Editor and Game Windows](/assets/img/2D-RPG-Engine/windows.png)

## Mapping

The mapping system supports **10 layers for each of 10 height levels**, allowing fine-grained control over world design. It provides **free camera movement**, **zoom**, and flexible **layer opacity** controls for better visualization. In addition, you can toggle overlays to display **colliders**, **scripts**, **grids**, and other visual indicators such as **names**, **positions**, and **gizmos**.

<div align="center">
  <video width="700" controls>
    <source src="/assets/img/2D-RPG-Engine/2d-engine-videos-layers-and-toggles.mp4" type="video/mp4">
  </video>
</div>

## Painting

The painting tool enables classic **tile-based map editing**, inspired by the design of the original Pokémon games. You can paint directly on the tile map and also place objects **off-grid** for a more natural look. It supports the essential **editing tools** such as select, move, brush, and copy, all integrated into a **dual-camera system**, where one is focused on the game map and the other on the tile and object palettes area. The engine also supports **auto-tiling** for elements like water and walls.  

<div align="center">
  <video width="700" controls>
    <source src="/assets/img/2D-RPG-Engine/2d-engine-videos-painting.mp4" type="video/mp4">
  </video>
</div>

## Collision

The engine allows to attach or remove **colliders** from map objects. By using shared attributes among copied objects the engine applys collider changes to similar objects automatically. This property can but must not necessarily apply to similar attributes such as scale, opacity, trigger colliders and scripts.

<div align="center">
  <video width="700" controls>
    <source src="/assets/img/2D-RPG-Engine/2d-engine-videos-collider.mp4" type="video/mp4">
  </video>
</div>

## Scripting

Each map object can have **scripts** attached to define its behavior. For example, the video below demonstrates **triggered animations** and **dialogues** that occur during interactions or on-collision events.

<div align="center">
  <video width="700" controls>
    <source src="/assets/img/2D-RPG-Engine/2d-engine-videos-scipted-objects.mp4" type="video/mp4">
  </video>
</div>

The scripting system provides **real-time access** to object data and supports **on-the-fly changes** to dialogue and logic. Developers can easily adjust **NPC paths** using moveable nodes, and even change the **animator** (sprite animation set) dynamically during gameplay.

<div align="center">
  <video width="700" controls>
    <source src="/assets/img/2D-RPG-Engine/2d-engine-videos-npc-script.mp4" type="video/mp4">
  </video>
</div>

## In-Game UI

The engine supports **custom in-game user interfaces**, which are implemented directly in code. It also provides a collection of **built-in components** such as boxes, labels, and other UI elements, as shown below. Most of the menus displayed are still **prototypes** and will receive additional polish and content.

<div align="center">
  <video width="700" controls>
    <source src="/assets/img/2D-RPG-Engine/2d-engine-videos-ingame-ui.mp4" type="video/mp4">
  </video>
</div>

## Thank You

A big **thank you** goes out to one of my dear friends who helped me get this project started. You can check out his work at [putterer.net](https://putterer.net/).