# Entity

## Description
This enity model a particular service alert entity model, including all properties which can be used to specify exactly which parts of the public transport network are affected by the alert. This data model is based on the [Realtime Transit Service Alerts](https://developers.google.com/transit/gtfs-realtime/guides/service-alerts) that defines a common format for public transportation service alerts.

## Data Model

- ```id```: Entity's unique indentifier.

- ```refAgency```: Spcecifies the agency that will be affected. This means that all the agency network will be affected.
	- Attribute type: Reference to a [Agency](https://github.com/ftcardoso/dataModels/blob/public_transportation_2/Transportation/PublicTransportTrip/Agency/doc/spec.md)
	- Mandatory

- ```refRoute```: Specifies the particular route that will be affected.
	- Attribute type: Reference to a [Route](https://github.com/ftcardoso/dataModels/blob/public_transportation_2/Transportation/PublicTransportTrip/Route/doc/spec.md)
	- Mandatory only if no other type of entity is defined

- ```route_type```: Specifies the type of route that will be affected. This means that all toutes of this type will be affectged.
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
	- Mandatory only if no other type of entity is defined

- ```refTrip```: Specifies the particular trip that will be affected
	- Attibute type: Reference to [Trip](https://github.com/ftcardoso/dataModels/blob/public_transportation_2/Transportation/PublicTransportTrip/Trip/doc/spec.md)
	- Mandatory only if no other type of entity is defined

- ```refStop```: Specifies the particular stop that will be affected
	- Attribute type: Reference to [Stop](https://github.com/ftcardoso/dataModels/blob/public_transportation_2/Transportation/PublicTransportTrip/Stop/doc/spec.md)
	- Mandatory only if no other type of entity is defined


## Example

```
{
    "id": "entityID0",
    "refAgency": "agencyID0",
    "refRoute": "routeID001"
}
```

