fuzzy-clock-german

This is a fork of bashfuzzyclock. It is an adaption to German. It is written in Bash. KDE offers a "umgangssprachliche Uhr" (fuzzy clock - clock in words), which Gnome does not have. But you can use Conky to produce the same effect. This Bash script also works with Conky, Tint2 (Linux/BSD) or GeekTool (Mac).

INSTALL:
========

In Linux, first download and unzip the compressed file. Then, in Terminal, use the following commands:

```
$ tar xf bash-fuzzy-clock.tar.gz
$ sudo install -v bash-fuzzy-clock.sh -m 0755 /usr/bin/bash-fuzzy-clock
```

Install the German translation:
Notice: Make sure you have 'LANGUAGE' set in .bashrc (and for Conky, .xinitrc) or 
/etc/locale.conf

```
$ sudo msgfmt de.po -o /usr/share/locale/de/LC_MESSAGES/bash-fuzzy-clock.mo
```

USE
===

In Terminal, just type:

```
$ bash-fuzzy-clock
--> zwanzig nach zehn
```

You can use the "m" option to display the general time of day:

```
$ bash-fuzzy-clock m
--> morgens 
```
On Linux I use it with conky to show it on my desktop:

You find an example (file: zeit.conf) of how to include and style the fuzzy clock in German. Note that in zeit.conf, you need to adjust the following lines:
**On which screen/monitor do you want to display the clock?**
At the beginning, adjust the following line:

xinerama_head = 2,

--> I use three screens, so here indicate the screen on which the clock should be displayed. IF you have only one screen, delete the line.

Under ---Placement
--> Adjust where you want to display the clock.

At the very end:
You may need to change the font or colors.

How to include the Fuzzy Clock in Conky?
In general, we use the following code to display the clock in conky:
${exec bash-fuzzy-clock}

If you download zeit.conf, you need to start it with conky:
In Terminal: 

```
conky -c ~/zeit.conf
```
RESULT:
<img src="https://github.com/gerald-drissner/fuzzy-clock-german/blob/master/example_umgangssprachliche_uhr.png">

On an Apple computer, you can use GeekTool to display the clock on your 
screen, using a Shell Geeklet: see 
<https://lifehacker.com/5834676/build-an-attractive-informative-mac-desktop-with-geektool>


WHAT IS A FUZZY CLOCK?
======================

Fuzzy clocks display a generalisation of the time in informal or natural 
language. They only give precise time on the hour and at five-minute intervals from the hour.
