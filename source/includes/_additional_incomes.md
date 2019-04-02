# Additional Incomes

Additional incomes belong to a user's financial profile. These are incomes that are received outside of an employer income. Additional income information is collected as part of the application process for an apartment.

## Create an Additional Income

```http
POST /api/financial_profiles/3/additional_incomes HTTP/1.1
Accept: application/json
Host: roomeze.com

{
  "data": {
    "type": "additional_income",
    "attributes": {
      "source": "Mom and Dad",
      "monthly_income": 5000
    }
  }
}
```
```http
HTTP/1.1 201 Created
Content-Type: application/json
Location: https://roomeze.com/api/additional_incomes/2

{
  "data": {
    "id": 2,
    "type": "additional_income",
    "attributes": {
      "source": "Mom and Dad",
      "monthly_income": 5000,
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

This endpoint creates an additional income

<aside class="notice">
You must be signed in as the user who owns the financial profile for which the additional income is being created or as a user with the <code>admin</code> role.
</aside>

### HTTP Request

`POST https://roomeze.com/api/financial_profiles/<FINANCIAL_PROFILE_ID>/additional_incomes`

### URL Parameters

Parameter            | Description
-------------------- | -----------
FINANCIAL_PROFILE_ID | The ID of the financial_profile to which the additional income will belong

### Attributes

Parameter      | Type    | Description
-------------- | ------- | -----------
source         | String  | The source from which this income is received
monthly_income | Integer | The amount of monthly income received from this source

## Update an Additional Income

```http
PATCH /api/schools/2 HTTP/1.1
Accept: application/json
Host: roomeze.com

{
  "data": {
    "type": "school",
    "attributes": {
      "source": "Grandma and Grandpa",
      "monthly_income": 5000
    }
  }
}
```
```http
HTTP/1.1 200 OK
Content-Type: application/json
Location: https://roomeze.com/api/additional_incomes/2

{
  "data": {
    "id": 2,
    "type": "employer",
    "attributes": {
      "source": "Grandma and Grandpa",
      "monthly_income": 5000,
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

This endpoint updates an additional income

<aside class="notice">
You must be signed in as the user who owns the financial profile for which the additional income is being updated or as a user with the <code>admin</code> role.
</aside>

### HTTP Request

`PATCH https://roomeze.com/api/additional_incomes/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID        | The ID of the additional income

### Attributes

Parameter      | Type    | Description
-------------- | ------- | -----------
source         | String  | The source from which this income is received
monthly_income | Integer | The amount of monthly income received from this source

## Delete an Additional Income

```http
DELETE /api/additional_incomes/2 HTTP/1.1
Accept: application/json
Host: roomeze.com
```
```http
HTTP/1.1 204 No Content
Content-Type: application/json
```

This endpoint deletes an additional income

<aside class="notice">
You must be signed in as the user who owns the financial profile for which the additional income is being deleted or as a user with the <code>admin</code> role.
</aside>

### HTTP Request

`DELETE https://roomeze.com/api/additional_incomes/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID        | The ID of the addtional income
