#### Installation of SheepShaver
SheepShaver is open-source software that runs on Windows, macOS and Linux. The best guide for setting it up is available [here](https://www.emaculation.com/doku.php/sheepshaver).

We can use SheepShaver to emulate Mac OS 7.5 to 9.0.4 (meaning all versions after the rebrand from System 7 to rebrand to OS X). This is achieved through emulating the hardware of a Power PC based Macintosh. 

For the hardware emulation to work correctly, we need to install an additional PPC Macintosh ROM file. The New World PPC ROM is suitable for versions 8.x+, otherwise get the Old World PPC ROM. 

#### Configuring SheepShaver
Create a new "hard disk" volume of at least 500 MB under the Volumes setting.

I also recommend setting the refresh rate to at least 15 Hz.

To later on boot from a *CD image*: On your host set the CD image to read only, then click Add and make sure the CD image is the first entry in the volumes list. This is because otherwise the virtual machine might try to write on the disk instead and you'll be met with a startup disk error.

Generally speaking, use the Old World PPC ROM, under the Memory/Misc setting in SheepShaver. Set the amount of RAM to at least 64MB (it is lower by default).

If you want, you can also use raw keycodes to reconfigure the bindings. For shortcuts in the virtual machine, the "Command" key is replaced with the left "Alt" key, though this may not be the case for all users. 

Before you can start the machine, you should also prepare the OS installation media. There is a variety of different Mac OS versions available [here](https://macintoshgarden.org/apps/mac-os-install-cd-library).
 

#### Installing the OS from floppy disk images

Before you can install an OS onto the hard disk you created, you must first initialize it with Disk Tools 2. You can do this by adding the DT2 disk as the first disk in the Volumes section. Start the machine and initialize the hard disk that you created in the SheepShaver settings. After this you can remove the Disk Tools 2 disk. 

Generally, add disk 1 as the first entry in the volumes section - then add all of the remaining installation disks (not Disk Tools!) that came with the distribution in ascending numerical order. After this, you can start the machine.

You should be greeted with an installation screen. On the "Install System Software" screen, make sure to click "Switch Disk" until your destination disk is the hard drive you created beforehand. 

Once you've completed the installation, shut down SheepShaver and remove the installation disks from the volumes view. You can now boot to the OS from the hard drive you created beforehand. 

#### Installing the OS from a CD image
Reminder: If you want to install Mac OS 8.6 through 9.0.4, it is best to use the New World ROM, though the Old World ROM will *also* work.

You won't have to separately initialize the hard disk that you've created if using a CD image to install. You can just add the CD image to the list of volumes in SheepShaver and install it onto your hard disk. 

Once you've completed the installation, shut down SheepShaver and remove the CD image from the volumes view. 

Note: If you are greeted with the Mac OS Setup Assistant, it is best to quit it, as it cannot detect network settings and will always hang.

#### Installing additional software

For testing purposes, I will download and run "The Secret of Monkey Island", available [here](https://macintoshgarden.org/games/secret-of-monkey-island). 

The first download will provide us with a compressed version of the game. To uncompress it inside our emulated machine, we will need StuffIt Expander 5.5, available [here](https://macintoshgarden.org/apps/stuffit-expander-55).

Create a folder on your host machine to share with your emulated system. You can point to it with the "Unix Root" option. Place the .sit file in the shared folder. Make sure to move the file out of the shared folder and onto the hard disk of the virtual machine before unzipping it or performing any other actions with it. 

Add the unzipped .toast file as a volume in the SheepShaver GUI and start the emulator. From there you can open the StuffIt disk and run the installer to get the StuffIt Expander.

Now you can just double-click on a compressed file on your emulated system and StuffIt Expander will decompress it. You can now open the "Monkey Island" folder on your emulated Desktop, or try it out with other software available on Macintosh Garden. 

In case the additional software you've downloaded is in an image format, just add it under the volumes section in the SheepShaver GUI. 

Files with the ".dsk" extension are meant for Mini vMac machines and do not function in SheepShaver.

