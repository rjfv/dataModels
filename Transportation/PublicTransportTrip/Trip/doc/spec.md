# Trip

## Description

This entity model a particular trip model, including all properties which can be used to find the users favorite public transport trip and all data related to it. This data model is based on the the [General Transit Feed Specification (GTFS)](https://developers.google.com/transit/gtfs/) that defines a common format for public transportation schedules and associated geographic information.

## Data Model

- ```id```: Entity's unique identifier.

- ```weekdays```: The weekdays that this trip refers to. 
	- Attribute type: List of [Text](https://schema.org/Text)
	- Mandatory

- ```segments```: An a array of segments containing details(see list below) about each segment that completes the trip. Each trip can have one or more segments.
	- Attribute type: List 

    - ```id```: Entity's unique identifier.

    - ```name```: Name given to this trip segment.
        - Normative references: https://schema.org/name
        - Mandatory

    - ```headsign```: Text that identifies the trip's segment destination to passengers.
        - Atttribute type: [Text](https://schema.org/Text)
        - Optional

    - ```wheelchairAccessible```: Wheelchair accessibility information for the trip segment.
        - Attribute type: [Number](https://github.com/schema.org/Number)
        - Allowed values: 
            - ```0```: Indicates that there is no accessibility information for the trip.
            - ```1```: Indicates that the vehicle being used on this particular trip can accommodate at least one rider in a wheelchair.
            - ```2```: Indicates that no riders in wheelchairs can be accommodated on this trip.
        - Optional

    - ```bikesAllowed```: Bicycle accomodation information for this trip segment
        - Attribute type: [Number](https://github.com/schema.org/Number)
        - Allowed values:
            - ```0```: Indicates that there is no bike information for the trip.
            - ```1```: Indicates that the vehicle being used on this particular trip can accommodate at least one bicycle.
            - ```2```: Indicates that no bicycles are allowed on this trip.
        - Optional

    - ```agency```: Agency the trip segment belogs to.
        - Attribute type: Reference to a [Agency](https://github.com/ftcardoso/dataModels/blob/public_transportation_2/Transportation/PublicTransportTrip/Agency/doc/spec.md) entity.
        - Mandatory

    - ```route```: Route the trip segment belongs to.
        - Attribute type: Reference to a [Route](https://github.com/ftcardoso/dataModels/blob/public_transportation_2/Transportation/PublicTransportTrip/Route/doc/spec.md)
        - Mandatory

    - ```stop_departure```: Stop where the trip segment start.
        - Attribute type: Reference to a [Stop](https://github.com/ftcardoso/dataModels/blob/public_transportation_2/Transportation/PublicTransportTrip/Stop/doc/spec.md)
        - Mandatory

    - ```stop_arrival```: Stop where the trip segment finish.
        - Attribute type: Reference to a [Stop](https://github.com/ftcardoso/dataModels/blob/public_transportation_2/Transportation/PublicTransportTrip/Stop/doc/spec.md)
        - Optional

    - ```departure_timestamp```: Timestamp which captures when the user started the trip segment. This value can also appear as a FIWARE [TimeInstant](https://github.com/telefonicaid/iotagent-node-lib/blob/develop/README.md#TimeInstant)
        - Attribute type: [Datetime](http://schema.org/DateTime) or ```ISO8601``` (legacy).
        - Mandatory

    - ```arrival_timestamp```:	Timestamp which captures when the user finished the trip segment. This value can also appear as a FIWARE [TimeInstant](https://github.com/telefonicaid/iotagent-node-lib/blob/develop/README.md#TimeInstant)
        - Attribute type: [Datetime](http://schema.org/DateTime) or ```ISO8601``` (legacy).
        - Optional

## Example
```
{
	"id": "tripID",
    "weekdays": ["monday", "tuesday"],
    "segments": [
    	"segment1":{
        	"id": "segmentID",
            "name": "Tacubaya - La Valenciana por Eje 3 Sur",
            "agency":{
            	"id": "CC",
                "name": "Corredores Concesionados"
            },
            "route": {
            	"id": "routeID",
                "short_name": "SAUSA"
                "long_name": "Metro Tacubaya - La Valenciana"
                "type": 3
            },
            "stop_departure": {
            	"id": "stopID",
                "name": "M. Tacubaya",
                "location": [19.402325646816475,-99.18885111808775]
            },
            "stop_arrival": {
            	"id": "stopID",
                "name": "Estación Metro Puebla",
                "location": [19.40738533642689,-99.08250689506531]
            },
            "departure_timestamp": "2017-02-05T08:30:11.5Z",
            "arrival_timestamp":"2017-02-05T08:50:30.8Z"
        }
    ]
}
```