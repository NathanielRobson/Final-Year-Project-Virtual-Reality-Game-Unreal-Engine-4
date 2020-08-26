# **Section 2-1 - Weapons**
## **Introduction**
This section describes the Weapons I have implemented into _Breaching Light_. Section 2 is split up into 2 chapters for easier content navigation.  

Please consider this documentation as a reference guide to get additional information on topics covered in my [](Final Report).  
  
## **Weapons**  
The weapons in breaching light are what offer the most diversity when it comes to gameplay. I have implemented multiple different kinds, below is
a list of each weapon in the game currently:  

*  Hand Knife
*  Assault Rifle
*  Mini Gun
*  Hand Axe
*  Great Axe
*  Thor Hammer
*  Desert Eagle
*  Grenade
*  Light Saber
*  Mace
*  Throwing Knives
*  Sword

  
Each weapon has been individually scripted and adjusted to perform a different action than the next.
I will split the weapons into categories: **Melee**, **Thrown**, and **Projectile**.

## **Melee Weapons**  
Beginning with melee weapons, as this is the first type of weapon I successfully implemented into _Breaching Light_.  
I will refrain from detailing all weapons due to their similarities so I will be detailing 1 per category.  
  
  
### Hand Knife (Melee Weapon)
Object Name: **_BP_PickupKnife_**  
  

![Knife Screenshot](/screenshots/Git-S2-WeaponKnife.png)  
  
  
The image above shows how the knife will look in-game, minus the fancy in-game lighting effects.  
At this stage, all the knife is is a 3D model which has no collisions, so effectively if it was placed in the game world, it would fall right
through the map. To prevent this from happening, we have to adjust the collision parameters and set them to the following:  
  
![Knife Collision Settings](/screenshots/Git-S2-WeaponCollision.png)  
  
  
Now the knife will not fall through the map, and this allows us to gain a step closer to interacting with the object.  
Next, we need to add the ability to pick the knife up with our in-game hands which are an extension of the motion controllers.  
In Section 1, I detailed how I allowed input from the controllers to be translated into scripts and called by functions; 
we now need to call a function when we press the trigger to attach the knife to our player's hand and in the correct orientation.  
  
![Knife Pickup](/screenshots/Git-S2-WeaponPickup.png)  
  
  
The above image is a script which enables the player to pick the weapon up when the player presses the trigger in range of the object.  
First, the **_EventPickup_** is called, the physics of the object, in this case the knife are disabled to prevent your in-game hand from falling to the
floor. The object is then attached to the hand that picked the object up. A switch case determines the orientation of the knife; all objects will have
a distinct location and rotation parameter, which positions the object correctly in the player's hand. The switch case simply randomises the chance that
the knife will be held pointing downwards or upwards. Most weapons only have one set orientation and location.  
  
In addition to picking up the weapon, it is important that once the player releases the trigger, the weapon is dropped and released from the player's grip.  
The following image demonstrates that implementation:  
  
![Knife Drop](/screenshots/Git-S2-WeaponDrop.png)  
  
  
The **_EventDrop_** function is called when the player releases the trigger of the motion controller, the object is then detached from the hand actor, 
and finally, the knife is set to true to simulating physics. At this point, the item should drop to the floor (Depending on Gravity settings).  
  
  
The knife is a staple in object interaction as almost all other weapons share these methods of picking up and dropping, each with their own tweaks to
better suit the object in hand and the interaction intended.  
  
  
## **Projectile Weapons**  
### Desert Eagle (Projectile Weapon)  
Object Name: **_BP_DesertEagle_**  
  
  
![Desert Eagle Screenshot](/screenshots/Git-S2-WeaponDesertEagle.png)  
  
  
Similar to the knife detailed above, the **_Desert Eagle_** has a very similar blueprint script structure to picking the weapon up and dropping it,
so there is no need to describe this again. Instead, I will describe how the projectile of the weapon is formed and how the collisions are checked for 
a hit.  
  
  
![Desert Eagle Muzzle Point](/screenshots/Git-S2-MuzzlePoint.png)  
  
In the image above we can see a pointer reference located at the end of the weapon, here I have created an invisible object called **_MuzzlePoint_**. 
This is an object used as a location and rotation reference to allow for a correct starting position of the projectile.  
This allows us to begin the Line Trace from the endpoint of our gun to a set defined range of my choosing.  

