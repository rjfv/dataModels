# Public Vehicle

## Description

This entity model a particular public vehicle model, including all properties which can be used to find the vehicle position, the vehiclhe characteristics and the network characteristics that belongs too.

## Data Model

- ```id```: Entity's unique identifier.

- ```name```: Name given to this vehicle.
	- Normative references: https://schema.org/name
	- Optional

- ```description```:
	- Normative references: https://schema.org/description
	- Optional

- ```category```: Vehicle category(ies) from an external point of view.
	- Attribute type: List of [Text](https://schema.org/Text)
	- Allowed values:
		- public
		- private
		- municipalServices
		- specialUsage
	- Mandatory

- ```location```: Vehicle's last known location represented by a GeoJSON Point. Such point may contain the vehicle's altitude as the third component of the coordinates array.
	- Attribute type: ```geo:json```
	- Normative references: https://tools.ietf.org/html/rfc7946
	- Attribute metadata:
		- timestamp: Timestamp which captures when the vehicle was at that location. This value can also appear as a FIWARE [TimeInstant](https://github.com/telefonicaid/iotagent-node-lib/blob/develop/README.md#TimeInstant)
			- Type: [DateTime](http://schema.org/DateTime) or ```ISO8601``` (legacy)
			- Mandatory

- ```speed```: Denotes the magnitude of the horizontal component of the vehicle's current velocity and is specified in Kilometers per Hour. If provided, the value of the speed attribute must be a non-negative real number. null MAY be used if speed is transiently unknown for some reason.
	- Attribute type: [Number](https://schema.org/Number)
	- Default unit: Kilometers per hour
	- Attribute metadata:
		- timestamp: Timestamp which captures when the vehicle was at that speed. This value can also appear as a FIWARE [TimeInstant](https://github.com/telefonicaid/iotagent-node-lib/blob/develop/README.md#TimeInstant)
			- Type: [DateTime](http://schema.org/DateTime) or ISO8601 (legacy).
			- Mandatory
	- Mandatory

- ```heading```: Denotes the direction of travel of the vehicle and is specified in decimal degrees, where 0° ≤ heading < 360°, counting clockwise relative to the true north. If the vehicle is stationary (i.e. the value of the speed attribute is 0), then the value of the heading attribute must be equal to null. null MAY be used if heading is transiently unknown for some reason.
	- Attribute type: [Number](https://schema.org/Number)
	- Default unit: Kilometers per hour
	- Attribute metadata:
		- timestamp: Timestamp which captures when the vehicle was heading towards such direction. This value can also appear as a FIWARE [TimeInstant](https://github.com/telefonicaid/iotagent-node-lib/blob/develop/README.md#TimeInstant)
			- Type: [DateTime](http://schema.org/DateTime) or ISO8601 (legacy).
			- Mandatory
	- Mandatory


- ```serviceStatus```: Specify the vehicle status.
	- Allowed values:
		- ```parked```: Vehicle is parked and not providing any service at the moment.
		- ```onRoute```: Vehicle is performing a mission.
		- ```broken```: Vehicle is suffering a temporary breakdown.
		- ```outOfService```: Vehicle is on the road but not performing any mission, probably going to its parking area.
	- Attribute type: [Text](https://schema.org/Text)
	- Attribute metadata:
		- timestamp: Timestamp which reflects when the referred service status was captured.
			- Type: [DateTime](http://schema.org/DateTime)
			- Mandatory
	- Mandatory

- ```refPublicVehicleModel```: Public vehicle model.
	- Attribute type: Reference to a [PublicVehicleModel](https://github.com/ftcardoso/dataModels/blob/public_transportation_2/Transportation/PublicTransportVehiclePositioning/PublicVehicleModel/doc/spec.md) entity.
	- Optional

- ```refTrip```: Specify the trip that this vehicle is performing.
	- Attribute type: Reference to a [Trip](https://github.com/ftcardoso/dataModels/blob/public_transportation_2/Transportation/PublicTransportTrip/Trip/doc/spec.md) entity.
	- Mandatory

- ```dateModified```: Last update timestamp of this entity.
	- Attribute type: [DateTime](http://schema.org/DateTime)
	- Optional

- ```dateCreated```: Creation timestamp of this entity.
	- Attribute type: [DateTime](http://schema.org/DateTime)
	- Optional

## Example

```
{
	"id": "Vehicle0001",
    "category": ["municipalServices", "public"],
    "location": {
    	"type": geo:json,
        "coordinates": [-3.164485591715449, 40.62785133667262]
    },
    "speed": 50,
    "heading": 210,
    "serviceStatus": "onRoute",
    "refPublicVehicleModel": "publicVehicleModelID001",
    "refTrip": "tripID"
}
```