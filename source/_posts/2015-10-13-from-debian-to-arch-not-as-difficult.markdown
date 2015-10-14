---
layout: post
title: "From Debian to Arch: not as difficult, nor simple either"
date: 2015-10-13 20:40:20 +0200
comments: true
categories: 
---

Recently I've changed my laptop main distro from Debian to Manjaro (an Arch-based distribution). Does it mean that the Carmina Burana's "Oh Fortuna" plays while apt-get falls into the depths of Oblivion? Well, technically yes. I mean, I can listen "Oh Fortuna" or any other piece of music while any linux distribution is being installed. And trully, pacman is NOT apt tools (It doesn't mean better or worse, just means they are different). But in the meantime I get used to this new approach and enjoy the views of KDE Plasma 5, I needed some help to the transition.

That's why I made some small utilities. And uploaded them to my Github. Until the time, there are only two small scripts (one made with python, the another with bash) who simplifies the mental transition between distros.

The first one, **service**, is just a simple translation to systemctl (I know, it's not only related to Arch but any systemd distro. But I haven't changed yet completely my way for calling start|stop|restart services). **Apt.py**, as its name suggests, is an apt-to-pacman translation with many, MANY lacks of functionality, but still usable on daily work.

I will explain with an example: I haven't uploaded the system for a while right now, so I want to perform 'apt-get update' to receive the new packages list and 'apt-get upgrade' to upgrade them. Well, with apt.py (installed by setup.sh), I can handle it easily:

<code>~$ sudo apt-get update</code>
<pre>
pacman -Sy
core is updated
extra is updated
community is updated
multilib is updated
</pre>

Or force the package update, even if it says the zips are updated:

<code> sudo apt-get update --force </code>
<pre>
pacman -Syy
:: Sincronizando las bases de datos de los paquetes...
 core                          134,6 KiB   302K/s 00:00 [############################] 100%
 extra                        1937,6 KiB   451K/s 00:04 [############################] 100%
 community                       3,1 MiB   263K/s 00:12 [############################] 100%
 multilib                      171,7 KiB   695K/s 00:00 [############################] 100%
</pre>

Note the <code>pacman -Sy</code> the program prints. It's because my translator doesn't want to be a substitute of pacman, but a simpler way to understand it through the apt approaching.

Hope it helps. Suggestions, as always, are welcome :D
