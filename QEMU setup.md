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

Note: If you are installing an operating system that uses multiple disks, you will need to install the first disk normally, by booting from the installation disk, and then any further disks by booting from the hard disk.

Look [here](https://wiki.qemu.org/Documentation/Platforms/PowerPC) as well, for additional info and examples on PPC emulation with different systems.
