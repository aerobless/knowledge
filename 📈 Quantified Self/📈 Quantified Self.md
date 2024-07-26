---
description: >-
  Quantified self refers to self-tracking with technology in order to improve
  oneself and/or various aspects of life.
---
I use [InfluxDB](https://www.influxdata.com), a time series database in combination with [Grafana](http://grafana.com) and [Home Assistant](http://home-assistant.io) to track various personal metrics.

## Data that I'm tracking in InfluxDB:

* [Apple Health & Workout data exported via Home Assistant](https://sixtymeters.com/automations/exporting-apple-health-data-to-home-assistant/)
* Financial metrics, such as account balance and spending. This is exported via combination of parsing banking emails and manual data entry via a [Apple Shortcuts](https://apps.apple.com/us/app/shortcuts/id915249334) workflow.
* Home metrics, such as temperature in various rooms/outside, energy consumption & cost, weather

## Data that I'm tracking elsewhere:

* Location history via [Thereabout]
* Music I listen to via [Last.fm](https://www.last.fm)
* Books on Goodreads

# Notes

* [Exist.io](https://exist.io): I got started with the topic of quantified self via Exist.io. It aggregates the data of a variety of services (Apple Health, Todoist, RescueTime etc.) and determines correlation off that data. Sadly the devs got burned out from developing the product and are [currently looking to sell](https://forum.exist.io/t/would-you-like-to-own-exist/873). For that reason I've migrated my data to my own solution with InfluxDB, Grafana and Home Assistant.
* [Gyrosco.pe](https://gyrosco.pe): A service similar to Exist.io but more closed sourced. They're claiming to use AI to coach you and provide insights into your data. But from the brief time that I've used it I've found it to not be very helpful. And unlike Exist.io I doesn't have a public API that allows access to your own data. What I do like tho is that they offered to print a yearly book of your data which looked quite cool. Although the book is also fairly expensive so I've never done that.
