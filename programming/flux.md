---
description: >-
  Flux is InfluxData’s functional data scripting language designed for querying,
  analyzing, and acting on data.
---

# Flux

## Setup

I'm using InfluxDB to store timeseries data from my Home Assistant instance. I use Grafana to visualise this data and create graphs. These examples assume a similar setup is provided.

## Compare data now vs. a year ago

Generally when querying data from InfluxDB in Grafana it is easiest to use Influx as a datasource and query with InfluxQL. However InfluxQL has various drawbacks versus Flux. For example in this case we need to use the timeshift command which is not available in InfluxQL.

![A graph comparing the total amount of steps from now vs. a year ago](<../.gitbook/assets/Screenshot 2021-12-31 at 14.39.16.png>)

To create a graph that has two lines (data now vs. data a year ago) for the same metric we need two queries:

#### Data: a year ago

```
import "experimental"

startRange = experimental.subDuration(
  d: 365d,
  from: v.timeRangeStart,
)

endRange = experimental.subDuration(
  d: 365d,
  from: v.timeRangeStop,
)

from(bucket: "homeassistant/autogen")
  |> range(start: startRange, stop: endRange)
  |> filter(fn: (r) => r._measurement == "count" and r._field == "value" and r.entity_id == "step_count")
  |> cumulativeSum()
  |> timeShift(duration: 1y)
  |> set(key: "_field", value: "a year ago")
```

This first query selects data via the range now-365. However this alone would lead to data being selected that is outside of the view window that we're displaying. So we need to shift the dates back by one year. This is done with the timeShift command on line 17. This means a datapoint from 01.01.2020 is now shown as 01.01.2021.

#### Data: now

```
from(bucket: "homeassistant/autogen")
  |> range(start: v.timeRangeStart, stop: v.timeRangeStop)
  |> filter(fn: (r) => r._measurement == "count" and r._field == "value" and r.entity_id == "step_count")
  |> cumulativeSum()
  |> set(key: "_field", value: "now")
```

The second query is how you're normally selecting live data. No shifting is needed here. In order to show the correct display name we need to enter `${__field.name}` into the "display name" setting of the panel.

## Calculate single value from multiple metrics in Flux

I want to have a graph comparing the total amount of calories burned now vs. a year ago. However I only have two metrics: "basal calories burned" and "active energy". So in order to calculate the total calories I need to add these two metrics to calculate a sum. In order for this to work the timestamps of these two metrics need to be in sync, otherwise you may need to normalise them first. For me this is already the case because I store these values once a day.

```
from(bucket: "homeassistant/autogen")
  |> range(start: v.timeRangeStart, stop: v.timeRangeStop)
  |> filter(fn: (r) => r._measurement == "kJ" and r._field == "value")
  |> filter(fn: (r) => r.entity_id == "basal_energy_burned" or r.entity_id == "active_energy")
  |> pivot(rowKey:["_time"], columnKey: ["entity_id"], valueColumn: "_value")
  |> map(fn: (r) => ({ r with _value: (r.active_energy + r.basal_energy_burned)/4.18 }))
  |> drop(columns: ["basal_energy_burned", "active_energy"])
  |> cumulativeSum()
  |> set(key: "_field", value: "now")
```

First I filter both metrics (line 3) then I create a pivot table by the column key "entity id" (line 4). This gives me a table with the columns: timestamp, basal energy, active energy, value.&#x20;

In order to calculate the value we can use a mapping function (line 6). This leaves us with the two additional columns that we no longer need so we can drop them (line 7). If we don't drop them they'll show up on the graph as well.

If you want to compare this graph to the data from a year ago the same setup as in the chapter above can be used.
