**About Admin Menu**

<img width="400" height="400" alt="изображение" src="https://github.com/user-attachments/assets/5bececc9-a9cc-4013-958f-d8268a785bb0" />

Manage your Rust server easier and more efficiently with the AdminMenu plugin. Track players, interact with them, edit their data and permissions, as well as change server convars and manage plugins.

**Features:**

    Menu retains its state after closing, you won't lose everything you did before.
    Ability to fully translate the menu into any language.  
    Large range of permissions for each action, will allow you to flexibly customize the admin menu for each group of administrators.
    Quick menu that allows you to perform quick actions
    Full list of players with the ability to filter by online, offline, admins and moderators. Also has a frame of different colors depending on the level of authorization.
    Wide range of information and actions for the selected player.
    Editing convars with search. Has a complete list of editable convars with descriptions for some of them.
    Extensive issue menu by category, with easy management of name, skin and amount (manual, +1, +100, +1000, +10000).
    Plugin management menu. It is possible to reload, unload or load a plugin easily and quickly. Updates occur in real time.
    Ability to create your own custom buttons that execute several commands

**Quick Start:**

    You install the plugin in the plugins folder.
    Give yourself the adminmenu.fullaccess permission.  
    Commands, use one of your choice, one for the player and one for the admin group:  

    o.grant user [name or steamid] adminmenu.fullaccess

    o.grant group admin adminmenu.fullaccess

    Press the X button (swap  seat button) or type adminmenu in the console.
    Enjoy

**Useful stuff:**

    You can quickly open a player in the admin menu. To do this, point at the player and press X.
    You don't have to hover over the player exactly, you will be able to open players within a certain radius of the place you are looking at.

**CUSTOM BUTTONS**
Custom buttons are buttons that when pressed will execute commands on behalf of the administrator, commands can be several, below will be the details.
At the moment, custom buttons can be created in two places: in the quick menu and in the menu when selecting a player. These places are separated in the config.
Button Fields:

    "Execution as server" - Call the command on behalf of the server, not the administrator
    "Label"  - Text that will be on the button, for each such inscription creates a field in the lang file, accordingly you can translate this text into several languages.
    "Commands" - Array of commands that will be executed on behalf of the administrator. Chat commands require a special entry, see examples.
    "Permission"- permission to display and use the button. You need to write the permission that will be after  "adminmenu.".
    Example: if you enter the permission "test"  the permission will be adminmenu.test
    "Position"  - The location for the button, the first number is responsible for the row number, the second for the position within the row, starts from 0.There are limits of locations, if you have gone beyond the limit - the button will not be displayed.
    Common Tags:
        {adminUID} - administrator's id.
        {position} - administrator coordinates (underfoot)
        {view_position} - the position where the administrator is looking (can be used for spawning or something similar)
        {view_direction_forward} - forward view direction of the administrator
        {view_direction_backward} - the direction the administrator is looking backwards
        {view_direction_left} - direction of the administrator’s view to the left
        {view_direction_right} - administrator’s view direction to the right
    Tags for target only:
        {steamid}, {steamID}, {userID}, {STEAMID}, {USERID} - mean the same thing, namely the id of the selected player.
        {target_position} - target coordinates (underfoot)

**Example of commands:**

    chat.say \"/{chat command}\"
    vanish
    ban {steamID}
    teleport {steamID} {adminUID}  

**More information about the grant menu:**
The grant menu includes the full list of items including hidden items as well as custom items created by the CustomItemDefinitions library.
The menu can be accessed from the navigation or from the menu of the selected player. When issuing itself has categories.
Search works in any registry by any part of the name or short name.  
Has a page system at any stage.

**More information about the buttons in the Quick Menu:**

    [Teleport to 0 0 0] - Teleport to coordinates 0 0 0.
    Requires  adminmenu.quickmenu.teleportto000 permission
    [Teleport to Deathpoint] - Teleport to your deathpoint.
    Requires adminmenu.quickmenu.teleporttodeath  permission
    [Teleport to Spawn point] - Teleport to a random spawn point.
    Requires adminmenu.quickmenu.teleporttospawnpoint  permission
    [Kill Self] - Kill Self, kills even when immortal.
    Does not require permission.
    [Heal Self] - Fully heal yourself.
    Requires  adminmenu.quickmenu.healself  permission  
    [Call Heli] - Call Helicopter to yourself (arrives in time).
    Requires adminmenu.quickmenu.helicall  permission
    [Spawn Bradley] - Spawn bradley on yourself.
    Requires adminmenu.quickmenu.spawnbradley  permission

