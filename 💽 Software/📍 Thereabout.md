---
aliases:
  - Thereabout
---
[Thereabout](https://github.com/aerobless/thereabout) is a self-hosted replacement for Google Location History that I’ve developed myself. It can be used to visualise your location history as a heatmap or a day-by-day view similar to what used to be Google Location History.

![[📍 Thereabout-20240726203438507.jpg]]

It’s also possible to import the existing Google Location History. New location data can be added directly via the REST API or by using the [Overland](Overland tracks your location and sends your data to a server of your choosing.) app. Overland is available for [[📱 iOS]] and Android.

Thereabout can be run via docker, either locally or on a server. The code & detailed installation instructions can be found on [GitHub](https://github.com/aerobless/thereabout).

# Development stack

Thereabout consists of a [[🍃 Spring Boot]] backend and a [[📐 Angular]] frontend. Data is stored in a Maria DB.