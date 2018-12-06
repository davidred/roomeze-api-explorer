# Showing Requests

## Create a Showing Request

```http
POST /api/properties/2/showing_requests HTTP/1.1
Accept: application/json
X-CSRF-Token: tOQ4mkzlsJJYX1CWoxvuNPOdeNJjZGOTJT0TgZBloGjjMRjb2IS0oknE0oi+eeWmxQNn4HtBkqAabvlEwynrFg==
X-Requested-With: XMLHttpRequest
Host: roomeze.com
```
```http
HTTP/1.1 201 Created
Content-Type: application/json
Location: properties/2/showing_requests/378

{
  "data": {
    "id": 378,
    "type": "showing_request",
    "attributes": {
      "created_at": "2017-02-04T20:52:27.259-05:00"
    },
    "relationships": {
      "user": {
        "data": {
          "id": "1",
          "type": "user"
        }
      },
      "property": {
        "data": {
          "id": 343,
          "type": "property"
        }
      }
    }
  },
  "included": [...]
}
```

This endpoint creates a showing request

### HTTP Request

`POST https://roomeze.com/api/properties/<ID>/showing_requests`

### URL Parameters

Parameter | Description
--------- | -----------
ID        | The ID of the property to request a showing for
