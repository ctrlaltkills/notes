# How to install Kali Linux apps in Debian
Are you a [Debian Linux](https://www.addictivetips.com/ubuntu-linux-tips/how-to-install-debian-linux/) user who also loves network security and computer testing? If so, you’ll probably want to install some security tools onto your Debian Linux system. Of course, the best way to get that type of software installed is to install the [Kali Linux](https://www.addictivetips.com/ubuntu-linux-tips/install-the-latest-kali-linux/) software suite. Here’s how to do it.

![](https://www.addictivetips.com/app/uploads/2021/07/kali-install-tools-fs8.png)

Adding the Kali Linux software repository to Debian
---------------------------------------------------

The best way to install Kali Linux software to your Debian Linux PC is to add the Kali rolling repo to your system. The reason this is the best way is that Kali is very similar to Debian.

To add the Kali repo to your existing Debian Linux installation, open up a terminal window on the desktop. You can open up a terminal window on the Debian desktop with **Ctrl + Alt + T**on the keyboard or search for “Terminal” in the app menu.

Once the terminal window is open and ready to use, open up the `/etc/apt/sources.list` file in the Nano text editor. Keep in mind that you’ll have to do this with **sudo**, ensuring you have Sudo privileges set up on Debian before attempting this.

sudo nano -w /etc/apt/sources.list

Inside the sources file, add in the following line of code at the very bottom of the file.

![](https://www.addictivetips.com/app/uploads/2021/07/kali-repo-fs8.png)

`## Kali Linux Rolling Repo ##`

After adding the top line of code, you’ll need to add in this second line directly below it. This code is the Kali Linux software repo URL, and without it, no software will be installed. 

`deb http://http.kali.org/kali kali-rolling main contrib non-free`

With the repo added to your system, save the edits to Nano. You can save the modifications in the Nano text editor by pressing **Ctrl + O**on the keyboard. Then, exit the Nano text editor by pressing **Ctrl + X**on the keyboard.

Once everything is saved, you’ll have to import the Kali Linux GPG key. This GPG key is essential. Without it, software from Kali doesn’t work. The quickest way to import the key is to use the **add-apt-key –recover**command below.

sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys ED444FF07D8D0BF6

With the Kali Linux repo key added to your system, the next step is to run the **update**command to refresh Debian’s software sources. Using the command below, update.

sudo apt update

Following the update, you’ll likely see some software updates available for your Debian Linux system. You can choose to update with the **apt upgrade** command or ignore it for now. Upgrades aren’t necessary to use the software.

If you do choose to update, run the following command below. Keep in mind; this update may take a bit as there may be a lot to update your system. Additionally, Debian may attempt to install the Kali desktop in its entirety. 

sudo apt-get upgrade 

Installing Kali Linux software
------------------------------

Once the Kali Linux software repository is enabled on your system, you can install Kali Linux software onto your Debian system. To start the installation process, open up a terminal window on the Debian desktop. The terminal is the best way to install Kali apps.

Open up a terminal window, press **Ctrl + Alt + T**on the keyboard, or search for “Terminal” in the app menu and open it that way. When the terminal window is open, use the **apt install** command below to install the “kali-tools-top10” packages on Debian.

![](https://www.addictivetips.com/app/uploads/2021/07/kali-install-tools-fs8.png)

sudo apt install kali-tools-top10

When you enter the command above, Debian will ask you for your password. The reason it asks for your password is that the **sudo**command requires root access. Enter your password using your keyboard.

After entering your password, Debian will collect all the packages and any dependencies needed to make the software work. This process will take a couple of seconds. When done, you’ll be asked to press the **Y**button to confirm you wish to install the software.

Upon pressing the **Y**button on your keyboard, Debian will install the top 10 Kali Linux security tools onto your computer. The installation will not take long. When done, open up your app menu to access your newly installed Kali Linux tools.

### Installing other software from Kali Linux on Debian

Installing the top 10 Kali Linux applications on Debian should be enough for most users. However, if you have more specific needs, here’s how to install more software from the Kali repos.

First, open up a terminal window. Once it is open, use the **apt search**tool and type what you wish to search for. For example, to search for Zonemaster in the Kali repos, you’d do:

![](https://www.addictivetips.com/app/uploads/2021/07/kali-search-fs8.png)

apt search zonemaster

Look through the search result for the application you wish to install from the Kali repos. When you’ve found it, install the software using the **apt install**command below.

sudo apt install zonemaster-cli

Repeat this process to install any Kali Linux software you want on Debian.