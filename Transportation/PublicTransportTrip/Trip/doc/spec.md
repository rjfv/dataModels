# Trip

## Description

This entity model a particular trip model, including all properties which can be used to find the users favorite public transport trip and all data related to it. This data model is based on the the [General Transit Feed Specification (GTFS)](https://developers.google.com/transit/gtfs/) that defines a common format for public transportation schedules and associated geographic information.

## Data Model

- ```id```: Entity's unique identifier.

- ```weekdays```: The weekdays that this trip refers to. 
	- Attribute type: List of [Datetimes](http://schema.org/DateTime)
	- Mandatory

- ```segments```: The segments that represent the trip. Each trip can have one or more segments and each one can have differente characteristics.
	- Attribute type: List of [Segments](https://github.com/ftcardoso/dataModels/blob/public_transportation_2/Transportation/PublicTransportTrip/Segment/doc/spec.md)
	- Mandatory