---
title:  "Homebrew QFH Antenna"
categories: electronics
tags: ham-radio wheather-satellites sattelite-reception
polarization-gallery:
  - url: https://upload.wikimedia.org/wikipedia/commons/9/99/EM-Wave.gif
    image_path: https://upload.wikimedia.org/wikipedia/commons/9/99/EM-Wave.gif
    alt: "Linear polarization"
    title: "Linear polarization"
  - url: https://upload.wikimedia.org/wikipedia/commons/d/d1/Circular.Polarization.Circularly.Polarized.Light_Left.Hand.Animation.305x190.255Colors.gif
    image_path: https://upload.wikimedia.org/wikipedia/commons/d/d1/Circular.Polarization.Circularly.Polarized.Light_Left.Hand.Animation.305x190.255Colors.gif
    alt: "Circular polarization"
    title: "Circular polarization"
results-gallery:
  - url: /assets/images/posts/qfh-antenna/meteor-1.png
    image_path: /assets/images/posts/qfh-antenna/meteor-1.png
    alt: "Meteor M2-3 Reception"
    title: "Meteor M2-3 Reception"
  - url: /assets/images/posts/qfh-antenna/meteor-2.png
    image_path: /assets/images/posts/qfh-antenna/meteor-2.png
    alt: "Meteor M2-3 Reception"
    title: "Meteor M2-3 Reception"
permalink: /qfh-antenna/
excerpt: "In 2018, I got my hands on an RTL-SDR and my ham-radio journey begun. Since I read a tutorial on weather satellite reception, I've wanted to try it out but lacked the equipment. This summer, I finally built a Quadrifilar Helix Antenna for the 137 MHz band. Here's how I did it..."
header:
  overlay_image: /assets/images/posts/qfh-antenna/head.jpg
  overlay_filter: 0.33
  teaser: /assets/images/teasers/qfh-teaser.png
---

