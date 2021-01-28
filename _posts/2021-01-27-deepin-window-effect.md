---
layout: post
title: "Deepin Window Effect Error"
author: "thenerdsuperuser"
tags: deepin-de ubuntu
---

I am enjoying my Deepin desktop environment, and I love the gestures but I suddenly started having issues with the Window Effect, especially the *Multitasking View*.


A window always popped up saying the following ->

> Kindly Remember: This application cannot run without window effect

And it was weird because it was working properly until yesterday. Also, I don't remember installing/updating any deepin-de packages; it just started suddenly.

Now, I started googling about it but to my no avail, I couldn't find any issue like that. Until, I knew what exactly was wrong; the Window Effect was not being enabled.

It all was due to a file called `kwinrc`, stored in the `~/.config` folder.

The contents were:

```bash
[Compositing]
OpenGLIsUnsafe=true

[Desktops]
Id_1=aed52c85-ca2b-4aa0-8d89-24d12e11e65b
Id_2=2c0089b3-acd9-431f-a37f-592e9f737457
Number=2

[Script-closewindowaction]
BorderActivate=

[Script-runcommandaction]
BorderActivate=

[deepin-chameleon]
theme=dark/deepin

[org.kde.kdecoration2]
library=com.deepin.chameleon
theme=
```

Anyway, all I had to do was delete the file and restart my laptop.

> Here is a link to the [Manjaro Forum post](https://forum.manjaro.org/t/deepin20-desktop-issue-with-window-effect/32162/4) which helped me fix it.
