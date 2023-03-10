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
more loose with my code architecture, but I haven't done many large projects before, and I want to use this project as a way to practice
scalability and modularity. Sort of practicing for working in a team setting.

![](https://github.com/TrevorWM/TrevorWM/blob/main/DudeSwingin.gif)
</details>


<details>
<summary> <h3> Feb 2, 2023 </h3> </summary>
<br>
Started working through the big CodeMonkey Unity tutorial he put out recently to get a better idea of how to properly
layout projects. It's been super helpful so far, and I was able to refactor things in a way where stuff
is more loosely coupled and easier to manage. Nothing really for visible progress, but I'm feeling better
about the project overall with the refactoring I've done.

Mostly creating events and better splitting code between different scripts in order to keep things easier to read and maintain.
</details>

<details>
<summary> <h3> Feb 7, 2023</h3> </summary>
<br>
Spent a fair bit of time today trying to do things the "best" way before
moving to just getting things working and then worrying about that stuff later. It's a lesson that I'm glad
I was able to learn relatively quickly because I was able to get some basic powerup items working and applying
buffs. Not quite the system I have in my head yet, but I'm getting a lot closer to what I have in my head.
</details>

<details>
<summary> <h3> Feb 13, 2023</h3> </summary>
<br>
Today I got a few visual things done. I made my own sprites for the powerup icons,
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

<details>
<summary> <h3> Feb 27, 2023</h3> </summary>
<br>
My goodness I spent so much time trying to get my custom relic inspector working properly. I was running into issues where data wasn't saving after Unity hit certain reset points. Creating a new build for example was causing all the data in my Relic Scriptable Object to be lost. Things were working in Editor, but then they weren't working in build, and I couldn't get shaders to load at runtime, so for the shader I swapped to just manually creating the reference. We finally got the other stuff working though, and I'm really happy with the way the custom inspector turned out. It's not super duper fancy, but now all that needs to be done to create new relics is to click a few buttons and put values into the SO. I even added the ability to attach abilities to the relics as well in order to try and keep them modular even when creating the more unique ones. It shouldn't be too difficult to turn that bit into a list of abilities if I want to extend it a bit further. Though with the current set up the relics are locked to a specific trigger for active effects. As I'm writing this I haven't implemented the active relics yet. Still deciding if I want to do that next, or if I want to make a proper enemy next so that once I start doing active abilities I'll be able to see if they're working properly when interacting with enemies.



Here is the inspector for Passive Relics.

![](https://github.com/TrevorWM/TrevorWM/blob/main/RelicSO%20Passive.png)
It allows you to select which stat it will modify, which kind of scaling you would like to use (Additive, Multiplicative, Logarithmic, or Exponential), and then you can put a scale value in.

And here is the Active Relic layout. I wanted it to change to fit the type of relic I was editing.
![](https://github.com/TrevorWM/TrevorWM/blob/main/RelicSO%20Active.png)
For the Active Relics I have a few different triggers laid out: On Attack, On Enemy Hit, On Enemy Killed, and On Self Hit (so if the player takes damage).

Currently all of this code is tied to the SO which is super nice right now because it means I can iterate and create new relics in the inspector and then just throw them on a container Monobehaviour script where they will just work without any additional coding. I should probably move this logic over to the Monobehaviour itself, but I thought of that after I started on working with abilities, so for now it stays, but it's on my to do list.
</details>

<details>
<summary> <h3> Mar 6, 2023</h3> </summary>
Worked on the abilities today to try and make them a bit more modular. I created a new class that handles abilities with projectiles. I think it's a little rigid right now as it specifically handles shooting out from a position. I want to move the actual shoot behaviour out of this script into either the projectile itself or the specific ability script. I also added in object pooling using the built in Unity classes. That part I think is definitely best to keep in this the ProjectileAbility base script. This way I can have different pools for each ProjectileAbility to handle different projectile prefabs, and pool size needs.
</details>

<details>
<summary> <h3> Mar 9, 2023</h3> </summary>
I wanted to try moving my stat system to an easier to manage system. Currently I'm just storing values and letting them sit there. I wanted to create a stat class so that I could hold a base, max, and current value for each stat. That way I can set hard limits on what the max stats are for things. As of now getting a bunch of Move Speed or Dodge Force can really make your character fly around, and I want the game to stay in a playable state (for the most part). I'm cool with crazy combos leading to game breaking synergies, but when it comes to actually moving the character around and feeling in control of what you're doing then I start to draw some lines in the sand. Who knows after getting more stuff done and experimenting a bit maybe I'll find something fun to do with the excessive move speeds. I was running on pretty little sleep today, and so trying to overhaul a system that was tied to a bunch of other things probably wasn't the best idea and also made me reconsider my approach to refactoring this bit. I stashed the changes that I made before reverting them, so maybe when I have a bit more brain power to spare I'll head back into that.

For tangible progress today I got the healthbar implemented for the player character. It updates based on an event system, so it's pretty standalone which is nice. I also put a few checks based on layers to determine which IDamagable objects IDamager objects could hit. But even just doing the 2 scripts. One for the current ability in the game, and one for the Enemy DealDamageOnCollision script I felt like I was repeating something that could be avoided. I'll try and find a better solution for this, but in the meantime it works. My mind immediately goes to IEnemyDamager and IPlayerDamager interfaces so I can just check that type as I already do this in the collision already. We'll see if I figure out a better solution than that though.

It's cool to be reaching a state where it's becoming more of a game rather than just a sandbox for me to mess around in. I think that once I add in an active relic of each type (maybe less), make it so the player can actually die, and add a spawner for enemies and relics then I can make a build of the game to pass along to some friends to see what they think when they can actually play it rather than look at the gifs I post or watch me stream it to them briefly on Discord.

I've also started debating if I want to keep the passive relic effects in the game or not. On one hand I think that they do a good job of pushing the player to the point of becoming an unstoppable killing machine which is the feeling I want to give the player, but on the other hand stat sticks are kind of boring. Unless it's a 4 STR 4 STAM Leather Belt of course. I definitely want to focus on more "active" effects. Stuff that changes the way you need to play, or stuff that has better visual feedback to player progression during a run. Stuff like attacks exploding, or bouncing. That kind of thing. I'm definitely going to keep the code in for the passive effects as they make it easy for me to test things like my relic manager, and it's easy enough for me to add or remove them from a loot pool if I flip flop on the idea before settling on a definitive answer.

Oh boy. That was kind of a long one. I've been thinking about a lot of stuff lately and wanted to get some of it down in a public place so that it feels more tangible in a way. Anyways here is a gif of some of the new things. The particles from before are gone cause I haven't added them back in since changing the relic prefabs, and I threw the Uncommon item outline on the character just to make sure it was working. I kind of like the character having an outline, but I'm not sold on it being neon green quite yet. I think I also want to make an actual sprite for the healthbar in the future as well. Right now it works and does what I need, but it feels out of place.

![](https://github.com/TrevorWM/TrevorWM/blob/main/DudeDamagin.gif)
</details>
