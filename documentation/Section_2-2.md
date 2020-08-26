# **Section 2-2 - Flashlight, Damage and Player Death**
## **Introduction**
This section describes the Player's Flashlight, Damage and Player Death. This is the second chapter of section 2.  

Please consider this documentation as a reference guide to get additional information on topics covered in my [](Final Report).  
  
## **Flashlight**  
The **Flashlight** in _Breaching Light_ is implemented differently to complement the VR aspect and immersion.  
Instead of the player having to hold the flashlight with one of their hands, I have attached and locked the position and orientation to the HMD(Head-Mounted Display).  
Below is a screenshot of the **Spot Light's** I have added to the **_MotionControllerPawn_** camera object.  
  
  

![FlashLight](/screenshots/Git-S2-PlayerCameraLight.png)  
  
  
In the image above, you can see the attached lights displaying a wireframe cone. This wireframe cone reflects the distance and radius of the lighting effect.  
To adjust the strength and the colour of the light, I can adjust the values to the right of the image such as '**Light Colour**' and '**Attenuation Radius**'.  
  
  
I have attached the lights to a '**Spring Arm**'. This allows me to control parameters such as the speed of movement and light 'Lag'.  
I utilised the spring arm to delay the speed at which the lights follow the head to control a sense of immersion in-game, the slower the light moves with the players
head, the less the player can see in an instant. This builds up tension in dark scenes such as my '_Survival Forest_' map. The spring arm can be seen in 
the image below:  
  
  
![FlashLight](/screenshots/Git-S2-SpringArm.png)  
  
  
## **Damage and Player Death**  
Damage in _Breaching Light_ is controlled by calling the '**_ApplyDamage_**' function and inputting an integer variable. However, if the object has not had some sort 
of health variable or interface created, this will have no effect.  
To allow my player to take damage, I first had to ensure that it has health. Adding a simple Float variable called 'Health' allowed me to manipulate this.  
  
  
![Damage](/screenshots/Git-S2-PlayerDamage.png)  
  
  
Above we can see that the '**_EventAnyDamage_**' has an input of a Float to control the amount of damage applied to the player.  
The first check is to see if the player currently has **_godmode_** activated or not, if not then we can safely check the see if the player's health, minus the damage
being applied is less than zero, which can be seen here:  
  
  
![Player Health Check](/screenshots/Git-S2-PlayerHealth0.png)  
  
  
If the player's health is less not less than 0, then we apply the damage to the player with the following function:  
  
  
![Player Damage Function](/screenshots/Git-S2-PlayerDamageFunction.png)  
  
  
If the player's health is less than 0, then we destroy the player, invoke player death and enact the game over sequence:  
  
  
![Player Death](/screenshots/Git-S2-PlayerDeath.png)  
  
  
Above we can see that a '**PlaySound2D**' function is called, this will play one of two death sounds to indicate to the player that they have died.  
  
  
The game over function is then called:  
  
  
![Game Over](/screenshots/Git-S2-GameOver.png)  
  
  
The above function retrieves the level that the player is currently on and displays the loading screen and once it reaches the return node, the map is reloaded.  
  
  

## Quick Link to Section 3 - Enemies, Damage and AI
  
*  [View Section 2-2](/documentation/Section_3.md)


