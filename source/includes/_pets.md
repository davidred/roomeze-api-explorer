# Pets

## Create a Pet

```http
POST /api/users/3/pets HTTP/1.1
Accept: application/json
Host: roomeze.com

{
  "data": {
    "type": "pet",
    "attributes": {
      "name": "sparky",
      "animal": "dog",
      "description": "Barks a lot."
    }
  }
}
```
```http
HTTP/1.1 201 Created
Content-Type: application/json
Location: https://roomeze.com/api/pets/2

{
  "data": {
    "id": 2,
    "type": "pet",
    "attributes": {
      "name": "sparky",
      "animal": "dog",
      "description": "Barks a lot."
    },
    "relationships": {
      "user": {
        "data": {
          "id": 3,
          "type": "user"
        }
      }
    }
  }
}
```

This endpoint creates a pet

<aside class="notice">
You must be signed in as the user for which the pet is being created or as a user with the <code>admin</code> role.
</aside>

### HTTP Request

`POST https://roomeze.com/api/users/<USER_ID>/pets`

### URL Parameters

Parameter | Description
--------- | -----------
USER_ID   | The ID of the user to which the pet will belong

### Attributes

Parameter   | Type   | Description
----------- | ------ | -----------
name        | String | The name of the pet
animal      | String | The type of animal. The possible options are: <code>dog</code>, <code>cat</code>, and <code>other</code>
description | String | The description of the pet

## Update a Pet

```http
PATCH /api/pets/2 HTTP/1.1
Accept: application/json
Host: roomeze.com

{
  "data": {
    "type": "pet",
    "attributes": {
      "name": "sparky",
      "animal": "dog",
      "description": "Barks a lot."
    }
  }
}
```
```http
HTTP/1.1 200 OK
Content-Type: application/json
Location: https://roomeze.com/api/pets/2

{
  "data": {
    "id": 2,
    "type": "pet",
    "attributes": {
      "name": "sparky",
      "animal": "dog",
      "description": "Barks a lot."
    },
    "relationships": {
      "user": {
        "data": {
          "id": 3,
          "type": "user"
        }
      }
    }
  }
}
```

This endpoint updates a pet

<aside class="notice">
You must be signed in as the user to whom the pet belongs or as a user with the <code>admin</code> role.
</aside>

### HTTP Request

`PATCH https://roomeze.com/api/pets/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID        | The ID of the pet

### Attributes

Parameter   | Type   | Description
----------- | ------ | -----------
name        | String | The name of the pet
animal      | String | The type of animal. The possible options are: <code>dog</code>, <code>cat</code>, and <code>other</code>
description | String | The description of the pet

## Delete a Pet

```http
DELETE /api/pets/2 HTTP/1.1
Accept: application/json
Host: roomeze.com
```
```http
HTTP/1.1 204 No Content
Content-Type: application/json
```

This endpoint deletes a pet

<aside class="notice">
You must be signed in as the user to whom the pet belongs or as a user with the <code>admin</code> role.
</aside>

### HTTP Request

`DELETE https://roomeze.com/api/pets/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID        | The ID of the pet
