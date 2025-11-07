# KH2-Rando-Archipelago-Linux-Guide

# KH2 Archipelago Setup for Steam Deck

> [!IMPORTANT]
> - This guide was built specifically for Steam Deck users, so if you're on another Linux distro, you may have to play around with more things to get it all running smoothly.
> - You will have to switch to Desktop Mode and use a mouse and keyboard, an external display is HIGHLY recommended but everything is possible on the Deck itself.
> - This guide assumes you have already set up KH2 for use with the standard Randomizer tools. If you have not, please consult the [wonderful guide](https://github.com/KHOmega/KH-PC-and-Linux-Setup/blob/main/GoA-Randomizer-linux-setup.md) by [KHOmega](https://github.com/KHOmega) 

This guide is to help Steam Deck/Linux users get set up with Archipelago for use with Multi-World Randomizers. You could use it for single game randomizers as well, but the KH2 Rando community already has guides and tools in place for single game purposes. 

As a note, I don't play Archipelago as much as I do base rando, so if something updates and breaks the guide, just reach out and I'll work on getting things up to date!

# Installing Archipelago

You'll want to go to the [Archipelago GitHub](https://github.com/ArchipelagoMW/Archipelago/releases/latest) page to download the most recent stable release of the Windows version, not the Linux version. To ensure that the game and other tools all work on the same layer, we have to use the Windows version rather than the Linux native version. Once you have the .exe downloaded, ensure that you know the file path to the .exe itself. 

Moving to Steam, you will want to right click on your copy of Kingdom Hearts in your Library and open up the Properties. Under the Launch Options, enter the following string `STEAM_COMPAT_LAUNCHER_SERVICE=proton WINEDLLOVERRIDES="version,dinput8=n,b" %command%` to ensure that the game launches with Proton and choose either Experimental or 9.0-4 as the Compatability Layer to force the game to run under. Many guides suggest Experimental, but I've had no issues with 9.0-4 to date. 

After updating Kingdom Hearts, you will want to Install a Non-Steam game, choosing to add the Installer you downloaded earlier. After getting it in your library, once again go to the Launch Options and this time enter `STEAM_COMPAT_LAUNCHER_SERVICE=proton` and enable to same Proton layer you chose for KH. 

Now, launch Kingdom Hearts 2 and choose `New Game` from the main menu, and then tab over to another window to leave the game running. 

At this point, you will need to open Konsole and run the following command, ensuring that the line break is held where it is listed:

`/...path.../...to.../steamapps/common/SteamLinuxRuntime_sniper/pressure-vessel/bin/steam-runtime-launch-client \
--bus-name=com.steampowered.App2552430 -- wine /...path.../...to.../Setup.Archipelago.0.6.3.exe`

Your file paths may vary slightly for where the download is, and I haven't had enough exposure to know if there is any variation in the strings for where `steam-runtime-launch-client` is located, so you'll need to do some digging. Good practice would be to keep a text file in an easy to find location that you can keep the command strings saved for ease of access on subsequent uses, and to allow editing for the correct file paths. On my Deck, the full command looks like:

`/home/deck/.steam/steam/steamapps/common/SteamLinuxRuntime_sniper/pressure-vessel/bin/steam-runtime-launch-client \
--bus-name=com.steampowered.App2552430 -- wine /home/deck/Downloads/Setup.Archipelago.0.6.3.exe`

Running this will open the installer for Archipelago, which you will just follow the on screen instructions to get set up. Afterwards, assuming you leave the box enabled, the base Archipelago client should open on its own!

# Launching the KH2 Archipelago Client

Next, you will return to Steam and add another Non-Steam Game, this time you will want to add the ArchipelagoKH2Client.exe, and once again add `STEAM_COMPAT_LAUNCHER_SERVICE=proton` and match the compatibility layer with Proton.

From here, you will use Konsole to launch the Client itself, so if you hadn't made a text file with the strings saved by now, this would be a good time to start one. 

The command is largely the same as what we used for the installer, just ensuring that you point to the client instead. Generic version looks like:

`/...path.../...to.../steamapps/common/SteamLinuxRuntime_sniper/pressure-vessel/bin/steam-runtime-launch-client \
--bus-name=com.steampowered.App2552430 -- wine /...path.../...to...//ArchipelagoKH2Client.exe`

And again for reference, this is what I use to launch the Client:

`/home/deck/.steam/steam/steamapps/common/SteamLinuxRuntime_sniper/pressure-vessel/bin/steam-runtime-launch-client \
--bus-name=com.steampowered.App2552430 -- wine /home/deck/.local/share/Steam/steamapps/compatdata/2552430/pfx/drive_c/ProgramData/Archipelago/ArchipelagoKH2Client.exe`

After you launch the client, refer back to your Archipelago room to enter the connect command. Once you've done so, you're ready to play!

If you want to use the AP tracker, you would follow the same steps as before, adding the .exe to steam, setting the Launch Options, Proton layer, and then launching from Konsole. 

# Credits

This was largely built from the work I did on the standard rando guide I have up for the KH2 Tracker and Livesplit, so I'll give some shoutouts to the folks who got me to the point I could compile this.

A MASSIVE thanks goes to [baili0411](https://github.com/baili0411) for suggesting the method to launch from Konsole, which has opened up more options for the Linux side of Rando. 

Another huge shoutout goes to [KHOmega](https://github.com/KHOmega) for maintaining the Linux guides that let me and many others join the rando scene.

Lastly, a big thank you to all the contributors for the Randomizer and Guide on the [main page](https://tommadness.github.io/KH2Randomizer) for the Randomizer. 

If anything breaks or if you have any issues, feel free to send me a DM on Discord and I'll see if I can help!
