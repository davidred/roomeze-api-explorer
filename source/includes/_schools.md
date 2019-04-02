# Schools

Schools belong to a user's financial profile. School information is collected as part of the application process for an apartment.

## Create a School

```http
POST /api/financial_profiles/3/schools HTTP/1.1
Accept: application/json
Host: roomeze.com

{
  "data": {
    "type": "school",
    "attributes": {
      "name": "Boston University",
      "focus": "Biomedical Engineering",
      "start_date": "2005-09-01",
      "part_time": false
    }
  }
}
```
```http
HTTP/1.1 201 Created
Content-Type: application/json
Location: https://roomeze.com/api/schools/2

{
  "data": {
    "id": 2,
    "type": "school",
    "attributes": {
      "name": "Boston University",
      "focus": "Biomedical Engineering",
      "start_date": "2005-09-01",
      "part_time": false,
      "created_at": "2017-01-29T21:59:30.064-05:00",
      "updated_at": "2017-01-29T21:59:30.064-05:00"
    },
    "relationships": {
      "financial_profile": {
        "data": {
          "id": 3,
          "type": "financial_profile"
        }
      }
    }
  }
}
```

This endpoint creates a school

<aside class="notice">
You must be signed in as the user who owns the financial profile for which the school is being created or as a user with the <code>admin</code> role.
</aside>

### HTTP Request

`POST https://roomeze.com/api/financial_profiles/<FINANCIAL_PROFILE_ID>/schools`

### URL Parameters

Parameter            | Description
-------------------- | -----------
FINANCIAL_PROFILE_ID | The ID of the financial_profile to which the school will belong

### Attributes

Parameter       | Type    | Description
--------------- | ------- | -----------
name            | String  | The name of the school
focus           | String  | The focus or subject being studied
start_date      | Integer | The date the user began attending the school. Format `YYYY-MM-DD`
graduation_date | String  | The date the user graduated or plans to graduate. Format `YYYY-MM-DD`
part_time       | Boolean | Whether or not attendance at this school is part time.

## Update a School

```http
PATCH /api/schools/2 HTTP/1.1
Accept: application/json
Host: roomeze.com

{
  "data": {
    "type": "school",
    "attributes": {
      "name": "Boston University",
      "focus": "Biomedical Engineering",
      "start_date": "2005-09-01",
      "part_time": false
    }
  }
}
```
```http
HTTP/1.1 200 OK
Content-Type: application/json
Location: https://roomeze.com/api/schools/2

{
  "data": {
    "id": 2,
    "type": "employer",
    "attributes": {
      "name": "Boston University",
      "focus": "Biomedical Engineering",
      "start_date": "2005-09-01",
      "part_time": false,
      "created_at": "2017-01-29T21:59:30.064-05:00",
      "updated_at": "2019-02-13T02:55:58.659-05:00"
    },
    "relationships": {
      "financial_profile": {
        "data": {
          "id": 3,
          "type": "financial_profile"
        }
      }
    }
  }
}
```

This endpoint updates a school

<aside class="notice">
You must be signed in as the user who owns the financial profile for which the school is being updated or as a user with the <code>admin</code> role.
</aside>

### HTTP Request

`PATCH https://roomeze.com/api/schools/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID        | The ID of the school

### Attributes

Parameter       | Type    | Description
--------------- | ------- | -----------
name            | String  | The name of the school
focus           | String  | The focus or subject being studied
start_date      | Integer | The date the user began attending the school. Format `YYYY-MM-DD`
graduation_date | String  | The date the user graduated or plans to graduate. Format `YYYY-MM-DD`
part_time       | Boolean | Whether or not attendance at this school is part time.

## Delete a School

```http
DELETE /api/schools/2 HTTP/1.1
Accept: application/json
Host: roomeze.com
```
```http
HTTP/1.1 204 No Content
Content-Type: application/json
```

This endpoint deletes a school

<aside class="notice">
You must be signed in as the user who owns the financial profile for which the school is being deleted or as a user with the <code>admin</code> role.
</aside>

### HTTP Request

`DELETE https://roomeze.com/api/schools/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID        | The ID of the school
