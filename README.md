# jsfour-dna
A script that lets you take DNA from all players as well as crime scene (dead players).
 ### LICENSE
You are more than welcome to change what you want in the script but you should NOT resell the script or reload it again, refer the people here instead.
 ### INFO
* You get DNA by going to the person and clicking the menu (look further down)
  - From a live player, DNA is counted as a test, from a dead player it is considered a crime scene
* You can only have 1 DNA on you, this is loaded at the computer at the cells on the polishus
* You can delete the DNA contained in the database, then a password is required. The password is hard-coded and is jsfour by default. This can be changed in init.js in line 136
* To take a DNA from a dead player, players must be killed by a melee weapon. A knife for example. It's very illogical that you can get DNA from a bullet. But is this something you want to add, you can do it in the table of weapons in client.lua
* In order for the match results to be positive, you need to have DNA from the player in the database
 ### INSTALLATION
For this to work, you need to do the following:
 For the script to work, you need to use ESX.
 1. Insert the script into your resource folder and then add it to your server.cfg to start it
2. Enter the table in the database (jsfour_dna.sql)
3. The script is based on the existence of load pointers in your database. There are 4 numbers that are unique to each player. This is something you must add. Either via a script that does it for you or you can do it manually for each player. My <a href="https://github.com/jonassvensson4/jsfour-register"> jsfour registry <a/> does this when registering.
4. These are code bits that will enter a menu, depending on how your menu looks like:
 `` `
{label = 'DNA', value = 'dna'}
 if data.current.value == 'dna' then
  local player, distance = ESX.Game.GetClosestPlayer ()
  
  if distance ~ = -1 and distance <= 3.0 then
    TriggerEvent ('jsfour-dna: get', player)
  End
End
 - There is also an event to remove the DNA you have on you. Even this is recommended to have in a menu
Trigger Event ( 'jsfour DNA remove')
`` `
 ### SCREENSHOTS
[Screenshot] (https://i.gyazo.com/0e38567915f677da7746ff263a8c74ba.png)
[Screenshot] (https://i.gyazo.com/72b115711470c1d86c1ced2cc4004fd9.png)
[Screenshot] (https://i.gyazo.com/54333c35e9eb68b5072ecf572f0ff496.png)
[Screenshot] (https://i.gyazo.com/654add0e77ed36d03c560943fb6264d8.png)