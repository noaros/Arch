# I use Arch btw
Ok this one is a bit silly, and not even a code project (yet), but I might as well use the repo README as a personal blog entry to log some notes about my switch to Linux / Arch.

At first I had a need to take Yocto for a spin, which requires Linux. Those plans have been postponed, but I still intend to specialize in all things Linux, so it seems hypocritical to keep using Windows as my daily driver, lol.

Being a minimalist, of course I'm drawn to Arch (again). It is supposed to be easy to install now, I think. Yet I hit more than a few obstacles as I added it to my new laptop. Still that is how you learn..

Since I still wanted to keep Windows as a security blanket, I opted to dual boot. I found some conflicting info regarding partitioning schemes but settled on using the Windows EFI partition also for Arch, mounting as /EFI, and separate partitions for /root and /home, as well as a shared data NTFS partition.

I was more interested in the manual install journey, but I flirted with the config script as well. Both paths failed at first, and the config script makes it a bit too easy and unclear as to when it is about to wipe out your preexisting Windows. The primary issue was getting rEFInd bootloader to work. That was my bootloader choice because the Windows EFI parition is small, and rEFInd supports loading the kernels from outside that partition, since it understands *ext4*. Alas my resulting install would not boot, failing to "switch root". The trick for me was running the rEFInd install script OUTSIDE of the *chroot* environment with /mnt as parameter argument. This was confusing because the install wiki instructs you to run it from inside the chroot, while warning this might not work, yet not making the solution clear. Also I learned there are two different rEFInd config files, and I was at first giving attention to the wrong one. 

Once in the system, it becomes a matter of how little I need to add to it to get it to behave acceptably. I was a bit surprised *Chrome* wasn't readily available without wrinkles, but used that as an excuse to just use *Firefox* instead. Playing with window manager options is of course one of the most fun aspects of *Linux*. At first I tried to roll without one and  virtual consoles only, using *cage* to launch *Firefox*, but copy paste between the consoles and browser was too annoying to get working. So I opted to give *Sway* a try, and like it so far. Touchpad scroll direction was inverted, but fixed with a Sway configuration file. I had to enable "tap to click" in the *Sway* config, but that still didn't get the job done until I replace the generic touchpad entry with my specific device name.

Next problem was sound. That went relatively smooth on the 2nd attempt of installing a bunch of things. Though it does sound a bit fuzzy.. Yes I needed the nvidia graphics drivers to fix the muffled sound, as well as adjusting volume with *alsamixer*.

I noticed *vim* has an annoying default configuration that doesn't allow backspace across line boundaries, but easy enough to just use neovim / emacs / nano / etc.

As of now I don't even have an app launcher, and not sure I need one. A base Arch system + editor + graphics driver + sway seems a proper starting point for getting things done, but I'm sure I'll hit a few more rough spots at some point.
