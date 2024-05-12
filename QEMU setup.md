#### Installation of QEMU
This setup guide is written with PowerPC architecture emulation in mind. 
Before doing anything else, you will need the QEMU base-program, available [here](https://www.qemu.org/download/#source). 

You will also need a disk image with the (PowerPC-compatible) operating system you intend to install on your virtual machine.

Before proceeding, it is also recommended to take a look at the [official documentation](https://www.qemu.org/docs/master/system/introduction.html).

From here, if you are using either **Windows** or **MacOS**, then Emaculation has published a good guide for gettings things running, available [here](https://www.emaculation.com/doku.php/qemu).

Otherwise, Linux users can look [here](https://wiki.qemu.org/Hosts/Linux) for help before starting QEMU. 

Note: Mac OS X versions 10.0 and 10.1 basically will not work on Debian-based distributions.

#### Create a hard disk image
A hard disk image can easily be created with the following command:
```
qemu-img create <myimage.img> <mysize>
```
You can add an M suffix to give the size in megabytes and a G suffix for gigabytes.

Make sure you make your hard disk large enough to accomodate your operating system and additional software!

Additional information about creating images can be found [here](https://www.qemu.org/docs/master/system/images.html).

For the purposes of our PPC machine, you can use the following command to create a 2Gb disk with raw format:

```
qemu-img create -f raw <myimage.img> 2G 
```

#### Configure the machine
A bash script is not entierly necessary, but can help streamline the process of starting the virtual machine, if you intend to use it multiple times. 

The general template for starting up QEMU is:
```
qemu-system-x86_64 [machine opts] \
                [cpu opts] \
                [accelerator opts] \
                [device opts] \
                [backend opts] \
                [interface opts] \
                [boot opts]
```
Note: It is very important that the bash script points to the correct disk images. For this purpose you can for example, create a separate folder that houses the script and the disks.

For emulating a PPC machine, a bash script can look like this:

```
#!/bin/sh
#!/bin/bash
cd $(dirname $0)

qemu-system-ppc \
-L pc-bios \
-boot d \
-M mac99,via=pmu \
-m 512 \
-display gtk \
-drive file=<opsys.iso>,format=raw,media=cdrom \
-drive file=<myimage.img>,format=raw,media=disk
```

Note: If booting normally, the hard disk should always be the first boot option and the boot flag should be changed to "c".

Look [here](https://wiki.qemu.org/Documentation/Platforms/PowerPC) as well, for additional info and examples on PPC emulation with different systems.

#### Installation with multiple disks
If the OS you are installing requires the usage of multiple disks, you should install the first disk normally and then boot from the hard disk for further disks. Then you can use QEMU monitor to insert disks as needed. You can access QEMU monitor with the combination Crtl + Alt + 2. To toggle back to the graphical display, use Ctrl + Alt + 1. 

Read further [here](https://www.linux-kvm.org/page/Change_cdrom) on how to utilize QEMU monitor to change disks on the go. 

#### File-sharing between the host and guest
There are many different ways to share files between the host and guest machines, a lot of them (for Linux) are detailed [here](https://wiki.archlinux.org/title/QEMU#Sharing_data_between_host_and_guest). 

The most simplistic way is to burn your desired files onto a virtual disk (creating an iso file) and then mounting it in the virtual machine. There are a variety of applications that allow you to do this, for example Brasero.

#### Mouse lagging or clipping
You can try changing the display mode to use sdl and specifying the vga input. You can also set the resolution of your output to that of your host's resolution, and then launch it in full-screen. Putting it all together, we get:
```
-display sdl
-vga std
-g 1920x1080x32
-full-screen
```
#### Note for Mac OS X installs
The Mac OS X installer expects the hard disk to be partitioned. So, the installer will not
offer a partition selection to you. Before you can install the software successfully, you will need to start the Disk Utility from the Tools menu and partition the hard disk. Only then can you  proceed with the installation