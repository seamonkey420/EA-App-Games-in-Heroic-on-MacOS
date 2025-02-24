# EA-App-Games-in-Heroic-on-MacOS
Just a quick guide on how to get EA App working in Heroic and also how to install individual EA Games in Heroic.



Hello all, just wanted to make a note that the EA App (windows) is working for me in Heroic 2.15.2 and Wine Crossover 23.7.1.1-1 and Whiskey.  I can install my EA games and play in Heroic finally!  The last few days i finally got some time to tinker and setup my Heroic install.  One thing i really wanted was to be able to play a few of my EA Games i had but couldn't get the EA App to install in Whiskey or in Heroic and really couldn't find any newer related guides/notes.  So today i decided to start from scratch and finally got a working solution to be able to install and run EA Games in Heroic and also have EA background services running for online (at least worked for NFS Heat when i tested). Main thing was to use whiskey wine to run preinstall ea app installer in heroic when setting up the new game, and then use crssover wine to run once game is setup.  its a bit clunky but seems to work!
Here is the process i used to get it all going if anyone else is having issues.  Verified it works with my Need for Speed Heat (online even connects).  

Installing EA App in Heroic:
Install Whiskey 2.3.4
In Heroic, create new game, use wine crossover as wine version (i also have whiskey installed in macos too)
Run exe pre-install, choose the EAappInstaller.exe (get latest from ea)It will load up the EA App installer, click Install.  It will do some installing and you'll see some popups.  Once it loads to a blank black screen, force quit wine64-preloader in  macos. (We need to use the d3dcompiler_47 dll to show the dialog but you can't do that until you have the app/game installed in heroic)
In the new game window, point the exe to the eadesktop.exe app and click on finish

Fixing EA App after Install:

In Heroic, right click on the EA App, go to Settings.  At the bottom click on winetricks,  then install the d3dcompiler_47 and dotnet48 in winetricks, the dotnet48 will take a few minutes and may show some errors, let it run until you see it shown in the "Installed Components" at the top.
In the settings screen, make sure the wine crossover 23.7.1.1-1 for crossover/wine version is set, also check the "auto install/update dxvk on prefix"
Launch ea app in heroic, it will go through and do a repair on the install and this time it should actually load the ea desktop app. The d3dcompiler_47 is needed to display that dialog window and heroic's pre-installer doesn’t allow us to add that dll so this seems to work around it!!
Once the EA App actually opens, login and let it load the launcher/desktop.  You can now choose to download/install in the EA App!!  I then use this prefix folder as a basis for making new EA Games.  See below if you want to do that, otherwise you can just start installing EA Games via the EA App and to run them just load up the ea app in heroic and choose the game via the ea launcher/desktop.

Making EA Games their own app (not running the ea launcher to run) in Heroic:
Cont from above, Quit the EA App and verify its closed/stopped running in Heroic
Now go to where you have your prefixes saved.   If you named your app EA App, copy that folder paste in same prefixes folder.  Rename folder to what ea game you want (ie Need for Speed Heat).
Open Heroic, Add New Game
Name it same as folder (ie Need for Speed Heat)
Let icon download/parse
choose wine options, choose the crossover wine and then for prefix folder it should already have our game listed, if not browse to the prefix folder we copied and renamed
choose the exe that launches game (ie c:\program files (x86)\EA Games\Need for Speed Heat\NeedForSpeedHeat.exe
Click Finish.  
You should now be able to launch your game w/ea app running in background!
If you want to do another game, just load up ea app in heroic, uninstall the prev game.  then install new game and again copy the prefix and add back to heroic 

I have confirmed this working so far with NFS Heat and Madden 22. I will try a few other games later tonight.  Let me know if this worked for ya or not. 
