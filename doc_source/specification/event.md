## Event

The event dictionary contains the following keys:

**type**
:  The value is always "Feature" <i>(string; required)</i>.

**properties**
:  A dictionary with the following keys <i>(dictionary; required)</i>:

   **id**
   :  A unique event id <i>(string; required)</i>.

   **time**
   :  Event origin time in UTC ISO 8601 *extended* format (i.e., with 
      separators between the year, month, and day, and the hour, minutes,
      and seconds, and with a “T” between the date and time)<i>(string; 
      required)</i>.

   **magnitude**
   :   Earthquake magnitude <i>(float; required)</i>.

**geometry**
:  A dictionary with the following keys <i>(dictionary; required)</i>;

   **type**
   :  The value is always "Point" <i>(string; required)</i>.

   **coordinates**
   :  A list of three floats: longitude, latitude, and depth.


Including the "event" dictionary is not required, but if it is present then the 
above elements are required.

```{note} 
"depth" in the events geometry coordinates array conforms with the
GeoJSON standard (meters above WGS datum). This is different from
seismic metadata convention, which is kilometers positive downward.
```

The following example illustrates the "event" dictionary:

```{code-block} json
---
force: true
---
{
    ...
    "event": {
        "type": "Feature",
        "properties": {
            "id": "ci38457511",
            "time": "2019-07-06T03:19:53Z",
            "magnitude": 7.1
        },
        "geometry": {
            "type": "Point",
            "coordinates": [
                -117.599,
                35.77,
                8.0
            ]
        }
    }
}
```
