# Amenities

## Get All Amenities

```http
GET /api/amenities HTTP/1.1
Accept: application/json
Host: roomeze.com
```
```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "data": [
    {
      "id": "26",
      "type": "amenity",
      "attributes": {
        "name": "Cats",
        "amenity_type": "Property",
        "pet_amenity": true,
        "utility_amenity": false
      }
    },
    {
      "id": "22",
      "type": "amenity",
      "attributes": {
        "name": "Washer/dryer",
        "amenity_type": "Property",
        "pet_amenity": false,
        "utility_amenity": false
      }
    },
    {
      "id": "29",
      "type": "amenity",
      "attributes": {
        "name": "Balcony",
        "amenity_type": "Room",
        "pet_amenity": false,
        "utility_amenity": false
      }
    }
  ]
}
```

This endpoint retrieves all amenities.

### HTTP Request

`GET https://roomeze.com/api/amenities`

### Attributes

Attribute         | Type    | Description
----------------- | ------- | -----------
name              | String  | The name of the amenity
amenity_type      | String  | The type of amenity. Options: (`Property`, `Room`, `Building`)
pet_amenity       | Boolean | Whether or not this is a pet-related amenity
utility_amenities | Boolean | Whether or not this is a utilities-related amenity
