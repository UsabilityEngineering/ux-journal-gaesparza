# Map the World

By: Gabe Esparza 11/22/2024

I recently embarked on a journey to create a live map of a Minecraft Server I host with a few friends. The end goal was to have a live updating map that would show the world, players, and any landmarks we had decided on. I decided to give Unmined a try.

  

In game it is possible to create smaller scale maps that show a select part of the world. It is not uncommon to then take these small maps and frame them together to create a larger collective map typically referred to as a map wall.

<img src="https://github.com/UsabilityEngineering/ux-journal-gaesparza/blob/main/assets/map.png" width="216" height="216">
<img src="https://github.com/UsabilityEngineering/ux-journal-gaesparza/blob/main/assets/map_wall.png" width="540" height="304">

Using Unmined was a similar process to in game. Unmined parses the world data found in their Minecraft world files. This then chops the world that has been rendered so far into 256x256 block tiles and then compiles those individual tiles into a large map.

<img src="https://github.com/UsabilityEngineering/ux-journal-gaesparza/blob/main/assets/single_map.png" width="216" height="216">
<img src="https://github.com/UsabilityEngineering/ux-journal-gaesparza/blob/main/assets/large_map.png" width="729" height="295">

Due to the nature of Minecraft being a cubic game, it makes it really easy mathematically to determine and show world areas. Unmined appears to work by rendering a 256x256 block of the map. And then stitch those together into a larger world map. Unmined applies **consistency and standards** by following and taking advantage of how a Minecraft world is generate.

The experience diminshes when trying to add custom markers to the world. I could not figure out how to add custom markers, I was pretty dedicated to getting this working. I decided to try to read the app documentation. While I was able to figure it out I do not think this is a **learnable** process as it involves creating the marker in a custom marker JSON file. I have the benefit of having coding experience, but most Minecraft players would not be able to do this. I can appreciate how detailed the documentation is as this helped me understand how to create a marker. 

<img src="https://github.com/UsabilityEngineering/ux-journal-gaesparza/blob/main/assets/markers.png" width="1077" height="488">

Players are not natively added into those world data tiles, but can be added by finding the player information in the Minecraft world files. Minecraft stores the player's last position in the player data. Unmined just reads that data and shows the player at that position on the map. In the Unmined menu I saw a familiar player-like icon. Clicking on that reveals a problem. The players show as player\_id strings, a jumbled mess of letters and numbers assigned to each player. I don’t know which player is which due to player\_id being stored in the player data files. The only way I would know which player I am is by remembering where I was when I last logged off.

<img src="https://github.com/UsabilityEngineering/ux-journal-gaesparza/blob/main/assets/map_players.png" width="846" height="303">

Next was to figure out how to show these players and markers. In the map view there are some map options that look promising. This feels like a **common convention** that is present in online maps. I click on the map drop option. It appears that Players and Custom Markers are turned off by default. This makes some sense since markers are created by the user so having these enabled by default is unnecessary in the case where the user doesn’t add markers. Turning players and makers on made them appear.

<img src="https://github.com/UsabilityEngineering/ux-journal-gaesparza/blob/main/assets/display_markers.png" width="665" height="233">
