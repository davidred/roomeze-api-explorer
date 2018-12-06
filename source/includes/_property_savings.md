# Property Savings

## Save a Property

```http
POST /api/properties/2/save HTTP/1.1
Accept: application/json
X-CSRF-Token: tOQ4mkzlsJJYX1CWoxvuNPOdeNJjZGOTJT0TgZBloGjjMRjb2IS0oknE0oi+eeWmxQNn4HtBkqAabvlEwynrFg==
X-Requested-With: XMLHttpRequest
Host: roomeze.com
```
```http
HTTP/1.1 201 Created
Content-Type: application/json
Location: /api/properties/2

{
  "data": {
    "id": 2,
    "type": "property_saving",
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

This endpoint saves a property.

### HTTP Request

`POST https://roomeze.com/api/properties/<ID>/save`

### URL Parameters

Parameter | Description
--------- | -----------
ID        | The ID of the property to save

## Unsave a Property

```http
DELETE /api/properties/2/save HTTP/1.1
Accept: application/json
X-CSRF-Token: tOQ4mkzlsJJYX1CWoxvuNPOdeNJjZGOTJT0TgZBloGjjMRjb2IS0oknE0oi+eeWmxQNn4HtBkqAabvlEwynrFg==
X-Requested-With: XMLHttpRequest
Host: roomeze.com
```
```http
HTTP/1.1 204 No Content
Content-Type: application/json
Location: /api/properties/2
```

This endpoint unsaves a property.

### HTTP Request

`DELETE https://roomeze.com/api/properties/<ID>/unsave`

### URL Parameters

Parameter | Description
--------- | -----------
ID        | The ID of the property to unsave

## Get all Property Savings

```http
GET /api/users/2/property_savings HTTP/1.1
Accept: application/json
Host: roomeze.com
```
```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "data": [
    {
      "id": 2,
      "type": "property_saving",
      "attributes": {
        "created_at": "2017-02-04T20:52:27.259-05:00"
      },
      "relationships": {
        "user": {
          "data": {
            "id": "2",
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
    }
  ],
  "included": [
  ],
  "meta": {
    "page_info": {
      "total_pages": 5,
      "current_page": 1,
      "prev_page": null,
      "next_page": 2,
      "page_size": 25,
      "total_count": 115      
    }
  }
}
```

This endpoint gets a users saved properties.

### HTTP Request

`GET https://roomeze.com/api/users/<ID>/property_savings`

### URL Parameters

Parameter | Description
--------- | -----------
ID        | The ID of the user whose saved properties are fetched
