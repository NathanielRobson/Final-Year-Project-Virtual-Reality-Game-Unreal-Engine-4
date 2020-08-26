# **Section 6 - Game Balancing, Bug Fixes, Future Implementations, and Review**
## **Introduction**
This section describes the balancing procedures put in place to ensure the game is playable and not heavily one-sided when it comes to fighting off the enemies.  
I will also detail some recent bug fixes, further implementations and finally discuss the polish and review.

Please consider this documentation as a reference guide to get additional information on topics covered in my [](Final Report).  
  
## **Game Balancing**  
It is important to ensure that a game is balanced to allow players not to get bored or frustrated with the game. The right level of balance can only be found
by playing the game. I was able to identify that in the beginning enemies were too slow and easy to kill, which translated into the game being boring and too easy.  
From this feedback, I was able to adjust the Enemies with the following parameters:  

*  Enemies intention previously was to find and chase the enemy, the **AI was not smart enough** and required
further implementation to work effectively. To ensure that the case was resolved, I **removed the searching behaviour** of the enemy and set them so only chase the enemy.
*  The **speed of the enemies was too slow** for the pace of the game I intended to create. To resolve this, I **increased the enemies movement speed** and the speed at which the enemies 
**animation is played back**. This resulted in the game feeling a lot more involved and immersive.
*  Some of the weapons felt underpowered and were not very effective against the enemies, e.g. the **throwing knives**, To
resolve this, I **adjusted the damage values** of the weapon and **implemented the feature of the knives returning to the player's hand**.
*  The player could previously move **freely by teleporting without restrictions**. This translated into the player constantly moving away from the enemies and the enemies
not standing a chance. To resolve this I implemented the **player energy feature**, and this **restricts how many times the player can teleport** in a set time 
and causes the player to think carefully when moving to prevent being in a situation where they run out of energy and cannot move, thus causing death.
* ** Assault Rifle Reload** and **Drop**. Two features were added in response to player feedback, whenever the **assault rifle was dropped**, players had to **kneel down** to grab the weapon from
the **floor**. This caused frustration and disorientation when coming up against an enemy and having no weapon in hand. To resolve this, I **removed the ability for the assault
rifle to simulate physics**. Instead the weapon **floats** exactly **where** the player **dropped** it. The **reload issue**. Previously players had to bring the assault rifle down to
**their waist** to reload, a lot of the time this **did not function as intended** and caused players to struggle when attempting to reload the weapon. To resolve this
I added the ability to **reload with one of the buttons** available on the **motion controllers**.
*  The **Flashlight** was previously a **physical item** which the player had to pick up and hold to see, this was not very good as it **prevented** the **use** of **one of the hands in combat**.
To resolve this, I **attached** the **flashlight** directly to the *players head*, thus removing the restriction of holding it and freeing up another hand.

All of these features and changes above were intentionally aimed at balancing the game and allowing a more fluid, fun experience to take place.  
  

## **Future Implementations**  
Many implementations can be made to further improve the game, although it is likely that these will not be implemented due to the project being completed, these are, however, 
some of the additions I would choose to make/change if I decide to return to this project in the near future.

Future implementations include:  
*  Better Enemy Animations
*  More Enemy Types
*  Map Optimisations
*  Alternate Player Movement Options
*  More Natural Enemy Death Physics/Animation
*  Change Current UI Elements into Modern UI Elements
*  New Maps
*  Multiplayer Support
*  Listed on Oculus/Steam Marketplace
*  Performance Optimisation
*  Support for Linux and Mac OS
*  Controller Support
*  More Weapons and Power-ups

 
## **Review**  
Virtual reality has progressed significantly in recent years, reflected by the amount of new and improved technology. 
The continuation of this can only enhance the area of games development and allow for new and improved experiences to take shape.  
Developing a game in VR has enabled me to gather experience from al different areas of development and additionally allowed me to further my knowledge in computer science. 
My beginning intentions were tightly centred around the development of the game and progressed into understanding all areas of VR platform implementation. 
I am eager for the prospect of what is to come for virtual reality and the benefits it has on the games industry as a whole.

The overall outcome of my game is positive as I have a fully playable and enjoyable experience centred around the virtual interactions and practises. 
Players can execute the game from their home desktops (if files are provided) and embark on the survival journey I have produced. 
Moreover, Development with Unreal Engine 4 has allowed me to gain an in-depth insight into what assignments triple-A games and indie games developers undertake on a daily basis. 
I now understand what managing and developing a project entails from start to finish, and this project has also allowed me to identify areas in which I can further improve and better my performance. 
I intended to produce a virtual reality game utilising the development engine UE4 and have succeeded in doing this along with acquiring a sizeable quantity of knowledge in both areas. 
I intend to make use of the knowledge attained in this project for many years and many projects to come, moving forward.
Reviewing my project code and structure, I found that developments made at the beginning of my project, in contrast to those made towards the end are not the same. 
This shows that as the project progressed, my knowledge and skill developed in correlation with my project; as the project progressed, so did I. 
To better my project, I would need to exploit the techniques and skills grasped throughout to reiterate developments made in the beginning.


Finally some images linked to the development of my game:  
  
  
![Breaching Light EXE Icon](/screenshots/Git-S6-Icon.png)
![Breaching Light Editor Splash](/screenshots/Git-S6-Icon2.png)
![Breaching Light Editor Splash 2](/screenshots/Git-S6-Icon3.png)  
  
![Breaching Light Forest Image](/screenshots/Git-S6-Icon4.png)

## Quick Link to Repository Home
  
*  [Home](ce301_robson_n)


