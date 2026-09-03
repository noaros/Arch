# I use Arch btw
Ok this one is a bit silly, and not even a code project (yet), but I might as well use the repo README as a personal blog entry to log some notes about my switch to Linux / Arch.

At first I had a need to take Yocto for a spin, which requires Linux. Those plans have been postponed, but I still intend to specialize in all things Linux, so it seems hypocritical to keep using Windows as my daily driver, lol.

Being a minimalist, of course I'm drawn to Arch (again). It is supposed to be easy to install now, I think. Yet I hit more than a few obstacles. Still that is how you learn..

Since I still wanted to keep Windows as a security blanket, I opted to dual boot. I found some conflicting info regarding partitioning schemes but settled on using the Windows EFI partition also for Arch, mounting as /EFI, and separate partitions for /root and /home, as well as a shared data NTFS partition.

I was more interested in the manual install journey, but I flirted with the config script as well. Both paths failed at first, and the config script makes it a bit too easy and unclear as to when it is about to wipe out your preexisting Windows. The primary issue was getting rEFInd bootloader to work. My resulting install would not boot, failing to "switch root". The trick for me was running the rEFInd install script OUTSIDE of the chroot environment with /mnt as parameter argument. This was confusing because the install wiki instructs you to run it from inside the chroot, while warning this might not work, yet not making the solution clear. Also I learned there are two different rEFInd config files, and I was at first giving attention to the wrong one. 

