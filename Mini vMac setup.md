#### Installing Mini vMac
There is a sufficient guide available at their own [homepage](https://www.gryphel.com/c/minivmac/start.html) that has the necessary information for Windows, Mac OS and Linux.

For the hardware emulation to work correctly we need a Macintosh Plus ROM Version 2 or Version 3. A dump of a variety of Mac ROMs is available [here](https://macintoshgarden.org/apps/macintosh-rom-archive). It is also under the supplementary Mac files in this repository (MacPlus.v3).

The Mini vMac guide also provides us with System 6.0.8 directly from Apple.

#### Installing additional software

You can follow the guide available [here](https://www.gryphel.com/c/minivmac/recipes/sys6util/index.html). 

This provides us with a way to use additional software on the emulated system.

A variety of additional software can be found [here](https://www.gryphel.com/c/sw/).

#### Compiling a personal variation
If you want to use Mini vMac with custom configurations, you will need to compile it yourself. You can also pay for the Mini vMac Variations Service. Currently, a free subscriber code (7084424_7730) is provided on their website, as they are not currently sold. 

As the Variations Service was free to use at the time of writing, I used the Advanced Variations Service, available [here](https://www.gryphel.com/c/minivmac/vara_srv.html).

Using custom configurations allows you to use a lot more features than the standard version of Mini vMac.

Note: "Full Screen Mode" is not just a simple full-screen but changes how to emulation works and does not behave well on Debian-based hosts.

#### Starting the VM with a disk inserted
You can have the virtual machine boot automatically into the operating system, by naming the bootable disk "disk1.dsk" (this also works with .dc42 files). Alternatively, you can start Mini vMac with the command line, like so: `./Mini\ vMac ./<mydisk.dsk>`.

Blank hard disk images for Mini vMac are available [here](https://www.gryphel.com/c/minivmac/extras/blanks/index.html). First two System versions use the Macintosh File System, from System 3 on the Hierarchical File System is used.