**More information about the buttons in the menu of the selected player:**

    [Teleport Self To] - Teleport yourself to the selected player.
    Requires adminmenu.userinfo.teleportselfto permission
    [Teleport To Self] - Teleport the selected player to yourself.
    Requires adminmenu.userinfo.teleporttoself  permission
    [Teleport To Auth] - Teleportation to random authorization (TC).
    Requires adminmenu.userinfo.teleporttoauth permission
    [Teleport to Deathpoint] - Teleportation to a player's deathpoint.
    Requires adminmenu.userinfo.teleporttodeath  permission
    [Heal] - Full healing, including metabolism.
    Requires adminmenu.userinfo.fullheal  permission
    [Heal 50%] - Half healing.
    Requires adminmenu.userinfo.halfheal permission.
    [View Inventory] - View and edit player's inventory.
    Requires adminmenu.userinfo.viewinv  permission
    [Strip Inventory] - Clear player's inventory.
    Requires adminmenu.userinfo.stripinventory permission
    [Unlock Blueprints] - Unlock all Blueprints.
    Requires adminmenu.userinfo.unlockblueprints  permission
    [Revoke Blueprints] - Reset all Blueprints.
    Requires adminmenu.userinfo.revokeblueprints permission.  
    [Kill] - Kill a player.
    Requires adminmenu.userinfo.kill  permission
    [Kick] - Kick a player.
    Requires adminmenu.userinfo.kick permission
    [Ban] - Ban a player.
    Requires adminmenu.userinfo.ban  permission

**More information about the buttons in the menu of the selected group:**

    [Remove Group] - Remove group, has confirmation.
    Requires adminmenu.groupinfo.removegroup  permission
    [Clone Group] - Clone group with the ability to copy users.
    Requires adminmenu.groupinfo.clonegroup permission

**Permissions:**

    adminmenu.use - Ability to use admin menu with basic set. Open tab quick menu (each button has its own permission, without permissions is present only kill yourself button) and the list of players.
    adminmenu.fullaccess - Full access to all functions without the need for each permission, includes also adminmenu.use. It is recommended to give only to the main administrators.
    adminmenu.quickmenu.teleportto000 - Access to the button in the quick menu, teleportation to coordinates 0 0 0 0.
    adminmenu.quickmenu.teleporttodeath - Access to the button in the quick menu, teleportation to the point of your death.
    adminmenu.quickmenu.teleporttospawnpoint - Access to the button in the quick menu, teleportation to a random spawn point.
    adminmenu.quickmenu.healself - Access button in quickmenu, heal yourself completely.
    adminmenu.quickmenu.helicall - Access to the button in the quick menu, call a helicopter to yourself (arrives in time).
    adminmenu.quickmenu.spawnbradley - Access button in quickmenu, spawn bradley.
    adminmenu.userinfo.teleportselfto - Access to the button in the menu of the selected player, teleportation to the selected player.
    adminmenu.userinfo.teleporttoself - Access to the button in the menu of the selected player, teleport the selected player to himself.
    adminmenu.userinfo.teleporttoauth - Access to the button in the menu of the selected player, teleportation to random authorization (TC).
    adminmenu.userinfo.teleporttodeath - Access to the button in the menu of the selected player, teleportation to the place of death of the player.
    adminmenu.userinfo.fullheal - Access to the button in the menu of the selected player, full healing, including metabolism.
    adminmenu.userinfo.halfheal - Access to the button in the menu of the selected player, half healing.
    adminmenu.userinfo.viewinv - Access to the button in the selected player's menu, view and edit the player's inventory.
    adminmenu.userinfo.stripinventory - Access to the button in the menu of the selected player, clear the player's inventory.
    adminmenu.userinfo.unlockblueprints - Access the button in the menu of the selected player, unlock all drafts.
    adminmenu.userinfo.revokeblueprints - Access to the button in the menu of the selected player, reset all drafts.
    adminmenu.userinfo.kill - Access the button in the selected player's menu to kill the player.
    adminmenu.userinfo.kick - Access the button in the selected player's menu to kick the player.
    adminmenu.userinfo.ban - Access to the button in the menu of the selected player, ban the player.
    adminmenu.groupinfo.removegroup - Access to the button in the menu of the selected group, the ability to remove the group.
    adminmenu.groupinfo.clonegroup - Access to the button in the menu of the selected group, the ability to clone the group.
    adminmenu.convars - View and edit convars.
    adminmenu.permissionmanager - View and edit permissions in groups, player groups, create, delete and clone groups (requires additional permissions from these buttons).
    adminmenu.pluginmanager - Access to plugin management, reloading, unloading, loading plugins.
    adminmenu.give - Access to give resources, as well as yourself and the selected player.

<img width="2560" height="1440" alt="1" src="https://github.com/user-attachments/assets/f4574d64-abbd-4f71-b475-47d81ccbaa3a" />

![2](https://github.com/user-attachments/assets/06ed8541-3de5-4b67-b7d6-98bc201abd7b)

<img width="2560" height="1440" alt="3" src="https://github.com/user-attachments/assets/f19cd4e3-c190-4f38-b253-8347bb881010" />

![4](https://github.com/user-attachments/assets/f69f5d7c-4af4-446d-8d8c-ce5394e2343e)
