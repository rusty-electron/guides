# installing virtual box on archlinux host machine

## installation
* install the `virtualbox` package via pacman
* We will also need to choose a package to provide host modules:
    * for the linux kernel, choose `virtualbox-host-modules-arch`
    * for any other kernel (including linux-lts), choose `virtualbox-host-dkms`

* reboot your system

virtualbox should now run.

> if virtualbox runs but after creating a virtual machine, it complains about missing kernel drivers. try to manually load the `vboxdrv` kernel module manually, using `modprobe vboxdrv`. If this module is not found in your kernel then I suggest you update your packages using pacman and it is quite possible that you have a new kernel update so once that is installed, reboot and the vm should now run.

## tips
* for auto-resizing of the vm window, install `virtualbox-guest-iso` package on the host and mount the iso at `/usr/lib/virtualbox/additions/VBoxGuestAdditions.iso`. The mounted drive contains installers for various OSes, install the one for your guest OS, reboot and it should work. You can now enable clipboard sharing and file drag and drop to guest/host desktop at *VM settings > General > Advanced*.

* in TWM, going fullscreen using keybindings like *mod+F* or *host+F* causes weird issues. This can be fixed by disabling `mini-bar` at *VM settings > User Interface*.
