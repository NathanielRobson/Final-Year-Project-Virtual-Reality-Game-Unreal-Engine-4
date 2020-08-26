# **Section 4 - Score, Kills The Main Menu and Game mode**
## **Introduction**
This section describes the implementation of the layers score, the kill tracker, the main menu and the game mode.  

Please consider this documentation as a reference guide to get additional information on topics covered in my [](Final Report).  
  
## **Score**  
The player's score is adjusted in different scenarios; one is when the player gets a kill, the score needs to be increased another is when the player decides to
spend his/her accumulated score in the item shop on weapons and upgrades. The script that allows the score to be adjusted in any scenario is as follows:  
  
  
![Player Score Script](/screenshots/Git-S4-Score.png)  
  
  
This allows me to call this method whenever the player's score needs to be adjusted, whether negated or incremented.  
  
  
The player will accumulate score by getting kills. Kills are similarly tracked and incremented. Each time the player defeats an enemy, the **TotalKills** integer variable
is incremented.  
  
  
In-game, the player can access the **_Leaderboard_** from which they see the the scores kept on file, along with the name that the 
player provided at the start of the game:  
  
  
![Leaderboard in-game](/screenshots/Git-S4-Leaderboard.png)  
  
  
The Leaderboard is created when the player is killed. The name of the player and score at the time of death is stored and written upon reloading the level. The player can provide a
name in the UI shown below:  
  
  
![Name Input](/screenshots/Git-S4-Name.png)  
  
  
The name will be stored as a variable and applied to the following script when storing the leaderboard data to file:  
  
  
![Leaderboard Script](/screenshots/Git-S4-Leaderboard.png)  
  
  
The beginning of the script checks whether the save exists or not and sets it to a variable for reference. Once the reference is stored the **_PlayerNames_** and **_PlayerScores_**
are applied to the save, and the newest score and name is added. The data is then saved to file for later reference when creating the **Leaderboard**.  
  
  
## **Main Menu**  

The **Main Menu** is a 2D Graphical User Interface created within UE4's widget editor. The Widget Editor allows developers
to drag, drop and scale elements of UI's and apply scripts to them. Elements can be stored as a variable and scripted on later:  
  
  
![Main Menu](/screenshots/Git-S4-MainMenu.png)  
  
  
The Main Menu looks like this wihtin the Widget Editor:  
  
  
![Main Menu Editor](/screenshots/Git-S4-MainMenuEditor.png)  
  
  
On the left side we, can see that each UI element is referenced and named accordingly. These can be saved as variables and then referenced as such:  
  
  
![Main Menu Script](/screenshots/Git-S4-MenuScript.png)  
  
  
In the image above we can see two separate scripts with two different function calls. The top one is executed when the **_ResetButton_** is pressed by the player. This
will display the loading screen, set a timer delay of four seconds and open the **Main Menu** level once more.  
The bottom script is an enumerated difficulty selector, the difficulty variable is an integer, and when incremented, the difficulty level is incremented to follow. 
Each time the player pressed the button, the difficulty is increased, and when it is at 5, it is reset back to 1.  
  
  
## **Gamemode**
The game mode of _Breaching Light_ is relatively simple, but the implementation is rather complex. As the difficulty level is increased, the amount of enemies is increased,
the enemies health and speed and spawn speed is increased whereas the players total health is decreased.  
In addition to this, each time the player completes a wave (kills all enemies on a set wave) the next wave will have an increased number of enemies depending on the difficulty
level selected.  
  
  
![Wave Increment Script](/screenshots/Git-S4-WaveIncrement.png)  
  
  
The above script is the implementation of the wave incrementation. We first check to see if the player has left the spawn protection zone and entered an enemy spawn zone,
once the player is in the enemy zone, we count how many enemies are alive. If this is zero, increment the number of enemies, decrement spawn delay, increment wave counter
and begin a while loop. The while loop retrieves all spawn locations within a set spawn zone and attempts to spawn the required enemies depending on the current wave and difficulty
modifiers.  
  
  
The spawn zones allow us to segregate sections of the map to prevent the enemies from spawning too far from the player, here is a visual representation of how the spawn
zones are segregated:  
  
  
![Spawn Zone](/screenshots/Git-S4-SpawnZone.png)  
  
  
Each island annotated is segregated with faint red cubes. These cubes act as invisible zones in which the enemies can spawn in when the player is on the correlating island.  
This image is from my **_Survival Froest_** Map and is Unlit, hence the cartoony appearance.
  
## Quick Link to Section 5 - Maps
  
*  [View Section 5](/documentation/Section_5.md)


