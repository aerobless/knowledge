---
description: Test edit
---

# Initial page

test

```text
msg.payload = msg.payload.data.metrics.map(metric => {

    //e.g. measurement for 01.01.2020 of active_energy
    return metric.data.map(actualMeasurement =>
       ({
            measurement: metric.units, //kJ
            fields: {
                ...(actualMeasurement.qty && {value: actualMeasurement.qty}), //2500 default
                ...(actualMeasurement.Avg && {Avg: actualMeasurement.Avg}), //Heartrate special
                ...(actualMeasurement.Max && {Max: actualMeasurement.Max}), //Heartrate special
                ...(actualMeasurement.Min && {Min: actualMeasurement.Min}), //Heartrate special
                ...(actualMeasurement.inBed && {inBed: actualMeasurement.inBed}), //Bed special
                ...(actualMeasurement.asleep && {asleep: actualMeasurement.asleep}), //Bed special
                ...(actualMeasurement.heartRateVariation && { value: measurement.heartRateVariation.length }), //irregular heartrate special
            },
            tags:{
                entity_id: metric.name, //active_energy
                ...(actualMeasurement.sleepSource && {sleepSource: actualMeasurement.sleepSource}), //Bed special
                ...(actualMeasurement.inBedSource && {inBedSource: actualMeasurement.inBedSource}) //Bed special
            },
            timestamp: Date.parse(actualMeasurement.date) //2021-03-16 00:00:00 +0100
        }))
    })
    .flat() // we've created array for each metric consisting of array of measurements
    .filter(e => Object.keys(e.fields).length) // only return entries with fields

return msg;
```



{% tabs %}
{% tab title="First Tab" %}
test
{% endtab %}

{% tab title="Second Tab" %}
test
{% endtab %}
{% endtabs %}

{% embed url="https://www.youtube.com/watch?v=208gyh8L0Q0" %}

> dddddddd



* [ ] ddd
* [ ] ddd
* [ ] ddd



![test](.gitbook/assets/supervisor.png)

