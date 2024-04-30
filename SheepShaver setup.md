#### Installation of SheepShaver
SheepShaver is open-source software that runs on Windows, macOS and Linux. The best guide for setting it up is available [here](https://www.emaculation.com/doku.php/sheepshaver).

We can use SheepShaver to emulate Mac OS 7.5 to 9.0.4 (meaning all versions after the rebrand from System 7 to rebrand to OS X). This is achieved through emulating the hardware of a Power PC based Macintosh. 

For the hardware emulation to work correctly, we need to install an additional PPC Macintosh ROM file. The New World PPC ROM is suitable for versions 8.x+, otherwise get the Old World PPC ROM. 

#### Configuring SheepShaver
Get the MacOS_7.5.3.zip from [here](https://macintoshgarden.org/apps/macintosh-os-755). 

Version 7.5.3 should be less buggy than previous versions and shows the rebrand, which is why this version was chosen to represent Mac OS 7.

Create a new "hard disk" volume of at least 500 MB under the Volumes setting.

To later on boot from a CD image: On your host set the CD image to read only, then click Add and make sure the CD image is the first entry in the volumes list.

For version 7.5.3, let's use the Old World PPC ROM, under the Memory/Misc setting in SheepShaver. Set the amount of RAM to at least 64MB (it is lower by default).
 

#### Installing the OS

Before you can install an OS onto the hard disk you created, you must first initialize it with Disk Tools 2. You can do this by adding the DT2 disk as the first disk in the Volumes section. Start the machine and initialize the hard disk that you created in the SheepShaver settings. After this you can remove the Disk Tools 2 disk. 

If using the same version as I am, add disk 1 as the first entry in the volumes section - then add all of the remaining installation disks (not Disk Tools!) that came with the distribution in ascending numerical order. After this, you can start the machine.

You should be greeted with a MacOS 7.5.3 installation screen. On the "Install System Software" screen, make sure to click "Switch Disk" until your destination disk is the hard drive you created beforehand. 

Once you've completed the installation, shut down SheepShaver and remove the installation disks from the volumes view. You can now boot to MacOS 7.5.3 from the hard drive you created beforehand. 

#### Installing additional software

For testing purposes, I will download and run "The Secret of Monkey Island", available [here](https://macintoshgarden.org/games/secret-of-monkey-island). 

The first download will provide us with a compressed version of the game. To uncompress it inside our emulated machine, we will need StuffIt Expander 5.5, available [here](https://macintoshgarden.org/apps/stuffit-expander-55).

Create a folder on your host machine to share with your emulated system. You can point to it with the "Unix Root" option. Place the .sit file in the shared folder.

Add the unzipped .toast file as a volume in the SheepShaver GUI and start the emulator. From there you can open the StuffIt disk and run the installer to get the StuffIt Expander.

Now you can just double-click on a compressed file on your emulated system and StuffIt Expander will decompress it. You can now open the "Monkey Island" folder on your emulated Desktop, or try it out with other software available on Macintosh Garden. 


