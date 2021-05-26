---
title: "Mont Analogue by Philippe Parreno"
image: parreno-mont-analogue.png
tags: ["AWS"]
categories: ["Art"]
date: 2021-05-19
---

# A companion app

Mont Analogue by Philippe Parreno, a transcription in coloured light signals of René Daumal’s eponymous novel, is set up at the top of the Medicis column.

As an echo to his installation, Philippe Parreno proposes an application that reacts to each variation in colour in real time, hitching a sound to it.

Daumal’s original text, transformed first to colour code, comes back to us therefore in sound, as a shadowy trace of the book.

https://colonnemedicis.pinaultcollection.com/

# Tech

The app (website and mobile apps) displays the same colors as the installation. It also plays a sound, created specifically. The content is more than 2 hours long then it loops.

The full color script is packed with the code. The sound is split in 1mn chunks for faster loading time, with some overlap between chunks to avoid glitches during play.

The app is synchronized with the installation: one can open it near the installation in Paris and observe that the colors change at the same time. The sound is also synchronized with the colors.

To achieve synchronizaton:
- it starts synchronized, and
- it maintains synchronization during play.
   Synchronization must be maintained over time. In practice, several machines running the same code/media independantly will shift by several seconds after few hours.

It uses several components/technologies, like DMX, ArtNet, a common clock for the installation and the app, realtime messaging, adaptative audio play rate, etc.

In the end, the offset between the installation and the app is under 100ms, which is fine considering there are mostly Wireless connections involved.

The webservices are built with serverless [AWS](https://aws.amazon.com/) services (API Gateway + Lambda, IOT Core) defined by [Terraform](https://www.terraform.io/).
