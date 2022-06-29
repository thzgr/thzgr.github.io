---
title: 'How do I setup my Linux machine'
date: 2022-06-29
permalink: /posts/2022/06/setup-linux-machine/
tags:
  - linnux
  - setup
  - customization
  - popos
  - polybar
  - rofi
---

Setting up a machine
======
Usually I like to automate things that I know I'll be doing multiple times. Even though I haven't distro hopping for some time I've used to change my main Linux distro because of some hardware issues.

But right now I've been daily driving Pop!_OS for quite some time to make a custom installation script and avoid having problems since I'm stable with it.

Automating the machine setup will actually help with all the customization that you've done previously and do it automagically, install all software you'll need and add additional features that you are used to.

What do I use
======
Personally I have been using [Pop!_OS](https://pop.system76.com/) as I have mentioned before, tiling mode from Pop Shell, a single Gnome extension to [disable the top bar](https://extensions.gnome.org//extension/545/hide-top-bar/), [polybar](https://github.com/polybar/polybar) as a replacement because it's easy to customize and add custom modules, and [rofi](https://github.com/davatorium/rofi) for launcher and powermenu.

The only reason I have been using Pop!_OS is because of it's stability without losing recent-ish important updates mainly regarding the kernel, and I also do believe in how System76 (the company behind Pop!_OS) handle its development and how they are changing from being only an Ubuntu clone.

My [dotfiles](https://github.com/thzgr/dotfiles)
====== 
In the root directory I have two .conf files, auto-cpufreq which is extremely important when using a laptop mainly because it sets battery usage governor, min and max CPU frequency scaling and turbo boost for both when charging and when discharging (using the laptop battery).

The other .conf file is some parts to be added onto the .bashrc file and be initialized every time a terminal window is opened including aliases and run prompt shell script.

Another file is the shell script named `pop_os_runner.sh` which is the main file here. This shell script install any additional source repos for installing software like nala instead of apt, VSCodium, Github CLI and Docker + docker-compose. It also check whether it has Flatpak installed and adds flathub to it.

After that it starts installing many softwares that I use. Most of them are Flatpaks which I find it easier to maintain since I don't have to install add lots of source repos. If I can't install any software as a Flatpak I'll compile from source or use a `.deb`. Those who are not Flatpaks: Firefox, GH Cli, Docker (ofc), YT Music client, VSCodium (I had some issues with the Flatpak version), Micro and auto-cpufreq. Everything else is a Flatpak.

I'd recommend checking out the shell script and modify if you don't want some software or add others if needed.

The shell script also copy some config files for Micro, gr8sh prompter, polybar and rofi. It also downloads and set a different icon theme.

In the `.config` folder you'll find keybindings for Micro and VSCodium, config files for Micro, VSCodium polybar and rofi, and also all the configuration for the gr8sh prompter which is the way I customize my terminal prompt without leaving bash.  

Configure your own way. Don't copy as is, you'll thank me later
======
tl,dr: title

Don't copy all the files except for those that are (kinda) reproducible. Micro is the easiest one since it'll install some plugins for LSP and more. VSCodium will be fine as well since there not much of configuration, it is more of keybindings. gr8sh is fine as well because it has everything it needs for a customized bash prompt. Now polybar and rofi you'll need to change some configuration for those modules that demand ethernet card name, battery, etc.

Everything in the [dotfiles](https://github.com/thzgr/dotfiles) are built for what I need. Change it the way you'd like better, modify, create, search, learn.

Anyways, that's it folks!
