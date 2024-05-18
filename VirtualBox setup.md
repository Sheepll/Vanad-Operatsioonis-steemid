#### Installation of VirtualBox
VirtualBox is available on Windows, MacOS and Linux, you can get it from [here](https://www.virtualbox.org/wiki/Downloads).

The User Manual available on their website gives a good overview of what the software is capable of doing and what kind of guest operating systems can be run.

#### Installing on Linux distributions
Running VirtualBox may not be as straightforward on Linux hosts as it is on other operating systems. I recommend carefully reading the installation guide created for your specific distribution, otherwise the likelyhood of running into problems is quite high. 

For example, the [Debian guide](https://wiki.debian.org/VirtualBox) has a good "Troubleshooting" section. You can always also read the [ArchWiki guide](https://wiki.archlinux.org/title/VirtualBox) that has plenty examples of running VirtualBox from the command line.

#### Configuring VirtualBox
For each installation, you may have to reconfigure VirtualBox for the software to work as wanted. Generally you won't have to change much aside from the storage devices and memory, especially in the case of newer operating systems, as VirtualBox is capable of doing most of the configuration for you.

For example, when installing Windows 1.04, you can use [this guide](https://i12bretro.github.io/tutorials/0066.html), which specifies the configurations you should choose both in the VirtualBox interface and the OS install (only up to 4MB of memory, small hard disk). 

In the VirtualBox settings you can also configure the boot order and used boot devices, in addition to mounting both hard disks and removable devices prior to booting. 


#### Installing an OS
For Windows 1.04 to work properly, it's reccomended to use MS-DOS 3.30, as that is what it was meant to be used on. 
To install MS-DOS on an empty hard disk, you need to do the following:
1. Have the first floppy disk inserted into the machine
2. Partition the hard disk: FDISK /C
3. Format the hard disk: FORMAT C: /S
4. Install the system on the hard disk: 
    SYS C:
    MD C:\DOS
    COPY A:\ C:\DOS
    COPY A:\COMMAND.COM C:\
5. Swap out the first disk for the second
6. COPY A:\ C:\DOS

Then, for installing Windows 1.04, do the following
1. Insert the first floppy disk into the machine
2. Go to the floppy disk: A:
3. SETUP
4. This starts the setup. Make sure to select keyboard device nr 1, pointing device nr 7 and graphical device nr 3.
5. Switch to the correct floppy disks when prompted.
6. You can start Windows 1.04 from C: by going to the Windows directory and typing WIN

Generally, I recommend you familiarize yourself with the capabilities and requirements (in addition to those of VirtualBox) of an OS before you attempt an install.
**Notes**
1. For installing Windows 95, you can follow [this](https://mrabandonware.wordpress.com/2018/02/11/tutorial-installing-windows-95-using-oracle-virtualbox/) guide. Typically you will need to reduce CPU acceleration to around 90% for both Windows 95 and Windows NT 4. 

2. Instead of a boot disk, you can also install MS-DOS 3.30 and then boot the CD-ROM from there.

3. For a Vista install, it's reccomended you choose something other than SATA as a controller.

4. You may need product activation codes for operating systems past Windows XP. These should be available alongside an installation disk.


#### Guest Additions 
VirtualBox provides a simple quality-of-life improvement in their Guest Additions .iso. Check out what guest-systems are supported [here](https://docs.oracle.com/en/virtualization/virtualbox/7.0/user/guestadditions.html#additions-windows).

In case the OS you've installed on your guest is not supported for Guest Additions, you can simply transfer files by creating an .iso file out of them and then mounting it in the virtual machine. This way, you can also provide third-party drivers (if available) to the guest that accomplish similar things to Guest Additions.

You can add and remove disks while the virtual machine is working as well, so it is not a lot slower than using a shared folder. Software for creating disk images is abundant and usually free, for example you can use Brasero or mkisofs.

