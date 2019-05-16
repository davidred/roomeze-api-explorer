# Previous Residences

## Create a Previous Residence

```http
POST /api/users/2/previous_residences HTTP/1.1
Accept: application/json
Host: roomeze.com

{
  "data": {
    "id": 2,
    "type": "previous_residence",
    "attributes": {
      "unit_number": "5B",
      "rent": 1500,
      "current": false,
      "move_in": "2015-02-23",
      "move_out": "2019-02-23",
      "landlord_name": "Trump Management",
      "contact_email": "donald@trump.com",
      "contact_phone": "555-555-1234"
    },
    "relationships": {
      "place": {
        "data": {
          "type": "place",
          "id": "1"
        }
      }
    }
  }
}
```
```http
HTTP/1.1 201 Created
Content-Type: application/json
Location: https://roomeze.com/api/previous_residences/2

{
  "data": {
    "id": 2,
    "type": "previous_residence",
    "attributes": {
      "unit_number": "5B",
      "rent": 1500,
      "current": false,
      "move_in": "2015-02-23",
      "move_out": "2019-02-23",
      "landlord_name": "Trump Management",
      "contact_email": "donald@trump.com",
      "contact_phone": "555-555-1234"
    },
    "relationships": {
      "place": {
        "data": {
          "type": "place",
          "id": "1"
        }
      }
    }
  }
}
```

This endpoint creates a previous residence

### HTTP Request

`POST https://roomeze.com/api/users/<ID>/previous_resdiences`

### URL Parameters

Parameter | Description
--------- | -----------
ID        | The ID of the user to whom the previous residence belongs

### Parameters

Parameter     | Type    | Description
------------- | ------- | -----------
unit_number   | String  | The unit number of the property.
current       | Boolean | Whether or not the user is currently living at the property.
move_in       | String  | The date the user moved in to the property. Format `YYYY-MM-DD`
move_out      | String  | The date the user moved out of the property. Format `YYYY-MM-DD`
rent          | String  | The monthly rent of the property
landlord_name | String  | The name of the landlord or management company who owns or manages the property
contact_email | String  | The email where the landlord or management company can be reached
contact_phone | String  | The phone number where the landlord or management company can be reached

## Update a Previous Residence

```http
PATCH /api/previous_residences/2 HTTP/1.1
Accept: application/json
Host: roomeze.com

{
  "data": {
    "id": 2,
    "type": "previous_residence",
    "attributes": {
      "unit_number": "5B",
      "rent": 1500,
      "current": false,
      "move_in": "2015-02-23",
      "move_out": "2019-02-23",
      "landlord_name": "Trump Management",
      "contact_email": "donald@trump.com",
      "contact_phone": "555-555-1234"
    },
    "relationships": {
      "place": {
        "data": {
          "type": "place",
          "id": "1"
        }
      }
    }
  }
}
```
```http
HTTP/1.1 200 OK
Content-Type: application/json
Location: https://roomeze.com/api/previous_residences/2

{
  "data": {
    "id": 2,
    "type": "previous_residence",
    "attributes": {
      "unit_number": "5B",
      "rent": 1500,
      "current": false,
      "move_in": "2015-02-23",
      "move_out": "2019-02-23",
      "landlord_name": "Trump Management",
      "contact_email": "donald@trump.com",
      "contact_phone": "555-555-1234"
    },
    "relationships": {
      "place": {
        "data": {
          "type": "place",
          "id": "1"
        }
      }
    }
  }
}
```

This endpoint updates a previous residence

### HTTP Request

`PATCH https://roomeze.com/api/previous_residences/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID        | The ID of the previous residence to update

### Parameters

Parameter     | Type    | Description
------------- | ------- | -----------
unit_number   | String  | The unit number of the property.
current       | Boolean | Whether or not the user is currently living at the property.
move_in       | String  | The date the user moved in to the property. Format `YYYY-MM-DD`
move_out      | String  | The date the user moved out of the property. Format `YYYY-MM-DD`
rent          | String  | The monthly rent of the property
landlord_name | String  | The name of the landlord or management company who owns or manages the property
contact_email | String  | The email where the landlord or management company can be reached
contact_phone | String  | The phone number where the landlord or management company can be reached

### Related Resources

Previous residences are associated with a place. These can be added the the `previous_residences` object under `relationships`.

#### Permanent Address

Parameter | Type    | Description
--------- | ------- | -----------
type      | String  | The type of related resource. The value should be `place`
id        | Integer | The id of the place

## Delete a Previous Residence

```http
DELETE /api/previous_residences/2 HTTP/1.1
Accept: application/json
Host: roomeze.com
```
```http
HTTP/1.1 204 No Content
Content-Type: application/json
```

This endpoint deletes a previous residence

<aside class="notice">
You must be signed in as the user who owns the previous residence that is being deleted or as a user with the <code>admin</code> role.
</aside>

### HTTP Request

`DELETE https://roomeze.com/api/previous_residences/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID        | The ID of the previous_residence