I will break down the Line Trace of the Projectile into stages as the script, at first sight, looks quite complex, but broken down can be quite manageable.  
  
  
![Projectile Script GIF](/screenshots/ProjectileScriptGif.gif)  
  
  
**Stage 1:**  
Get the initial projectile world location and orientation, set the distance at which we wish to track:  
  
  
![Projectile Script Stage 1](/screenshots/Git-S2-ProjectileStage1.png)  
  
We take the object **_MuzzlePoint_** and retrieve its world location and world rotation.  
  
  
**Stage 2:**  
Begin the **Line Trace**, store reference to objects collided and determine whether object and projectile should cause a '**hit**'.  
  
  
![Projectile Script Stage 2](/screenshots/Git-S2-ProjectileStage2.png)  
  
  
References to the impact point, impact normal, hit actor and component are stored and checked to determine if the object can be '**hit**' or not.  
  
**Stage 3:**  
Decrement the ammunition in the weapons clip.  
  
  
![Projectile Script Stage 3](/screenshots/Git-S2-ProjectileStage3.png)  
  
  
**Stage 4:**  
Spawn the bullet, particle effects, and weapon firing sound.  
  
  
![Projectile Script Stage 4](/screenshots/Git-S2-ProjectileStage4.png)  
  
Each effect is spawned at a specific location in correlation with its intended purpose. E.g. the weapon firing sound is spawned at the centre of the gun.  
  
  
**Stage 5:**  
Finally, if the object is determined to be damageable, apply damage to the object hit and spawn and attach bullet hole decal.  
  
  
![Projectile Script Stage 5](/screenshots/Git-S2-ProjectileStage5.png)  
  
  
## **Thrown Weapons**  
Thrown weapons include the **grenade** and **throwing knives**.  
  
  
Both objects are picked up and dropped in similar methods to the knife detailed at the start. However, there are slight additions to when the item is dropped,
which changes the behaviour of the item. An example of this is the grenade, once it is dropped a timer will start, once the timer is up the grenade will
explode, causing damage to enemies within a set radius.  
The throwing knives, on the other hand, also have a timer, but instead of exploding, they teleport back into the player's hand for a total of three times.
Allowing the player to throw them more than once.  
  
  
### Grenade (Thrown Weapon)  
Object Name: **_BP_Grenade_**  
  
  
![Grenade Screenshot](/screenshots/Git-S2-ThrownGrenade.png)  
  
  
The grenade is similar to the knife, however, you can see from the image that there is a sphere around the object. This wireframe sphere
acts as the damage radius of the grenade. The sphere expands instantly to a wide radius, and any enemies within the radius at the time of the explosion
will be destroyed.  
  
  
![Grenade Script](/screenshots/Git-S2-GrenadeScript.png)  
  
  
In the image above, we can see that the function **_EventDrop_** must be called for the actions to take place.  
Once dropped, the object simulates physics a timer is started (Four seconds), and after the timer has completed the function **_Detonate_** is called.  
The explosion effect is spawned at the location of the grenade, and the explosion sound is played. The sphere surrounding the grenade is transformed to
sixteen times its size. A loop is then created, iterating over each enemy within the sphere at the time of the explosion, applying damage to each to destroy them 
and then the player's score is updated to reflect the kills. Finally, upon loop completion, the grenade actor is destroyed, removing it from the game.
  
  
### Throwing Knives (Thrown Weapon)  
Object Name: **_BP_ThrowingKnife_**  
  
  
![Throwing Knife](/screenshots/Git-S2-ThrownKnife.png)  
  
  
The above image is what the throwing knife looks like within _Breaching Light_.  This weapon functions differently to most due toh the **EventDrop** and **EventPicup**
functions being combined to achieve the intended effect.  
  
  
![Throwing Knife Script](/screenshots/Git-S2-ThrowingKnifeScript.png)  
  
  
In the above image we can see that a loop is formed with the **_EventDrop_** and the **_EventPickup_** function to allow the weapon to be attached to the hand when dropped.  
When the object is dropped, it will check to see how many knives have been thrown with **_Knifecounter_** and if it is less than 3, perform the normal drop motions of detaching from the hand and simulating physics.  
However, there is also a **_Delay_** timer which is set to wait six seconds, once the time is up, the object is attached to the hand once more, and the knife count is incremented.  
When the knife counter is more than 3, the knife will no longer return to the player's hand after being thrown.  
  
  

## Quick Link to Section 2-2 - Flashlight, Damage and Player Death
  
*  [View Section 2-2](/documentation/Section_2-2.md)


