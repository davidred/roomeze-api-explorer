# Rules

## Get All Rules

```http
GET /api/rules HTTP/1.1
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
      "type": "rule",
      "attributes": {
        "name": "Female Only",
      }
    },
    {
      "id": "2",
      "type": "rule",
      "attributes": {
        "name": "No Cats",
      }
    }  
  ]
}
```

This endpoint retrieves all rules.

### HTTP Request

`GET https://roomeze.com/api/rules`

### Attributes

Attribute         | Type   | Description
----------------- | ------ | -----------
name              | String | The name of the rule
