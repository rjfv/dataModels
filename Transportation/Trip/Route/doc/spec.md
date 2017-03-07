# Route

## Description

This entity model a particular a public transport route model, including all properties which are commom to multiple trip instances belonging to such model. This data model is based on the the [General Transit Feed Specification (GTFS)](https://developers.google.com/transit/gtfs/) that defines a common format for public transportation schedules and associated geographic information.

## Data Model

- ```id```: Entity's unique identifier.
- ```short_name```: Short name of a route, often a short and abstract identifier like "7", "34", or "Blue" that riders use to identify a route.
    - Normative References: https://schema.org/name
    - Mandatory 

- ```long_name```: Full name of a route, more descriptive than the ```route_short_name``` and often include the route's destination or stop
    - Normative References: https://schema.org/name
    - Mandatory 

- ```description```: Description about this route.
	- Attribute type: https://schema.org/Text
	- Optional 

- ```type```: Describes the type of transportation used on a route
	- Attribute type: [Number](https://github.com/schema.org/Number)
	- Allowed values:
		- ```0```: Tram, Streetcar, Light rail. Any light rail or street level system within a metropolitan area.
		- ```1```: Subway, Metro. Any underground rail system within a metropolitan area.
		- ```2```: Rail. Used for intercity or long-distance travel.
		- ```3```: Bus. Used for short- and long-distance bus routes.
		- ```4```: Ferry. Used for short- and long-distance boat service.
		- ```5```: Cable car. Used for street-level cable cars where the cable runs beneath the car.
		- ```6```: Gondola, Suspended cable car. Typically used for aerial cable cars where the car is suspended from the cable.
		- ```7```: Funicular. Any rail system designed for steep inclines.

	- Mandatory

- ```color```: Color that corresponds to the route. The color must be provided as a six-character hexadecimal number, for example, 00FFFF.
	- Attribute type: [Text](https://schema.org/Text)
	- Optional

- ```url```: The URL of a web page about that particular route
	- Normative references: https://schema.org/url
	- Optional