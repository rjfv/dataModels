# Time Range

## Description
This enity model a particular service alert time range model, including all properties which can be used to specify exactly the time ranges affected by the alert. This data model is based on the [Realtime Transit Service Alerts](https://developers.google.com/transit/gtfs-realtime/guides/service-alerts) that defines a common format for public transportation service alerts.

## Data Model

- ```ìd```: Entity's unique identifier.

- ```startDate```: The specific date when the alert will start.
	- Attribute type: [DateTime](http://schema.org/DateTime)
	- Mandatory

- ```endDate```: The specific date when the alert will end.
	- Attribute type: [DateTime](http://schema.org/DateTime)
	- Mandatory

## Example

```
{
    "id": "timeRangeID0",
    "startDate": "2017-04-05T08:15:30+01:00",
    "endDate": "2017-04-05T10:15:30+01:00"
}
```