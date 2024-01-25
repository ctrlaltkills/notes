"Do cool stuff with live-usbs
January 8, 2022
MX utilizes the antiX live system, which allows some pretty neat stuff, especially for enthusiast users.

Probably the biggest advantage of the live system is that you can run a persistent live-usb environment, so installed apps are available on the next boot of the live system. And if you do an install from a persistent live-usb setup, then all of those apps you added (or removed) will be available on the newly installed system.

Slightly more advanced but still pretty easy to do is to “remaster” those persistent systems, which compresses the original default file system and the changes in the persistent system together into a “new default” system, freeing up the allocated persistence storage to be reused.

Remastering is particularly useful after a kernel update, because if you remaster, then you can also change the kernel the live system will use at boot time with the live-usb-kernel-updater tool.

Even if you don’t run persistence, you can still remaster any changes made during a live-session, so that your “default” file system is always up to date.

There is even a rollback boot option if you need to “undo” a remaster.

If your usb device is writable, you can still save files to the writable areas of your live-usb in the $HOME/Live-usb-storage folder even without persistence being enabled.

I keep live-usbs of clean build environments for MX releases, just in case I need to drop back a release or two to do an update.

On top of all that live-usb goodness, you can even make a snapshot from a running live-usb, effectively turning your custom live-usb into an iso file for archiving, sharing, or whatever. They make great backup installation media.

And snapshot isos behave essentially the same as our default isos, and are install-able in the usual way.

Folks can share their snapshot creations in the MX forum in the MX Respins subforum. I recently posted a couple of examples, one being a 64 bit “bare” snapshot with pared down applications and and the other being a 32 bit snapshot that utilizes a 4.9 kernel (handy for some users of older machines with IDE devices). These were made via snapshot of running live-usb systems, so I never touched my production environment. adrian’s MX-Workbench was also originally built using the snapshot system."
 https://mxlinux.org/blog/do-cool-stuff-with-live-usbs/#:~:text=Do%20cool%20stuff,the%20snapshot%20system.