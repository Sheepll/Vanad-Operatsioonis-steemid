#### Installing MAME

MAME should be available in the package repositories of most Linux distributions. On Debian or Ubuntu:

```
sudo apt-get install mame
```
The Apple II driver is included in the package.

For macOS, more information is available on the [GitHub page](https://github.com/mamedev/mame). The [official documentation](https://docs.mamedev.org/initialsetup/compilingmame.html) details the compilation process.

For Windows, you can take look at [the official page](https://www.mamedev.org/release.html). 

#### Configuring MAME

MAME supports a lot of systems. To run the Apple II specifically, you have to specify...

```
mame apple2
```

MAME should complain that it can't find the Apple II ROM files. I can't tell you where to acquire them, but MAME tries to look for apple2.zip, a2diskiing.zip, d2fdc.zip and votrax.zip. If you have these files, you can specify their location with the -rompath argument:

```
mame apple2 -rompath </path/to/roms>
```

Now MAME should start up. The screen should fill with a bunch of @'s and various characters and then present you with a '*' prompt. Don't worry about the missing Apple ][ startup screen, we haven't installed an operating system yet.

The default configurations for Apple II and II Plus are:
16K Language Card in slot 0, Mockingboard in slot 4, Disk II controller and 2 drives in slot 6.

This means you can have up to 2 floppy disks entered at any given time: Slot 5 would usually have a 3.5" disk drive interface card and Slot 6 5.25" disk drive interface card. Apple II did not include any support for hard disks, so I like to have a DOS 3.3 floppy in at all times.

Look [here](https://wiki.mamedev.org/index.php/Driver:Apple_II#The_default_configurations) for more default configurations and information on other Apple II line of systems.


To use MAME's UI-mode while emulating, you need to use the UI-key. This is by default Scroll Lock/Forward Delete (Mac Desktop)/fn-Delete (Mac Laptop). If these keys are not available on your keyboard, you will need to remap them if you wish to use the UI-mode. Using the UI-mode may be necessary, if you need to switch between floppies.

The UI-mode key can be changed with the `-uimodekey` flag, as such:
```
mame ibm5150 -uimodekey DEL
```
which rebinds the UI-mode key to DEL instead of SCRLOCK

Look [here](https://docs.mamedev.org/usingmame/defaultkeys.html#default-computer-keys) to see what options the MAME UI-mode offers.

#### Apple II emulation

Once you've completed the installation, the emulation itself is quite simple. MAME can easily be started from the command line. Since we are emulating the original Apple II, a command may look like this:

```
mame apple2 -rompath <path/to/roms> -flop1 <path/to/floppy> -uimodekey DEL
```

The original apple2 driver on MAME will **not** auto-boot floppy disks. Mount a floppy disk in the first slot by doing the following:
    1.Press 6 (or the number of the slot you are using)
    2.Press Control+P+Enter

Alternatively, you can type `Cx00G`, where x is the slot number. So to boot the 6th slot, you would enter `C600G` into the `*` prompt.



