# **Section 1 - Character Setup**
## **Introduction**
This section describes the VR character movement, object interaction, and simple energy system.  

Please consider this documentation as a reference guide to get additional information on topics covered in my [](Final Report).  
  
## **Input, Character Movement, Teleportation and Energy**
### **Setting up input in Unreal Engine 4:**  

Input mappings are stored in configuration files and can be edited within the Input section of Project Settings. 
In the screenshot, we can see an action and 2 button mappings being applied to that action.  
  
![Input Image](/screenshots/Git-S1-Input.png)  
  
  
**AxisMappings** can be edited or added to allow for new input actions.  
  
![Input Image 2](/screenshots/Git-S1-Input2.png)  
  
  
Input actions are called within blueprints and tend to look like this:  
  
![Input Image Call](/screenshots/Git-S1-InputCall.png)  
  
  
  
Adding the Input Bindings like so allows for the player to press the analogue stick, which will call the **Teleport** function:  
  
![Input Image 3](/screenshots/Git-S1-Input3.png)  
  
The input procedure is as follows:  
  
![Input Image Diagram](/screenshots/Git-S1-InputDiagram.png)  
  
  
The following Blueprint Snippet controls the **Teleportation** and **Energy** mechanism.  
If the player wishes to teleport but does not have enough energy remaining, it will fail and a sound indicating that the player is out of breath will play.  
  
![Input Image Energy](/screenshots/Git-S1-InputBlueprint.png)  
  
  
The players' energy increases Every 2 seconds if it is lower than the players **_Energy Max_**, the following screenshot reflects the process
of energy incrementation:  
  
![Input Image Energy](/screenshots/Git-S1-InputBlueprintEnergy.png)  

  
## **Player Camera Setup and Object Interaction**
The player named **_MotionControllerPawn_** has no physical body; the hands are a separate object named **_MotionController_**.  
Here is the visual appearance of the player in development view:  
  
![Player Image](/screenshots/Git-S1-Player.png)  
  
  
The camera is attached to the **HMD(Head-Mounted Display)** and is locked to its **location** and **rotation**. The height of the player
is checked upon setting up VR, and this translates into setting the players height in UE4:  
![Player Camera Image](/screenshots/Git-S1-PlayerCamera.png)  
  
  
Next, we have to attach the hands to the player, so interaction becomes possible, the hands are similarly attached to a hardware element. 
The hands lock to the location and rotations of the motion controllers, so wherever the player moves the 3 points of contact (Head + 2 Hands) follow.
The hand actor **_BP_MotionController_** is spawned twice and flipped once to act as both the left and right hands and then attached to the _VROrigin_ (Players Position):  
![Player Camera Attach](/screenshots/Git-S1-AttachPlayerCamera.png)  
  
  
Now the player has both the visual aspect of VR and the physical. Virtual interactions can now take place.  
  
Utilising the already mapped controls, we can call functions each time the player presses a button and perform an action.  
In the image below, there are two forms of interaction, the left (Cyan) is when the player presses the trigger on the motion controller, the **_GrabActor_** function is called 
and this allows for objects to be picked up or interacted with.  
The right (Magenta) reflects the interaction with the _Main Menu_, _UI_ or pause interfaces when 
the game is paused or the player is in the _Main Menu Box_ the inputs change the actions of the trigger and now performs a mouse button press, Thus allowing for 
menu interaction:  
![Player Interaction](/screenshots/Git-S1-PlayerInteraction.png)  
  
  

## Quick Link to Section 2 - Weapons, Flashlight, Damage and Player Death  
  
*  [View Section 2](/documentation/Section_2-1.md)


