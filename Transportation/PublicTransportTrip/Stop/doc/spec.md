# Stop

## Description

This entity model a particular a public transport stop model, including all properties which are commom to multiple trip instances belonging to such model. This data model is based on the the [General Transit Feed Specification (GTFS)](https://developers.google.com/transit/gtfs/) that defines a common format for public transportation schedules and associated geographic information.

## Data Model

- ```id```: Entity's unique identifier.

- ```code```: Number that uniquely identifies the stop for passengers.
	- Attribute type: [Text](https://schema.org/Text) 
	- Optional

- ```name```: Name given to this stop.
	- Normative references: https://schema.org/name
	- Mandatory

- ```description```: Description of this stop.
	- Attribute type: [Text](https://schema.org/Text) 
	- Optional
	
- ```location```: Stop location represented by a GeoJSON Point.
	- Attribute type: ``geo_json`` 
	- Normative References: https://tools.ietf.org/html/rfc7946
	- Mandatory

- ```location_type```: Identifies whether this stop represents a stop or station.
	- Attribute type: [Number](https://github.com/schema.org/Number)
	- Allowed values:
		- ```0```: Stop. A location where passengers board or disembark from a transit vehicle.
		- ```1```: Station. A physical structure or area that contains one or more stop.
    - Optional  

- ```wheelchairBoarding```: Wheelchair accessibility information for the stop.
	- Attribute type: [Number](https://github.com/schema.org/Number)
	- Allowed values: 
		- ```0```: Indicates that there is no accessibility information for the stop.
		- ```1```: Indicates that at least some vehicles at this stop can be boarded by a rider in a wheelchair.
		- ```2```: Wheelchair boarding is not possible at this stop.
	- Optional