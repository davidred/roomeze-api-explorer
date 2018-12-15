# Subway Lines

## Get All Subway Lines

```http
GET /api/lines HTTP/1.1
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
      "type": "line",
      "attributes": {
        "line": "Q",
        "image_url": "/assets/commuter_options/new_york/subway/Q.svg"
      }
    }
  ]
}
```

This endpoint retrieves all subway lines.

### HTTP Request

`GET https://roomeze.com/api/lines`

### Attributes

Attribute | Description
--------- | -----------
name      | The name of the subway line
image_url | The url of the subway icon (svg)
