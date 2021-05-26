---
title: "Dailycious"
image: 'dailycious.jpg'
tags: ["Qt", "AWS"]
categories: ["Industry"]
date: 2021-05-17
bannerIsNarrow: true
---

# Brief

[Dailycious](https://dailycious.io/) is an application that allows you to play and review dailies on tablets. Thanks to the numerous onset generated metadata, it offers you infinite ways to sort and filter your media.
Dailycious can be set both on local and/or cloud-based server.

For me, it's one of the biggest project I developped alone. It's a 6-8 months job, spanned over the last 3 years. Today, the company's developers took over for the daily improvements, while I'm contracted on the architecture changes. I'm quite happy that the decisions I made early are still relevant today. There is a feeling of "it just works".

# Tech

The service is built with 3 elements: the manager, the players and webservices.

The manager is a Windows/OSX app built with [Qt](https://www.qt.io/) (C++, QML, Felgo). It is generally used on-set by the DIT and is the entry point for media and meta data.

The player is a Windows/OSX/Android/iOS app built with [Qt](https://www.qt.io/) (C++, QML, Felgo). It is used by the on-set team, producer, labs, etc. to receive media and meta data, create and share edited playlists.

Synchronization between the manager and players can be:
- cloud-based (built with [AWS](https://aws.amazon.com/) using [Terraform](https://www.terraform.io/)), and/or
- local if there is no Internet connection on set, or it is too slow to share GBs of data. The manager acts as the server on the local network.

The development is focused on several aspects:
- usability: QML is perfect to match the designed UX
- performance: the heavy lifting is done by C++ code, from sorting and filtering to persistency or synchronization.
- security: cloud-based sync is secured by regular means (HTTPS, 2FA) and local sync using [libsodium](https://github.com/jedisct1/libsodium).
