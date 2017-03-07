# Agency

## Description

This entity model a particular a public transport agency model, including all properties which are commom to multiple trip instances belonging to such model. This data model is based on the the [General Transit Feed Specification (GTFS)](https://developers.google.com/transit/gtfs/) that defines a common format for public transportation schedules and associated geographic information.

## Data Model
- ```id```: Entity's unique identifier.
- ```name```: Name given to this agency.
    - Normative References: https://schema.org/name
    - Mandatory 

- ```url```: URL which provides information about this agency.
    - Normative references: https://schema.org/url 
    - Optional 
    
- ```timezone```: Timezone where this agency belongs to.
    - Attribute type: [Text](https://schema.org/Text)
    - Optional