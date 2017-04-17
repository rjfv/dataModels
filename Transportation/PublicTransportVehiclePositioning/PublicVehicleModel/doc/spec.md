# PublicVehicleModel

## Description
This entity model a particular public vehicle model, including all properties which are common to multiple instances belonging to such model.

## Data Model

- ```id```: Entity's unique identifier.

- ```name```: Name given to this vehicle model.
	- Normative references: https://schema.org/name 
	- Mandatory

- ```description```: Vehicle's model dedscription
	- Normative references: https://schema.org/description
	- Optional

- ```brandName```: Vehicle's brand name.
	- Attribute type: [Text](https://schema.org/Text)
	- See also: https://schema.org/brand
	- Mandatory

- ```modelName```: Vehicle's model name.
	- Attribute type: [Text](https://schema.org/Text)
	- See also: https://schema.org/model
	- Mandatory

- ```passengersTotal```: The total number of passenger that the vehicle can transport (including the driver).
	- Attribute type: [Number]()
	- Optional

- ```fuelType```: The type of fuel suitable for the engine or engines of the vehicle.
	- Normative references: https://schema.org/fuelType
	- Allowed values: (One of the followings)
		- ```gasoline```
		- ```petrol(unleaded)```
		- ```petrol(leaded)```
		- ```petrol```
		- ```diesel```
		- ```electric```
		- ```hydrogen```
		- ```lpg```
		- ```autogas```
		- ```cng```
		- ```biodiesel```
		- ```ethanol```
		- ```hybrid electric/petrol```
		- ```hybrid electric/diesel```
		- ```other```

- ```fuelConsumption```: The amount of fuel consumed for traveling a particular distance or temporal duration with the given vehicle (e.g. liters per 100 km).
	- Normative references: https://schema.org/fuelConsumption
	- Default unit: liters per 100 kilometer
	- Optional

- ```height```: Vehicle's height.
	- Normative references: https://schema.org/height
	- Optional

- ```width```: Vehicle's width.
	- Normative references: https://schema.org/width
	- Optional

- ```depth```: Vehicle's depth.
	- Normative references: https://schema.org/depth
	- Optional

- ```weight```: Vehicle's weight.
	- Normative references: https://schema.org/weight
	- Optional

- ```dateModified```: Last update timestamp of this entity.
	- Attribute type: [DateTime](https://schema.org/DateTime)
	- Optional

- ```dateCreated```: Creation timestamp of this entity.
	- Attribute type: [DateTime](https://schema.org/DateTime)
	- Optional

## Example

```
{
	"id": "publicVehicleModel001"
    "name": "vehicleName",
    "brandName": "vehicleBrandName",
    "modelName": "vehicleModelName",
    "passengersTotal": 65,
    "fuelType": "diesel"
    
}
```