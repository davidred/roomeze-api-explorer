# Cities

## Get All Cities

```http
GET /api/cities HTTP/1.1
Accept: application/json
Host: roomeze.com
```
```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "data": [
    {
      "id": "3",
      "type": "city",
      "attributes": {
        "name": "Queens",
        "short_name": "Queens",
        "short_description": null,
        "long_description": null
      },
      "relationships": {
        "subregion": {
          "data": {
            "id": "35",
            "type": "subregion"
          }
        },
        "neighborhoods": {
          "data": [
            {
              "id": "74",
              "type": "neighborhood"
            }
          ]
        }
      }
    }
  ]
}
```

This endpoint retrieves all cities.

### HTTP Request

`GET https://roomeze.com/api/cities`

### Attributes

Attribute         | Type   | Description
----------------- | ------ | -----------
name              | String | The name of the city
short_name        | String | The short name of the city
short_description | String | The short description of the city
long_description  | String | The full description of the city
