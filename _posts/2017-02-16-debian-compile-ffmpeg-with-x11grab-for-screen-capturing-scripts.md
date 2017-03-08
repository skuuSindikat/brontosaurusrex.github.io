---
published: true
layout: post
date: '2017-02-16 17:24 +0100'
title: 'Debian, compile ffmpeg with x11grab for screen-capturing scripts'
---
Leave the system version alone, leave the ~/bin version there as well, this compiled one is only ever used for screen capturing

    cd ~/source/ffmpeg && git pull # assuming ffmpeg git is cloned there
    ./configure --enable-gpl --enable-libx264 --enable-x11grab --enable-nonfree --enable-version3
    make
    
That's it, now just call it directly from screencapturing scripts like 

    pathtoffmpeg="$HOME/source/ffmpeg"
    "$pathtoffmpeg/"ffmpeg ...
