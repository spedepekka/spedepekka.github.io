---
layout: post
title: "Install Devuan 4 Chimaera to Raspberry Pi 3"
date: "2022-08-29 12:50:00 +0300"
permalink: /:title
---

## Prepare the SD-card

Get the image from [https://arm-files.devuan.org/](https://arm-files.devuan.org/)

I wrote it to SD-card with [Raspberry Pi Imager](https://downloads.raspberrypi.org/imager/) ([tutorial](https://howchoo.com/pi/raspberry-pi-imager)).

## Initial boot and setup

It is good idea to have keyboard and display connected to Pi to make the initial setup.

The default username and password are `root` and `toor`.

First change the password for `root` with command `passwd`

You can check it works by logging out with `exit` and logging in again with the given new password.

Here is Finland we have a different keyboard layout so it is good idea to run `run-setup` to set keyboard layout, timezone etc.

## Enable SSH access

I don't really want Pi to be connected to keyboard and display all the time and I'm going to use [Ansible](https://www.ansible.com/) to provision Pi eventually, so let's create a user for Ansible. Also root-login via SSH is not enabled by default.

```
adduser ansible
```

Give the password for ansible-user.

Devuan should be set up to run ssh by default, so now you should be able to connect to your Pi via SSH with ansible-user.

## Root-access to Ansible

Run `visudo` as root-user (I like vi more than nano, so I ran `EDITOR=vi visudo`)

Add line

```
ansible ALL=(ALL:ALL) ALL
```

under following line


```
root    ALL=(ALL:ALL) ALL
```

Just to make sure everything has been reloaded restart the Pi with

```
shutdown -r 0
```

Now your Pi is ready to be put in to dark closet for remote access :)

