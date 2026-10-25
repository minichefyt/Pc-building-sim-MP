PC Building Simulator Co-op 0.5.0
================================================

Play the career together: one player hosts, the others join the host's workshop.
Shared: money, shop orders, inventory, deliveries, jobs, emails, days, the PCs on every bench
(including on/off), PCs being carried, storage, and desk peripherals.
Not shared yet: furniture, the post-it board, what is on a running PC's screen. Other players
look like a bean in the color they picked, with their name above it.

Was made with Claude opus 5.5

New in 0.5.0
  - A new co-op window (F7) with Host / Join tabs, your Radmin address shown for the host,
    and recent hosts as one-click buttons.
  - Pick your bean color (12 colors, Random, or mix your own).
  - One player per PC: while someone works on a PC, a marker in their color floats above it
    ("<name> is working here") and nobody else can work on it, pick it up, swap it or switch it
    on or off until they step away.
  - The host can bring a player, or everyone, to where the host stands.

This is an early test build. Expect bugs. Only play with people you trust: the host sends its
save to the others over the network.

Everyone needs: PC Building Simulator (the first game, Steam or Epic), this same mod version,
and Radmin VPN.


UPDATING FROM 0.4.0
-------------------
Copy everything from this package into the game folder again and say yes to replacing files.
(Only BepInEx\plugins\PCBSCoop\PCBSCoop.dll really changed.) Everyone must update: 0.4.0 and
0.5.0 cannot play together.


1. BACK UP YOUR SAVES (host especially)
---------------------------------------
Open the game folder (see step 3) and copy the "Saves" folder somewhere safe.
The host's career is the one you play together and it is saved as normal.
The joining player's own saves are not touched (their game does not save while joined).


2. RADMIN VPN (connects your PCs as if they were on the same network)
---------------------------------------------------------------------
Download it from the official site only: https://www.radmin-vpn.com

Host:
  a. Install and open Radmin VPN.
  b. Network > Create network. Pick a network name and a password.
  c. Send the name and password to your friend.

Friend:
  a. Install and open Radmin VPN.
  b. Network > Join network, enter the name and password.
  c. You should see the host in the list with a green dot.


3. INSTALL THE MOD (both players)
---------------------------------
Find the game folder:
  Steam: Library > right-click PC Building Simulator > Manage > Browse local files
  Epic:  Library > PC Building Simulator > "..." > Manage > the folder icon next to "Installation"
The right folder contains PCBS.exe.

Copy EVERYTHING from this package into that folder (the BepInEx folder, winhttp.dll,
doorstop_config.ini, .doorstop_version, changelog.txt). Afterwards winhttp.dll must sit right
next to PCBS.exe.

Check it works: start the game once, press F7 on the main menu: the co-op window opens and its
top-right corner says 0.5.0.


4. PLAY
-------
Everyone: press F7 to open the co-op window. Type your name and pick your bean color.
(You can change both later, even while playing; the others see it right away.)

Host:
  a. On the main menu, open the "Host a game" tab.
  b. The window lists your addresses. Give your friends the one marked "Radmin VPN"
     (it starts with 26.). "Copy" puts it on the clipboard.
  c. Click "Start hosting", then load your career (Continue or Load).
  d. The first time, Windows Firewall asks about PCBS.exe: click Allow access.
     If your friend cannot connect, see "Problems" below.

Friend:
  a. STAY ON THE MAIN MENU. Open the "Join a game" tab.
  b. Type the host's Radmin address (26.x.x.x), leave the port at 27960, click Join.
     Next time the address is under "Recent".
  c. Wait. The game loads the host's workshop by itself (the window shows progress).

While playing, the window shows everyone with their color, ping and what they are doing.
The host has a "Bring" button per player and "Bring everyone to me". A player who is busy
(working on a PC, in a menu) is brought over as soon as they step away, if that is within a minute.

Good to know:
  - A PC someone is working on is locked: you see "<name> is working on this PC" instead of the
    usual actions. It unlocks when they step away (or disconnect).
  - Ending the day works from either game. The host's game does the actual day change.
  - Quit the session by closing the game (or "Leave" / "Stop hosting" in the window).
    If the host quits, everyone else's session ends; go back to the main menu.
  - While the window is open in the workshop, walking and looking around are paused so you can
    type. Close it with F7 to move again.


5. PROBLEMS
-----------
Friend cannot connect:
  - Both of you must be online in the same Radmin VPN network (green dot).
  - The host's window must say "hosting on UDP port 27960".
  - Windows Firewall on the host: Windows Security > Firewall & network protection >
    Allow an app through firewall > find "pcbs" (PCBS.exe) and make sure it is allowed for the
    network type Radmin VPN uses. Radmin often counts as a "Public" network, so tick Public
    for PCBS.exe while you play. You can untick it again afterwards.
  - Both must run this same version (0.5.0). Different versions refuse to connect.

Steam + Epic: the mod does not use Steam or Epic online features, so mixing should work, but it
has not been tested yet. If joining fails between a Steam and an Epic copy, please send the logs.

Anything strange: close both games and send both BepInEx\LogOutput.log files, plus what you did
just before it happened.


6. UNINSTALL
------------
In the game folder delete: the BepInEx folder, winhttp.dll, doorstop_config.ini,
.doorstop_version and changelog.txt. The game is then exactly as before.
