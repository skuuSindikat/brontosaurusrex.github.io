---
published: true
layout: post
date: '2017-07-18 10:04 +0200'
title: 'conky, nvidia utilization'
---
## nvidia infos

[https://github.com/brndnmtthws/conky/issues/329](https://github.com/brndnmtthws/conky/issues/329)

For many cards?

![](https://images.nvidia.com/pascal/img/gtx1060/GeForce_GTX_1060_Front.png)

from [conky man](http://conky.sourceforge.net/variables.html)

> Nvidia graficcard support for the XNVCtrl library. Each option can be shortened to the least significant part. Temperatures are printed as float, all other values as integer.

    threshold - The thresholdtemperature at which the gpu slows down
    temp - Gives the gpu current temperature
    ambient - Gives current air temperature near GPU case
    gpufreq - Gives the current gpu frequency
    memfreq - Gives the current mem frequency
    imagequality - Which imagequality should be chosen by OpenGL applications

Again, [for many cards](https://forums.bunsenlabs.org/viewtopic.php?pid=56255#p56255)?

Possible solutions:  
- including output of nvidia-settings (${execi nvidia-settings....) or [nvidia-smi](http://developer.download.nvidia.com/compute/DCGM/docs/nvidia-smi-367.38.pdf).

## nvidia overclocking on linux

untested

- nvidia-smi [https://devtalk.nvidia.com/default/topic/1011804/nvidia-smi-not-fully-supported-on-gtx-1060/](https://devtalk.nvidia.com/default/topic/1011804/nvidia-smi-not-fully-supported-on-gtx-1060/)
- coolbits?

## IP int, ext

    ${addr} < IP internal, ${exec curl -s www.icanhazip.com} < IP external