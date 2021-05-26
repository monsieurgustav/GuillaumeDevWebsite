---
title: "Montblanc Interactive Tech Wall"
image: 'byzance-montblanc.jpg'
tags: ["Cinder", "OpenCV"]
categories: ["Brand"]
date: 2020-05-01
---

# An interactive wall

Customers are invited to try the Headphone MB01, the Augmented Paper and the Summit 2 watch and discover more about each. While the customer takes in hand the product, the screen triggers a dedicated movie then an interactive experience.

# Tech

The application is a C++ Windows app based on [Cinder](https://libcinder.org/).

* Object detection:

   An Intel® RealSense™ camera is used to detect when a product is missing. (taken by the user) Image progressing is done using [OpenCV](https://opencv.org/).

   The application comes with a simple calibration process to support the world wide distribution using different cases, products and bases. Calibration is managed by the shop employees.

* Display images, movies, buttons, animations.


Developped for [Byzance](https://byzance.world/portfolio/montblanc-interactive-tech-wall/).
