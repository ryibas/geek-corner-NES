Nothing quite hits the memory feels like the 'ding' sound of Mario collecting a coin. Remember the old school video games of years past? The original NES? Mario games? For those of us old enough to remember when video games didn't have the ability to 'save' games, that 'ding' sound should bring back some fond/frustrating memories!

As a side note - that original NES? It's over 30 years ago that bugger was released. 

Since most of us in IT are tinkers at heart, I'm sure most of us have speculated as to what went into building one of these games back in the day. 

Well...

This Geek's corner covers creating a very simple NES game from the ground up in assembly; the tools required, walking through some of the steps, and getting it running on a PC using an emulator. If you'd like - you can actually take it a step further and run the game on a Raspbery Pi with an Xbox controller. 
 
Level I - Bring on the assembly
 
Ingredients Needed
PC - Really any Windows machine will work for this.
Visual Studio Code - A great lightweight editor that works surprisingly well for editing assembly code.
https://code.visualstudio.com/
Emulator (Fceux) - This is the application you will use to actually run your NES game.
http://www.fceux.com/web/home.html
NESASM3 - This is the application that takes your source code (.asm file) and compiles it into a .nes file which can then be opened by the Fceux emulator. 
NESASM3 Source Code - https://github.com/toastynerd/nesasm
NESASM3 Application - http://www.nespowerpak.com/nesasm/NESASM3.zip
YY CHR - The application that can be used to create sprite images. This was used to create the letters and the little monster in the game.
http://www.romhacking.net/utilities/119/

Always be prudent when downloading things from the Internet. We don't need any viruses for the Andy(s) to get worked up about. In fact, other than MS Visual Studio Code - don't download these tools to your work laptop... 
 
Directions
 
1.) Download the code (.zip file) for this project at https://github.com/geek-corner-NES/geek-corner-NES and extract the .zip file to a folder somewhere on your computer (or use git to pull it down).



2.) Copy the nesasm3.exe file downloaded in the ingredients and copy it to the /source folder in step #1.



3.) Load up Visual Studio Code. You may want to install one of the 6502 Assembly extensions available. These help with syntax highlighting. Open the geek-corner-NES folder that you just downloaded and open up the geek-corner-NES.asm file once the folder is open. This file is the entire program, which then compiles down into your NES ROM.



4.) So now that you've taken a look at the code, you'll probably want to take a peek at the rockin' graphics of this thing. To do this open up the YY CHR program you downloaded in the ingredients and navigate to the folder where you extracted the code. Open up the holidays.chr file and you should see a screen similar to below. You can use the tool to create/modify the lettering, image, or add your own sprites to the file.



5.) Ready to compile the program! Open up a terminal/command line window and navigate to the (source) directory that the geek-corner-NES.asm file is located in. Run ‘nesasm3.exe geek-corner-NES.asm’ and if no errors come out, you’ll see a resulting ‘.nes’ file that was created. This file is the compiled version of the .asm code and the .chr sprites. You should see something that looks like the following output. If there were any compilation issues, you would see them listed in the terminal/command output.



6.) Open up the Fceux - NES emulator application and navigate to the folder where the ‘.nes’ file that was created in the previous step exists. You can then open this file and the ‘game’ will start up. You should see a little car in the center of the screen that you can move around with arrow keys.



7.) Explore. Tweak the code, the sprites, recompile, and re-open the .nes file in the Fceux application to see your results. 
 
Level II - Run your new NES game on your Raspberry Pi
 
So if you've gotten this far and are like - "Well so what, when do we get to the geeky stuff". You can take your freshly minted ‘.nes’ file to the big screen and move that little monster with real live Xbox controllers. Follow the instructions below.
 
Ingredients for the Icing on the Pi
Raspberry Pi (any version will work)
Wired Xbox 360 Controller (Most other controllers will work - check the RetroPie site for compatibility)
SD or MicroSD card - This is the storage mechanism that you will install RetroPie on. 
RetroPie - This is the operating system that runs the various game emulators and runs on the Pi.
https://retropie.org.uk/

Directions
 
1.) Plugin the USB Controller and HDMI cable into the Pi.
 


2.) Following the instructions on the RetroPie site, install RetroPie to the SD/MicroSD card. Insert the SD/MicroSD card into the Pi and power it on. You should see the Raspberry Pi boot up into the RetroPie menu screen.



3.) Once RetroPie is up and running on the Pi, you’ll want to follow the instructions on copying your NES ROM (the .nes file) created above to the Raspberry Pi. There are great instructions for this on RetroPie wiki. I found the easiest was to use USB thumb drive to transfer the ROM between your PC and the Raspberry Pi. You do need to be careful when powering down the Raspberry Pi as it is easy to corrupt the RetroPie OS install on the Pi. If this happens you’ll just need to redo the previous step to get the RetroPie OS reinstalled.
 


4.) Play the geek-corner-NES ROM and enjoy HOURS (well maybe a few minutes) of fun.


Level III - Contribute to the geek-corner-NES game
 
If you tweaked the code, sprites, or made any improvements send me a GitHub pull request!
 
Tooling for Mac's
Visual Studio Code - Hey this runs on a Mac too! Yay.
https://code.visualstudio.com/
Homebrew - Package manager for the Mac. You don’t need this but, it makes installing the tools much easier.
http://brew.sh/
Emulator - OpenEmu - This can be used on the Mac instead of Fceux.
http://openemu.org/
NESASM - You can find these binaries built for Windows pretty easily, for the Mac - you’ll probably need to compile the NESASM source to run it.
Sprite Editors - There really aren’t great NES sprite editors available that I’ve found. Many suggestions just point to loading up a Windows VM in Bootcamp or parallels. 