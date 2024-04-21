


OS Type: macOS 10.13 High Sierra (64-bit)
Base Memory: 4096 GB RAM
Disk Size: 32 GB disk size
Video RAM: 128 MB
2 CPUs
disable floppy
disable serial port
disable audio


    VBoxManage setextradata  {vm name or ID} "VBoxInternal/Devices/efi/0/Config/DmiSystemProduct" "iMac17,1"
    VBoxManage setextradata  {vm name or ID} "VBoxInternal/Devices/efi/0/Config/DmiSystemVersion" "1.0"
    VBoxManage setextradata  {vm name or ID} "VBoxInternal/Devices/efi/0/Config/DmiBoardProduct" "Iloveapple"
    VBoxManage setextradata  {vm name or ID} "VBoxInternal/Devices/smc/0/Config/DeviceKey" "ourhardworkbythesewordsguardedpleasedontsteal(c)AppleComputerInc"
    VBoxManage setextradata  {vm name or ID} "VBoxInternal/Devices/smc/0/Config/GetKeyFromRealSMC" 1


https://github.com/myspaghetti/macos-virtualbox

https://github.com/sadponyguerillaboy/Apple-Chunklist-Verification-Creation-Toolkit

https://github.com/notpeter/apple-installer-checksums?tab=readme-ov-file#mac-osx-installers-sha1-checksums

https://github.com/DrDonk/unlocker

https://github.com/paolo-projects/auto-unlocker

https://www.downtowndougbrown.com/2017/10/virtualizing-mac-os-x-10-4-with-vmware/