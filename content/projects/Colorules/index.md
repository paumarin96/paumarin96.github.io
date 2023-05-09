---
title: "Colorules"
date: 2022-02-03T18:33:34+01:00
draft: false
tags:
- Game Jam
- Game project

summary: "Gamejam puzzle game about interacting with colors"

---

Colorules is a small game made in the Game Gen Game jam, by a team of 5 people.

This project served me as my first game jam, and I used it to test myself in a time-constrained environment.

The theme of the jam was to make a game with 3 rules. In our case, we made a game were color combinations make the 3 rules, and you control a ball with your mouse:

- If you touch the same color as your, you loose.
- Touching a different color swaps the colors.
- You can destroy objects by touching them with their complementary color

{{< youtube QpcAb4yKZ8w >}}

*A gameplay uploaded by a player*

## My contributions to this project

I was the programmer for the main color mechanics, while movement and the general flow of the game was made by my collegues.
The main problem I faced was detecting the collision between the player, and the line that leaves behind. 
As this line is traced with Unity's line renderer, there's no way we can do physics-based collision detection. 

My solution was to use a small render texture that captures the center of the screen. Because the player is always in center,
I can sample the middle pixel of the texture to detect which color the player is on top of.

This is an expensive solution, as reading data from the GPU on the CPU is very expensive, but due
to the nature of a game jam, I went along with it.
 In the future, I would like to rewrite this using another solution that isn't so expensive, and is also compatible with WebGL.




{{< button href="https://bitplayy.itch.io/colorules" target="_self" >}}
Play it now on Itch.io
{{< /button >}}