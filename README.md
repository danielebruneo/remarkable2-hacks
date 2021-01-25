# remarkable2-hacks
A collection of hacks, mods, tools, tips &amp; tricks, specifically focused on the Remarkable 2

## Introduction
### Why this?
So you got your awsome Remarkable 2 because you heard that it could be "hacked", improved and customized... now what?  
Well, you can start here!

Most of the documentation, hacks and tools you can find online are still referred to the Remarkable 1 device and, unfortunately, not directly appliable to your Remarkable 2.  
So this repo has the goal to collect all the "hacks" and tools that can be used on a Remarkable 2, how to apply them and what to expect.  
Things are evolving rapidly on the subject, while the user base grows. Many project are starting to support RM2 and many more will come.  
So this is an on-going project. I'll try to keep track of everything is going on for the RM2, but any collaboration is welcome!  

### Hacks?
First let me spend a few words on the term "hack" as it's being used here.  
Among the Remarkable community the term "hack" has been used to point to almost everything that is not writing on the device :)  
For many users open an SSH terminal to the device and edit a file follow under this term. For a seasoned linux user, clearly, that's all but hacking.  
In one hand, the term "hack" in its wider (and original) sense of "using something in a different way than intended" is appropriate here, for a device that is being marketed as "just like a paper notebook".   
But we know that under that eink screen sits a dual core 1.2GHz ARM CPU, with 1GB of RAM, running Linux... and... you can SSH into it by default!!! That's every hacker's dream!  

So, for the one of you that links the term "hack" to "illegaly gain access" or the like... no, none of this tools or technique are actually "hacking" anything!

The most adequate term for many of these customizations should be "mod", while often is simply "installing custom software on an open device"... but, it's somewhat significant that the way this kind of device are normally "jailed" by manufacturers make us think that installing a software is actually hacking it :)

### Disclaimer
While one of the goal of this repo is try to give you things (and simple procedures) that has been proved to work on a RM2, all you will do is at your own risk and no warranty is given by anyone to anyone. Be aware, you could brick your device if you don't know what you are doing!

## Preliminary Steps
### USB network interface
To enter something, we need a door. And the best one to do this sort of things is the virtual network interface that is provided over USB.  
If you plug the USB-C cable into your PC, indeed, a part from recharging your device, a new virtual ethernet interface will be created, ready to estabilish a connection to the device.

The RM2 will be available at 10.11.99.1

### SSH into device
The first thing you should do then, is SSH into the device.  
To do this, first you need to know how to SSH. Have a look here if you don't: http://letmegooglethat.com/?q=how+to+ssh+from+windows+linux+mac

Second, you'll need the IP address of your RM2.  
While you can SSH into the RM2 through the WiFi connection (and the IP address it gets from there), this is not adviced because the connection could go down during some of the steps that are required to apply those changes.  
Use the USB interface instead: the RM2 will be at 10.11.99.1 as per above.

Third, you'll need the SSH password.  
This is found on your RM2, going into Menu->Settings->Help->Copyright and licences.  
At the end of this page you will find all the IP addresses of your device and the SSH password you'll need.  
Store it in a safe location (not your RM2)! If you should be in the situation in which the standard UI won't lunch, that could save you from fully bricking your device.

# Hacks
## remarkable-hacks
The first and most valuable improvement you should give a try is the remarkable-hacks by ddvk https://github.com/ddvk/remarkable-hacks.

The term hack here is quite correct, this is, indeed, a binary patch that is being applied upon the original UI binary file.  
This patch adds a lot of improvements to the RM2, things that youonce you've tried you'll think they should have been there since the beginning, to start with.
The list includes:
- ability to select many different sizes for every writing/drawing tool
- two additional customized pen/pencil
- pinch to zoom
- a focus mode, called "zen mode"
- bookmarks
- clock and battery indicator in the notebook sidebar
- other useful gestures (for eraser, most recent document, undo, etc.)

The installation is pretty simple:
- you SSH into device (see above)
- you copy-paste this command `sh -c "$(wget https://raw.githubusercontent.com/ddvk/remarkable-hacks/master/patch.sh -O-)" ` end press ENTER
- the modded UI will be launched
- once you've tried that, you press CTRL+C to stop it and go back to normal
- if you want to make it permanent you will be instructed to type Y and the patch will be made persistent

The patch is pretty safe and it makes copies of the file it changes.  
So... you can roll it back if anything goes wrong or if you stop liking it https://github.com/ddvk/remarkable-hacks#revert-in-case-things-go-terribly-wrong

Follow the instruction on the original repo for more info: https://github.com/ddvk/remarkable-hacks.

## (TODO) toltec
## (TODO) rm2fb
## (TODO) Oxide
## (TODO) Genie

# Credits
This repo is freely inspired by https://github.com/reHackable/awesome-reMarkable, awsome collection, but not specifically focused on RM2.
A big thanks also goes to the amazing work of ddvk at https://github.com/ddvk/remarkable-hacks.

# References 
- https://github.com/reHackable/awesome-reMarkable
- https://github.com/ddvk/remarkable-hacks
- https://github.com/rmkit-dev/rmkit
- https://github.com/toltec-dev/toltec
