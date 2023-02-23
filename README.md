# Unity Roguelike Project

A sort of blog talking about what I've been working on in my Roguelike game.
Doing it in my spare time as a fulltime student, so progress will be kind of slow I just wanted a place to keep track of what I was
working on and learning about.

<details>
<summary> <h3> Jan 28, 2023</h3> </summary>
<br>
Decided to start my Godot project over in Unity becauase I wanted to get some experience with a more widely used engine.

So far I've gotten a basic PlayerController set up, and animated an attack. Can you tell I'm not an animator?

![](https://github.com/TrevorWM/TrevorWM/blob/main/DudeShmoovin.gif)
</details>


<details>
<summary> <h3> Jan 29, 2023 </h3> </summary>
<br>
I found out that Unity had an updated Input Management system, and I wanted to swap my code over to that
as it looked easier to use and just kind of jived with my brain better. I didn't get around to implementing
the attack again yet, but I did add in a dodge. It's a little hard to see in the gif as there is no visual
indicators other than the speed of the character changing.

![](https://github.com/TrevorWM/TrevorWM/blob/main/DudeDodging.gif)
</details>


<details>
<summary> <h3> Jan 30, 2023 </h3> </summary>
<br>
Spent a lot of time today going over the same code a bunch of times for the attack. Trying to figure out
the best way to handle things. I feel like I could have got some more actual progress done if I was being
more loose with my code architecture, but I haven't done many large projects before, and I want to make
the inevitable refactoring as easy as possible in the future.

![](https://github.com/TrevorWM/TrevorWM/blob/main/DudeSwingin.gif)
</details>


<details>
<summary> <h3> Feb 2, 2023 </h3> </summary>
<br>
Started working through the CodeMonkey Beginner Unity tutorial to get a better idea of how to properly
layout projects. It's been super helpful so far, and I was able to refactor things in a way where stuff
is more loosely coupled and easier to manage. Nothing really for visible progress, but I'm feeling better
about the project overall with the refactoring I've done.

Mostly creating events and better splitting code
between different scripts in order to keep things easier to read and maintain.
</details>

<details>
<summary> <h3> Feb 7, 2023</h3> </summary>
<br>
Took a break for the weekend. Spent a fair bit of time today trying to do things the "best" way before
moving to just getting things working and then worrying about that stuff later. It's a lesson that I'm glad
I was able to learn relatively quickly because I was able to get some basic powerup items working and applying
buffs. Not quite the system I have in my head yet, but I'm getting a lot closer to what I have in my head.
</details>

<details>
<summary> <h3> Feb 13, 2023</h3> </summary>
<br>
I was pretty busy lately and haven't had the chance to work on things much. Today I got a few visual things done. I made my own sprites for the powerup icons,
  and I'm going to go back and make my own sprites for the character as well at some point. Currently I'm using the sprites from https://0x72.itch.io/dungeontileset-ii.
  
I also followed a tutorial on how to do outlines using shader graph cause I tried to do something on my own and that was super out of my current knowledge. Shaders seem pretty cool though, and I'm interested to learn more about them. Probably something to focus on at a later time though. I wanna focus on getting a gameplay prototype going. We're slowly but surely getting there.
  
![](https://github.com/TrevorWM/TrevorWM/blob/main/DudeUpgradin.gif)
</details>

<details>
<summary> <h3> Feb 22, 2023</h3> </summary>
<br>
Spent some time recently creating the item system. I had a few designs that I had come up with and implemented, but none of them were doing what I really wanted. I spent a bunch of time researching stuff looking at how other people solved the issue as well as learning about design patterns that I haven't used before. I tried a few of things out such as decorator functions for adding functionality to my attacks. This didn't work quite the way I wanted, and the way code ends up laid out is kind of awkward for what I had in mind as well. After a while I accepted that I was trying to overengineer the solution and went with a fairly simple but effective one instead. I also had the idea of creating a manager for my items. This will make it pretty easy for me to extend the functionality of my items to enemies or other objects in my game if I really want to later on. Do some cool stuff with barrels that chain lighting enemies if they break or something fun like that.

After I got the items squared away I also went ahead and applied a similar system to the attack that was in the game currently. I changed it to an Ability, and then made a similar implementation to the items to make it more modular. I think I've also settled on giving characters set loadouts to use rather than having a bunch of equipable items they can grab. Tones down the scope a bit for myself to make things more achievable, and I can always add new abilities to the loadouts to give a similar feeling of character progression that I wanted from equips.

I'm really happy with the system I have in place now. I hope that feeling sticks around for a long time, and future me doesn't end up wanting to kick past me in the butt.
</details>
