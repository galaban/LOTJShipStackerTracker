# Galaban's Ship Stacker and Tracker
This is a plugin to stack the ships and display them in a much more readable, compact fashion.  In addition to that, it will remember which ships belongs to whom, displaying that information next to the ship name.

This is for the Legends of the Jedi mud.

Commands:

    shipstacker            - Shows the help screen
    shipstacker <format>   - Sets the format for the output.  Options are 0, 1, 2, 3, or 4
    shipstacker enable     - Enables it, if you ever disable it
    shipstacker disable    - Disables it, obviously.  Kills the triggers, etc.
    
    shipstacker db <option> - Used to access the database of ships

    shipstacker locatenext - calls "locateship" for the next unowned ship in the database 
    shipstacker locateoldest - calls "locateship" for the most stale lookup in the database

## To install
1. Download the raw file from github:
https://raw.github.com/galaban/moons/master/Galabans_Ship_Stacker.xml
2. Place the raw file into your "plugins" directory.  This is found in your Mushclient folder under /worlds/plugins.
3. Install the plugain in MushClient.  From the "File" menu, choose "plugins", then "Add".  Select the file and choose "OK".

Note: If you do not already have the lotj_colors.lua file in your plugins directory, you will need that too.

## How to use this plugin

How To Use This Plugin:
1. To store these ships, the plugin keeps a list of valid pads.  This is to workaround the poor MSDP implementation in LOTJ.  To make a pad valid, you must call locateship on a ship that is on that pad. This will add the pad to the valid list of pads. When this happens, you will see: Not storing ships.  Uncertain pad...

2. When you first enter a pad, it will not store the ships on the pad. (Due to the poor MSDP implementation.)  You must look at the pad in order to store the ships.  (And be on a 'valid' pad. See #1 above). When this happens, you will see: Not storing ships.  Uncertain pad...

3. On Corellia you must use logships to log the ships on the three main pads.  Again, the MSDP code is the reason.  However, it is the only solution to this problem. When this happens, you will see: Not storing ships... use logships to...

Make sure to wait half a second or so before logging the ships on the pad. Otherwise, it will cause considerable performance and ships showing up on the wrong pad.
