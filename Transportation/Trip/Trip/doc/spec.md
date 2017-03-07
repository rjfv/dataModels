# Trip

## Description

This entity model a particular trip model, including all properties which can be used to find the users favorite public transport trip and all data related to it. This data model is based on the the [General Transit Feed Specification (GTFS)](https://developers.google.com/transit/gtfs/) that defines a common format for public transportation schedules and associated geographic information.

## Data Model

- ```id```: Entity's unique identifier.

- ```name```: Name given to this trip.
	- Normative references: https://schema.org/name
	- Mandatory

- ```headsign```: Text that identifies the trip's destination to passengers.
	- Atttribute type: [Text](https://schema.org/Text)
	- Optional

- ```wheelchairAccessible```: Wheelchair accessibility information for the trip.
	- Attribute type: [Number](https://github.com/schema.org/Number)
	- Allowed values: 
		- ```0```: Indicates that there is no accessibility information for the trip.
		- ```1```: Indicates that the vehicle being used on this particular trip can accommodate at least one rider in a wheelchair.
		- ```2```: Indicates that no riders in wheelchairs can be accommodated on this trip.
	- Optional

- ```bikesAllowed```: Bicycle accomodation information for this trip.
	- Attribute type: [Number](https://github.com/schema.org/Number)
	- Allowed values:
		- ```0```: Indicates that there is no bike information for the trip.
		- ```1```: Indicates that the vehicle being used on this particular trip can accommodate at least one bicycle.
		- ```2```: Indicates that no bicycles are allowed on this trip.
	- Optional

- ```agency```: Agency the trip belogs to.
	- Attribute type: Reference to a [Agency](https://github.com/ftcardoso/dataModels/blob/public_transportation/Transportation/Trip/Agency/doc/spec.md) entity.
	- Mandatory

- ```route```: Route the trip belongs to.
	- Attribute type: Reference to a [Route](https://github.com/ftcardoso/dataModels/blob/public_transportation/Transportation/Trip/Route/doc/spec.md)
	- Mandatory 

- ```stop_departure```: Stop where the trip start.
	- Attribute type: Reference to a [Stop](https://github.com/ftcardoso/dataModels/blob/public_transportation/Transportation/Trip/Stop/doc/spec.md)
	- Mandatory 

- ```stop_arrival```: Stop where the trip finish.
	- Attribute type: Reference to a [Stop](https://github.com/ftcardoso/dataModels/blob/public_transportation/Transportation/Trip/Stop/doc/spec.md)
	- Optional 

- ```departure_timestamp```: Timestamp which captures when the user started the trip. This value can also appear as a FIWARE [TimeInstant](https://github.com/telefonicaid/iotagent-node-lib/blob/develop/README.md#TimeInstant)
	- Attribute type: [Datetime](http://schema.org/DateTime) or ```ISO8601``` (legacy).
	- Mandatory 


- ```arrival_timestamp```:	Timestamp which captures when the user finished the trip. This value can also appear as a FIWARE [TimeInstant](https://github.com/telefonicaid/iotagent-node-lib/blob/develop/README.md#TimeInstant)
	- Attribute type: [Datetime](http://schema.org/DateTime) or ```ISO8601``` (legacy).
	- Optional 

- ```date```: Date which captures when the user used this trip.
	- Attribute type: [Date](https://schema.org/Date)
	- Mandatory 

    