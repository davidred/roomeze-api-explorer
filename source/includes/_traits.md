# Traits

## Get All Traits

```http
GET /api/traits HTTP/1.1
Accept: application/json
Host: roomeze.com
```
```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "data": [
    {
      "id": "1",
      "type": "trait",
      "attributes": {
        "name": "Foodie",
      }
    },
    {
      "id": "2",
      "type": "trait",
      "attributes": {
        "name": "Wine lover",
      }
    }  
  ]
}
```

This endpoint retrieves all traits.

### HTTP Request

`GET https://roomeze.com/api/traits`

### Attributes

Attribute         | Type   | Description
----------------- | ------ | -----------
name              | String | The name of the trait