In 2018, I stumbled upon an article about the [RTL-SDR](https://www.rtl-sdr.com/){:target="_blank"} dongle.
For the uninitiated, the RTL-SDR is a software defined radio receiver that uses a Realtek RTL2832U chipset.
An SDR is basically a radio communication system where components that have been traditionally implemented in hardware are instead implemented by means of software on a personal computer or embedded system.
I of course had to get my hands on one of these dongles and start playing with it.
My kit came with some basic dipole antennas that I used with RTL-SDR's tutorials to grab FM radio and ham-radio signals and get boat and aircraft tracking data.
This was essentially my first step into the hobby of [amateur radio](/categories/#ham-radio/).

# Weather Satellites

The next goal was satellite signal reception, but the dipole antennas were simply not getting the job done, even though people have been successful on using them in a certain configuration.
The "Hello World" of satellite reception is the NOAA weather satellites, namely the NOAA 15, 18, and 19.
These sats transmit APT (Automatic Picture Transmission), an analog image transmission system that transmits two channels of image data in the 137 MHz band.
They move in a sun-synchronous orbit, which means they pass over the (approximately...) same location at the same time every day (...approximately).

Another popular satellite is the Russian Meteor-M2.
It is a more modern satellite that transmits digital images in the 137 MHz band using a method called LRPT (Low-rate Picture Transmission).
The images are of higher resolution and quality than the NOAA satellites, but the downside is that the signal is more difficult to decode.
In all other aspects, the Meteor-M2 is similar to the NOAA satellites.

To track these satellites and find what time they will pass over your location you can use satellite tracking software such as [Orbitron](http://www.stoff.pl/){:target="_blank"} or [GPredict](https://oz9aec.dk/gpredict/){:target="_blank"}.
There is also an amazing website by [N2YO](https://www.n2yo.com/){:target="_blank"} that provides real-time tracking of satellites and has some info on the frequences they transmit on.
Meteor M2-3 and M2-4 satellites transmit on 137.9000 MHz but are known to change their frequencies, so you can check if the latest information is available [here](https://usradioguy.com/meteor-satellite/#status).
For the NOAA satellites, the frequencies are 137.6200 MHz for NOAA 15, 137.9125 MHz for NOAA 18, and 137.1000 MHz for NOAA 19.

# Quadrifilar Helix Antenna

The reason why many common antennas, like dipoles, are not suitable for satellite reception is that they are linearly polarized.
Polarization is the orientation of the electric field of the radio wave in 3D space.
In linear polarization, the electric and magnetic fields exist on static planes.
By aligning the receiving antenna with the transmitting antenna, the signal strength is maximized.
However, satellite signals are [circularly polarized](), which means that the electric field rotates in a circular pattern.
This means that special antennas are needed to receive these signals that are called circularly polarized antennas.
It is also important to note that the direction of the rotation can be either right-hand (RHCP) or left-hand (LHCP) circularly polarized.
NOAA and Meteor-M2 satellites transmit with RHCP polarization on the 137 MHz band.

{% include gallery id="polarization-gallery" layout="half" caption="Linear vs Circular polarization" %}

Most articles and tutorials about weather satellite reception recommend the Quadrifilar Helix Antenna (QFH).
It is not the easiest antenna to build, but supposedly it is very good for this kind of satellite reception and it can have a wide bandwidth which means that it is forgiving in terms of tuning.
The QFH consists of two loops that are wound in a helix around a central support.
The dimensions of the loops are critical and must be calculated based on the frequency of the satellite signal.
The direction of the helix is also important, as it determines if the antenna is right-hand or left-hand circularly polarized.

![QFH Antenna](https://www.dxzone.com/dx33863/how-to-build-a-quadrifilar-helix-antenna-for-weather-satellites.jpg)

# The Build

Unfortunately, I did not document the build process of my QFH antenna in detail.
The mast was made from a PVC pipe, and the antenna elements were made from soft copper pipe.
The dimensions of the loops were calculated using [this online calculator](https://jcoppens.com/ant/qfh/calc.en.php){:target="_blank"}.
I based my design on other people's work, and I used a combination of different designs to come up with my own.
I will not attempt to provide any blueprints here since I did not come up with the design myself, so do read the articles linked in the [Further Reading](#further-reading) section for more information.

## Antenna Elements & Mast

To begin with, I cut pieces of the copper pipe to the calculated lengths for the straight elements on the top and bottom of the loops.
I used a circular electrical box to secure the top elements and allow for the connection of the coaxial cable.
Waterproof electrical pass-throughs were used to secure the elements to the electrical box.
The ends of the top elements were cut in a 45° angle to allow for a better connection to the larger, bent parts of the loops.

![Top Elements](/assets/images/posts/qfh-antenna/1.jpg)

Slots were cut in the PVC pipe to allow for the insertion of the top elements.

![PVC Pipe](/assets/images/posts/qfh-antenna/2.jpg)


Similar pass-throughs were used to secure the bottom elements to the PVC pipe in the appropriate positions.
Attention should be paid on the 45° angle of the bottom elements, as they need to be in a 90° offset on the opposite side of each element.
This is also true for the top elements, but the two ends are separate there and can be rotated independently.

![Bottom Elements](/assets/images/posts/qfh-antenna/3.jpg)

The four large, bent elements were cut in appropriate lengths and bent to a semi-circle.
The ends were once again cut in a 45° angle to allow for a better connection to the top and bottom elements.
Plumbing solder and a blowtorch was used to make the connections with the bottom elements.
The large elements were then bent from a semi-circle to a helix around the PVC pipe to attach to the top elements and soldered in place.

## Coaxial Cable & Balun

A length of 50Ohm coaxial cable was soldered to the top elements according to the blueprints.

![Coaxial Connection](/assets/images/posts/qfh-antenna/5.jpg)
*Source: [A QFH design by K6KZO](https://wx.k6kzo.com/qfh.html){:target="_blank"}*

Right under the top elements, a hole was drilled in the PVC pipe to allow for the coaxial cable to pass through.
The coaxial was then looped 4 times around the PVC pipe to act as a balun.
Another hole was drilled below the balun to allow for the coax to go back inside the mast pip and exit at the bottom.

![Balun](/assets/images/posts/qfh-antenna/6.jpg)
*<br>Source: [A QFH design by ON7EQ](https://jcoppens.com/ant/qfh/adapt.en.php){:target="_blank"}*

## Mounting

To waterproof the antenna I used sealing silicone to fill the electrical box on the top and holes for the coaxial cable in the PVC pipe.
The mast was secured on the wall on my roof using pipe clamps.
Steel wire was attached at four points on the antenna, two on the top and two on the base of the antenna.
The wire was then attached on the roof and tightened to secure the antenna against the wind.

![Mounted Antenna](/assets/images/posts/qfh-antenna/4.jpg)

# Results

{% include gallery id="results-gallery" caption="Images received using my QFH antenna"%}

# Further Reading

- [RTL-SDR NOAA Reception Tutorial](https://www.rtl-sdr.com/rtl-sdr-tutorial-receiving-noaa-weather-satellite-images/){:target="_blank"}
- [RTL-SDR Meteor-M2 Reception Tutorial](https://www.rtl-sdr.com/meteor-m2-3-now-in-orbit-and-transmitting-weather-images/){:target="_blank"}
- [QFH Antenna Calculator](https://jcoppens.com/ant/qfh/calc.en.php){:target="_blank"}
- [A QFH design by F4BPP](https://f4bpp.com/en/qfh-antennas/){:target="_blank"}
- [A QFH design by G4ILO](https://www.g4ilo.com/qfh.html){:target="_blank"}
- [A QFH design by George Goodroe, KF4CPJ](https://www.qsl.net/kf4cpj/qha/){:target="_blank"}
- [A QFH design by Dr. Will Dillon](https://housedillon.com/blog/helical-quad-antenna-for-weather-satellites/){:target="_blank"}
- [A QFH design by K6KZO](https://wx.k6kzo.com/qfh.html){:target="_blank"}