# remarkable2-hacks
A collection of hacks, mods, tools, tips &amp; tricks, specifically focused on the reMarkable 2

# TOC
- [remarkable2-hacks](#remarkable2-hacks)
    + [Disclaimer](#disclaimer)
  * [Introduction](#introduction)
    + [Why this?](#why-this)
    + [Hacks?](#hacks)
    + [Contribute / Support / Requests](#contribute--support--requests)
  * [Preliminary Steps](#preliminary-steps)
    + [USB network interface](#usb-network-interface)
    + [SSH into device](#ssh-into-device)
    + [Back it up](#back-it-up)
- [Hacks](#hacks)
  * [remarkable-hacks](#remarkable-hacks)
    + [What is it for?](#what-is-it-for)
    + [Setup](#setup)
    + [Compatibility](#compatibility)
  * [Toltec](#toltec)
    + [What is it for?](#what-is-it-for-1)
    + [Setup](#setup-1)
    + [Compatibility](#compatibility-1)
    + [Additional notes](#additional-notes)
  * [rm2fb](#rm2fb)
    + [What is it for?](#what-is-it-for-2)
    + [Setup](#setup-2)
    + [Compatibility](#compatibility-2)
  * [Oxide](#oxide)
    + [Setup](#setup-3)
    + [Compatibility](#compatibility-3)
  * [Genie](#genie)
    + [What is it for?](#what-is-it-for-3)
    + [Setup](#setup-4)
- [Credits](#credits)
- [References](#references)

### Disclaimer
While one of the goal of this repo is trying to give you things (and simple procedures) that has been proved to work on a RM2, all you will do is at your own risk and no warranty is given by anyone to anyone.  
Be aware, you could brick your device if you don't know what you are doing!

Also, for the moment, all of this is very experimental and still requires some more test to be confirmed as working on every device!
Everyone who is willing to test this and confirm is welcome :)

## Introduction
### Why this?
So you got your awsome reMarkable 2 because you heard that it could be "hacked", improved and customized... now what?  
Well, you can start here!

Most of the documentation, hacks and tools you can find online are still referred to the reMarkable 1 device and, unfortunately, not directly appliable to your reMarkable 2.  
So this repo has the goal to collect all the "hacks" and tools that can be used on a reMarkable 2, how to apply them and what to expect.  
Things are evolving rapidly on the subject, while the userbase grows. Many project are starting to support RM2 and many more will come.  
So this is an on-going project. I'll try to keep track of everything is going on for the RM2, but any collaboration is welcome!  

### Hacks?
First let me spend a few words on the term "hack" as it's being used here.  
Among the reMarkable community the term "hack" has been used to point to almost everything that is not writing on the device :)  
For many users opening an SSH terminal to the device and editing a file falls under this term. For a seasoned linux user, clearly, that's all but hacking.  

In one hand, the term "hack" in its wider (and original) sense of "using something in a different way than originally intended" is appropriate here, for a device that is being marketed as "just like a paper notebook".   
But we know that under that Eink screen sits a dual core 1.2GHz ARM CPU, with 1GB of RAM, running Linux... and... you can SSH into it by default!!! That's every hacker's dream!  

So, for the one of you that links the term "hack" to "illegaly gain access" or the like... no, none of these tools or techniques are actually "hacking" anything! Also, none of this illegal! But, be carefull, warranty could be invalidated modding the device.

The most adequate term for many of these customizations should be "mod", while often is simply "installing custom software on an open device"... but, it's somehow significant that the way this kind of device are normally "jailed" by manufacturers make us think that installing a software is actually hacking it :)

### Contribute / Support / Requests
Please use Discussions for any feedback: https://github.com/danielebruneo/remarkable2-hacks/discussions

## Preliminary Steps
First of all let me say that, while I try to make things simple for everyone, a general computer knowledge and some specific Linux shell confidence are required to go forward.  
A part from that, you will need the following steps:

### USB network interface
To enter something, you need a door. And the best one to do this sort of things is the virtual network interface that is provided over USB.  
If you plug the USB-C cable into your PC, indeed, a part from recharging your device, a new virtual ethernet interface will be created, ready to estabilish a connection to the device.

The RM2 will be available at `10.11.99.1`

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

### Back it up
Please make sure you have fully synced your device and possibly done a backup of your work by other means before doing any changes to the software.

# Hacks
## remarkable-hacks
https://github.com/ddvk/remarkable-hacks

The first and most valuable improvement you should give a try is the remarkable-hacks by ddvk.

The term hack is quite fitting here. This is, indeed, a binary patch that is being applied upon the original UI (xochitl) binary file.  

### What is it for?
This patch adds a lot of improvements to the RM2, things that, once you've tried, you'll think they should have been there since the beginning.
The list includes:
- ability to select many different sizes for every writing/drawing tool
- two additional customized tool (pen/pencil)
- pinch to zoom
- a focus mode, called "zen mode"
- bookmarks
- clock and battery indicator in the notebook sidebar
- other useful gestures (for eraser, most recent document, undo, etc.)

### Setup
The installation is pretty simple:
- SSH into device (see above)
- copy-paste this command  
`sh -c "$(wget https://raw.githubusercontent.com/ddvk/remarkable-hacks/master/patch.sh -O-)" `  
end press ENTER
- the modded UI will be launched
- once you've tried that, you press CTRL+C to stop it and go back to normal
- if you want to make it permanent, you will be instructed to type Y at the end of the process and the patch will be made persistent

The patch is pretty safe and it makes copies of the file it changes.  
So... you can roll it back if anything goes wrong or if you stop liking it https://github.com/ddvk/remarkable-hacks#revert-in-case-things-go-terribly-wrong

Follow the instructions on the original repo for more info: https://github.com/ddvk/remarkable-hacks.

### Compatibility
Also if it was born for the RM1, the hack has been ported succesfull to RM2 since a while, it runs smoothly and automatically detects which kind of device you have during the setup.

## Toltec
https://github.com/toltec-dev/toltec

Toltec is a community-maintained repository of free software for the reMarkable tablet. 

This project too was intended for the reMarkable 1 and still does not have a specific channel targeted to RM2, but many packages inthere are starting to run on RM2 as well. Many of them accomplish this thanks to the *rm2fb* tool, a "compatibility layer" that allows the RM2 framebuffer (that is slightly different from its predecessor) to be threated like the RM1 one.

### What is it for?
Once you setup Toltec, you'll basically have a package manager (opkg) at your hand and a bounch of software (https://toltec-dev.org/stable/) available for being installed with `opkg install <packagename>`.

### Setup
Setup is pretty easy here too.
You run the following commands (please refer to https://github.com/toltec-dev/toltec#install-it for up-to-date instructions) :
```
wget http://toltec-dev.org/bootstrap
echo "46f556b06f5624b48e974ae040b6213828eff6aa2cc78618a4d8961a27cdc8b3  bootstrap" | sha256sum -c
bash bootstrap
```
and the setup will start.

Please notice that:
- you may need (depending on your firmware) to replace the first line with `wget -k http://toltec-dev.org/bootstrap` bypassing wget SSL checks.
- the second line performs a check against the actual installer content, so it will vary when a new version is released, so refer to the toltec repo for the latest version

### Compatibility
While not every package there has been tested for RM2 compatibility, many should work, once you setup rm2fb.

### Additional notes
If you want to use the *testing* branch, with the latest beta features, follow this instructions:
- `nano /opt/etc/opkg.conf`
- edit the last line to read `src/gz toltec https://toltec-dev.org/testing` rather than `src/gz toltec https://toltec-dev.org/stable`
- run `opkg update`

Now you are using the testing branch. Be aware, things sitting there are not confirmed to be stable yet!

## rm2fb
https://github.com/ddvk/remarkable2-framebuffer

As previously said, this is a sort of compatibility interface to allow application intended to run on RM1 to be run smoothly on a RM2.  
The major software difference between the two is, indeed, the framebuffer to interact with the screen, that has changed significantly with the new screen.

### What is it for?
This software sits in the middle and lets older app interact with it like it was an RM1 framebuffer.

### Setup
If you have installed Toltec (if you don't, go above and do it), installing rm2fb is as simple as `opkg install rm2fb`.

### Compatibility
This is specifically for RM2 and does what it promises. Majority of the RM1 apps will be able to work with this installed.  
This does not mean that all of them will work well, though.  
Here's a list of tested apps: https://github.com/ddvk/remarkable2-framebuffer/issues/14.

## Oxide
Once you have the ability to install new software, you will need a way to launch those (and go back to main screen), a part from manually launch it from an ssh session.  
That's what a Launcher does. And Oxide is one of those (among with draft, remux, etc).

### Setup
Through Toltec you can simply do `opkg install oxide`.  
Once the setup is complete you will be instructed to do the following if you want oxide to be your default launcher:
- `systemctl disable --now xochitl`
- `systemctl enable --now tarnish`

If you want to revert it back, just do:
- `systemctl disable --now tarnish`
- `systemctl enable --now xochitl`

### Compatibility
BETA!!!

The RM2 support on Oxide is still being properly implemented and it's still on a "beta" phase. But it kinda works.  
Some bug has to be expected!!!  
(Please see below!)

One of the main thing to solve is that Oxide was thought to work together with the physical buttons the RM1 had, while the RM2 has none.  
For instance, without the buttons, once you launch an app, you won't be able to go back to the launcher if the app has no exit button.  
To help us handling that, Genie comes to the resque (see below). We'll set a gesture (two fingers tapping) for that!

### Bugs
The main known bug is that the device come back from standby with a blank screen.  
This happens specifically if you do not set a PIN for the lockscreen when instructed.
https://github.com/Eeems/oxide/issues/142

If you get a blank screen awakening RM2, tap with two fingers and, thanks to genie, you'll be back to Oxide.  
If you want to work around that, for the time being, you'll need to setup a PIN.

If you already went through the setup and did not selected a PIN, you can do it now running the following:
```
systemctl stop tarnish
rm /home/root/.config/Eeems/decay.conf
systemctl start tarnish
```

## Genie
https://github.com/rmkit-dev/rmkit/tree/master/src/genie

Genie is a config based gesture launcher.

### What is it for?
It allow you to execute commands when a gesture is performed.
The main reason we are going to use it is, in combination with our Oxide Launcher, to handle the "Back to the launcher" action.

### Setup
- With Toltec installed, run `opkg install genie`.
- edit the config file with `nano /opt/etc/genie.conf`
- copy-paste the following
```
gesture=tap
fingers=2
command=/opt/bin/rot apps call previousApplication
duration=1
```
- save
- restart genie with `systemctl restart genie`
- now if you tap with two fingers for more than a second, you'll go back to the launcher

# Credits
This repo is freely inspired by https://github.com/reHackable/awesome-reMarkable, awsome collection, but not specifically focused on RM2.
A big thanks also goes to the amazing work of ddvk at https://github.com/ddvk/remarkable-hacks.

# References 
- https://github.com/reHackable/awesome-reMarkable
- https://github.com/ddvk/remarkable-hacks
- https://github.com/ddvk/remarkable2-framebuffer
- https://github.com/rmkit-dev/rmkit
- https://github.com/toltec-dev/toltec
- https://github.com/Eeems/oxide
- https://remarkablewiki.com/
