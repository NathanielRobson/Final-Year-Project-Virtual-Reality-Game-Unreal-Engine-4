# **Section 3 - Enemies, Damage and AI**
## **Introduction**
This section describes the implementation of the enemies, how they damage the player and the artificial intelligence involved in their process.  

Please consider this documentation as a reference guide to get additional information on topics covered in my [](Final Report).  
  
## **The Enemy**  
The enemies’ purpose in my game is to track down the player and attack them, making survival harder for the player and of course giving the player an objective in the game. 
I decided to use UE4’s Mannequin as the enemy player model as this would save time and allow me to focus on the fundamentals of their actions. 
I can control many parameters and have manipulated so to adjust difficulty levels. 
Parameters include enemy movement speed, attack speed, health, the total number of enemies, and how smart the artificial intelligence controlling the enemies is.
  
  
Below is a screenshot of how the enemy looks within _Breaching Light_:  
  
  
![The Enemy](/screenshots/Git-S3-TheEnemy.png)  
  
  
From the image you can see two wireframe shapes, the sphere surrounding the wrist is the object which will be used to check for collisions with the player, the other shape
surrounding the whole enemy is the object that can be hit by the player, weapons and projectiles.
  
  
## **Damaging The Player**  
To implement the damage function, I could have opted for an easier option of simply damaging the player when the enemy is within a certain radius.
I decided that this was not sufficient and was not fun enough. Instead, I opted for the method which involved damaging the player with a specific animation and
bone part of the enemy. The enemy will swing their hand at the player, and midway through the swing, a check is performed to determine whether the player
was indeed hit or not and if the player was hit, damage them.  
  
  
![Enemy Damage](/screenshots/Git-S3-EnemyDamage.png)  
  
  
The above image reflects the '**_EventMeleeAttack_**' function, when called it executes the '**_PlayMontage_**' function, which will cause the
enemy to perform an attack animation. The animation can be seen in the gif below:  
  
  
![Enemy Animation](/screenshots/Git-S3-EnemyAnim.gif)  
  
  
I have annotated the section which I have implemented a ‘**_Notify_**’ action. 
This action allows me to store this frame reference in a variable and apply it to the enemies scripts.
When attacking the player, this information is vital as it identifies when the ‘**check for collision**’ should take place.
If the enemy collides with the player in this animation frame, it signifies that the player is hit and should lose health. 
This can be seen below:  
  
  
![Enemy Anim Notify](/screenshots/Git-S3-AnimNotify.png)  
  
  
Once the enemy performs the attack, we now need to confirm whether the player was hit or not. We also need to prevent the enemy from hitting the player more than once
in one swing of the enemies arm.  
  
  
![Enemy Collison Blueprint](/screenshots/Git-S3-ConfirmCollision.png)  
  
  
The above image reflects the check for collision when the wireframe sphere begins the overlap of the player. A check is performed to confirm collision.  
On the overlap end, a delay is of 1.5 seconds is set to prevent the enemy from damaging the player again within this period.  
  
  
## **Artificial Intelligence**  
To allow the enemy to chase the player, I had to implement some form of artificial intelligence into the enemy system.
I used a **Blackboard** and **BehaviourTree** to do this. A blackboard is a simple place where data can be written and read for decision-making purposes. 
A blackboard can be used by a single AI pawn, shared by a squad, or used for any other purpose where it’s convenient to have a central place to look up relevant data. 
Blackboards are commonly used with behaviour trees, 
but you could use them separately from behavior trees for convenience, or you could make a behaviour tree with no need of a blackboard.  
I used a blackboard to make efficient event driven decisions and behaviours.  
  
Blackboard:  
  
![Enemy Collison Blueprint](/screenshots/Git-S3-Blackboard.png)  
  
  
Behavior Tree:  
  
![Enemy Collison Blueprint](/screenshots/Git-S3-BT.png)  
  
  
From the images above we can see that in the blackboard we have a list of variables; Yellow = **_TargetLocation_** is a Vector, Blue = **_SelfActor_**
is a reference to the enemy itself, Red = **_CanSeePlayer_** and **_PlayerIsInMeleeRange_** are Booleans.  
This information is relayed between the behaviour tree and the blackboard to allow decisions to be made in reference to these variables.  
  
  
The image below reflects the script that allows the continuous execution of the **BehaviourTree** and **Blackboard**.  
  
![Enemy Collison Blueprint](/screenshots/Git-S3-AI.png)  
  
  
When the game begins, the function **_RunBehaviourTree_** is called, which initialises the numerous variables detailed above. **_OnTargetPerceptiponUpdated_**
then takes the **_AIPerception_** Object as its parameter and determines whether the player successfully senses the player. The **AIPerception** Object is an object which
we can add or edit on our enemy blueprint to apply the intended intelligence.  
  
  
To inform the blackboard that the player is in range, we use the following script:  
  
  
![Enemy Collison Blueprint](/screenshots/Git-S3-PlayerInRange.png)  
  
  
Upon activation, the distance from the enemy and the player is checked against the **_Melee Range_** float variable, and if it is less than or equal to the melee range, the value
is parsed to the blackboard to allow for a decision to be made. In this case, the **Attack Player** sequence will take place.  
  
  
## Quick Link to Section 4 - Score, Kills and Gamemode
  
*  [View Section 4](/documentation/Section_4.md)


