# **Section 5 - Maps**
## **Introduction**
This section describes the development of the maps within _Breaching Light_.  

Please consider this documentation as a reference guide to get additional information on topics covered in my [](Final Report).  
  
## **Main Menu**  
The **Main Menu** map is where the player will first be placed within _Breaching Light_, at first glance they will see three **teleporters** placed around the room, each of which
loads a new level.
  
  
![Main Menu Room](/screenshots/Git-S5-MainMenuRoom.png)  
  
  
In the image above, there are three boxes with the word '**teleporter**' pasted on each side. Once the player enters one of these, they will load the corresponding area.  
  
  
The main menu consists of a **welcome message**, the **main menu ui** and the **three teleporters** along with the **control scheme layout models**:  
  
  
![Main Menu Room2](/screenshots/Git-S5-MainMenuRoom2.png)  
  
  
To create this map, I used UE4's **Geometry Editor**. I created rectangular slabs and positioned them to create a large room. I used the provided texture from UE4's VR tutorial of the VR headset,
which is a matte black colour. This is applied to all walls. I then scattered lights around the scene, with shadows disabled to prevent a heavy performance impact.  
  
  
![Geometry Editor](/screenshots/Git-S5-GeometryEditor.png)  
  
  
The geometry editor can be seen in the image above. This allows me to scale, rotate, position, translate and extrude shapes to create necessary polygons for my scenes. 
  
  
In the main menu map, I have added the teleporter labelled '**Shooting Range**', this is situated above the main menu room and allows the player to test out all weapons 
and power-ups in my game before navigating to a level.  
  
  
![Shooting Range](/screenshots/Git-S5-ShootingRange.png)  
  
  
Enemies will spawn behind a wall, and the player will have the ability to attack them either from safety or by traversing the wall and fighting close-quatres.  
  
  
![Shooting Range 2](/screenshots/Git-S5-ShootingRange2.png)  
  
  
The **Glowing Yellow Cubes** represents the spawn locations of the enemies. These are not visible in-game; they are only for reference when developing and debugging the map.  
  
![Shooting Range 3](/screenshots/Git-S5-ShootingRange3.png)  
  
![Shooting Range 4](/screenshots/Git-S5-ShootingRange4.png)  
  
![Shooting Range 5](/screenshots/Git-S5-ShootingRange5.png)  
  
Above is the options the player has to choose from when it comes to testing out all weapons and power-ups within my game.  
  
  
## **Survival Forest**  
The **Survival Forest** map is the first map I intended to create. There are three islands, each with its own purpose and method of crossing. The player will be set in a dark spooky forest
environment and will have to fend off the enemies once they leave the spawn zone:  
  
  
![Forest Spawn Zone](/screenshots/Git-S5-ForestSpawn.png)  
  
  
The above image is an old barn created using the **Geometry Editor** and gives a nice effect to the player of a remote location:  
  
  
Once leaving the spawn zone they will have two options of travel, either navigate to the right where they can climb the broken bridge to **_Island 3_**, where the shop is located, 
or take the long way around, passing weapon drops and power-ups along the way.  
  
  
Bridge:  

![Forest Bridge](/screenshots/Git-S5-ForestBridge.png)  
  
  
Long Path:  

![Forest Path](/screenshots/Git-S5-ForestDrops.png)  
  
  
Each direction has its own consequences that the player will have to suffer.  
  
  
![Forest Camp](/screenshots/Git-S5-ForestCamp.png)  
  
  
In the image above, we can see the **Forest Camp** located on **Island 2**. This offers the player weapons and power-ups as well as a notification of progress towards the item shop on
**Island 3**.  
Passing the camp to the right, the player will see the **Item Shop** situated on a hill in the distance:  
  
  
![Forest Distant Shop](/screenshots/Git-S5-ForestShopDistance.png)  
  
  
To reach the shop, the player will have to **climb** the wall in the image below:  
  
  
![Forest Shop Climb](/screenshots/Git-S5-ForestShopClimb.png)  
  
  
Upon climbing the wall, the player will be located just outside the **Item Shop**. The player can enter and choose to **spend their accumulated points** on weapons and upgrades:  
  
  
![Forest Shop Inside](/screenshots/Git-S5-ForestShopInside.png)  
  
  
## **Gladiator Arena**  
The Gladiator Arena is the second map which I did not intend to make. I finished the development of the first map rather quickly and decided that I wanted to offer
a more diverse opportunity of experiences to the player. Also, not being able to see much in the Forst map removed the ability to showcase what I have worked on over the 
project period.  
  
  
![Gladiator Arena 1](/screenshots/Git-S5-Arena1.png)  
  
  
The images above reflect the main part of the arena, and this is where the player will begin to fight the enemies in the level.  
  
  
![Gladiator Arena 2](/screenshots/Git-S5-Arena2.png)  
  
  
The above image reflects the walkway which the player can utilise to better line-up the enemies to defend themselves.  
  
The player can access two more levels via the stairs.
  
![Gladiator Arena 2](/screenshots/Git-S5-Arena3.png)  
  
  
The upper level is where the player will find the item shop and some decent weapons and powerups:  
  
  
![Arena Upper 1](/screenshots/Git-S5-ArenaUpper1.png)  
![Arena Upper 2](/screenshots/Git-S5-ArenaUpper2.png)  
![Arena Upper 3](/screenshots/Git-S5-ArenaUpper3.png)  
  
  
The lower level is where some hidden loot is located along with the prison cells:  
  
  
![Arena Lower 1](/screenshots/Git-S5-ArenaLower1.png)  
![Arena Lower 2](/screenshots/Git-S5-ArenaLower2.png)  
![Arena Lower 3](/screenshots/Git-S5-ArenaLower3.png)  
  
  


## Quick Link to Section 6 - Game Balancing, Bug Fixes, Future Implementations, Polish and Review
  
*  [View Section 6](/documentation/Section_6.md)


