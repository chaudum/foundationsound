---
title: "Broadcasting on Linux With Butt"
date: 2019-01-03T22:02:02+01:00
draft: true
author: Christian
tags:
  - linux
  - broadcasting
  - technology
---

On January 4, 2019 I will broadcast the radio show from my home studio, meaning
I need to stream the audio signal from the studio to the programme server that
handles the various audio sources and transmits the final signal to the radio
transmitters.

I've been using Mac hardware and software since more than a decade for all
sorts of graphic and sound design, however, lasta year I switched to Linux. The
reason for that was that Mac hardware is overpriced and never up to date and
the environment for software development has become worse. Additionally, I
haven't done any music or design recently.

However, now that I had to get a setup up and running again to be able to
produce the radio shows from the home studio, I had to find a solution for
Linux. Luckily, there is a cross-platform audio streaming client named
[BUTT](http://danielnoethen.de) (broadcast using this tool).

On Linux - Debian in my case - you have to build the binary from source and
there are quite a few
[requirements](http://danielnoethen.de/manual.html#_install). You can install
them with:

```
sudo apt install libopus-dev libmp3lame-dev libflac-dev portaudio19-dev libsamplerate0-dev libfdk-aac-dev libfltk1.3-dev libdbus-1-dev
```

Thereafter, it's simply extracting the tarball and perform *cmmi*:

```
tar xzf butt-0.1.17.tar.gz
cd butt-0.1.17/
./configure
make
sudo make install
```

Then you can run BUTT by executing `/usr/local/bin/butt`. Since the
installation does not generate a Desktop file (which is handy when using an
application launcher such as [rofi](https://github.com/DaveDavenport/rofi)) I
created it manually (`$HOME/.local/share/application/BUTT.desktop`).

```
[Desktop Entry]
Encoding=UTF-8
Categories=Music;Streaming;Audio;
Version=0.1.17
Type=Application
GenericName=Streaming Client
Exec=/usr/local/bin/butt
Name=butt
Comment=broadcast using this tool
```
