### Migrating the Windows OS to another SSD

This summer I bought an 256GB SSD to upgrade from my previous 128 GB C drive partition. I wanted to transfer my Windows partition to the new SSD so I started looking for guides. In the beginning, I had a hard time finding good guides and software recommendations but later I was able to 'mix-and-match' steps from various forums and articles, and finally complete the os migration to the SSD.

I put together this guides to save others' time that will be spent in doing the same things that I did.

> Bonus: No SSD enclosure of any kind needed.

#### Tools needed:

1. Internet Connection - to download Macrium Reflect
2. a USB drive (>=4GB) - to create the Rescue USB

#### Steps:

* Download and Install [Macrium Reflect](https://www.macrium.com/reflectfree) Free Edition. Choose *Home use* during download.
* Run Macrium Reflect and in the Backup tab, choose the Backup Windows option
	* it will ask you to choose the Windows partition drive, do so
	* specify the location for storing the disk image file (if could be on your system or on an external drive)
	* wait for the cloning to be completed, the created image should be of extension `.mrimage`
* Use the Macrium Rescue Media Builder to create a Rescue USB
* Turn off the computer
* If the created image file is on an external drive, connect it. *(ignore if not)*
* Swap the SSDs
* Boot from the Rescue USB
	* In the image restore tab, browse and select the image file
	* choose the drive to write the image file to
	* [Optional] If the new SSD is larger in size, you can enlarge it now or you can do it later using `diskpart`
	* start the restore process and wait for it to complete
	* reboot

> It may happen that on reboot, the device drivers for the SSD are not loaded and therefore, the system fails to boot. In such a scenario, one fix is to boot the system in safe mode so that Windows is forced to load the drivers.
