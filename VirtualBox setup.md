#### Installation of VirtualBox
VirtualBox is available on Windows, MacOS and Linux, you can get it from [here](https://www.virtualbox.org/wiki/Downloads).

The User Manual available on their website gives a good overview of what the software is capable of doing and what kind of guest operating systems can be run.

#### Installing on Linux distributions
Running VirtualBox may not be as straightforward on Linux hosts as it is on other operating systems. I recommend carefully reading the installation guide created for your specific distribution, otherwise the likelyhood of running into problems is quite high. 

For example, the [Debian guide](https://wiki.debian.org/VirtualBox) has a good "Troubleshooting" section. You can always also read the [ArchWiki guide](https://wiki.archlinux.org/title/VirtualBox) that has plenty examples of running VirtualBox from the command line.

#### Configuring VirtualBox
For each installation, you may have to reconfigure VirtualBox for the software to work as wanted. Generally you won't have to change much aside from the storage devices and memory, especially in the case of newer operating systems, as VirtualBox is capable of doing most of the configuration for you.

For example, when installing Windows 1.04, you can use [this guide](https://i12bretro.github.io/tutorials/0066.html), which specifies the configurations you should choose both in the VirtualBox interface and the OS install. 

Generally, I recommend you familiarize yourself with the capabilities and requirements (in addition to those of VirtualBox) of an OS before you attempt an install.

In the VirtualBox settings you can also configure the boot order and used boot devices, in addition to mounting both hard disks and removable devices prior to booting. 

#### Guest Additions 
VirtualBox provides a simple quality-of-life improvement in their Guest Additions .iso. Check out what guest-systems are supported [here](https://docs.oracle.com/en/virtualization/virtualbox/7.0/user/guestadditions.html#additions-windows).

In case the OS you've installed on your guest is not supported for Guest Additions, you can simply transfer files by creating an .iso file out of them and then mounting it in the virtual machine. This way, you can also provide third-party drivers (if available) to the guest that accomplish similar things to Guest Additions.

You can add and remove disks while the virtual machine is working as well, so it is not a lot slower than using a shared folder. Software for creating disk images is abundant and usually free, for example you can use Brasero or mkisofs.

