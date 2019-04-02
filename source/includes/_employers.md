# Employers

Employers belong to a user's financial profile. Employer information is collected as part of the application process for an apartment.

## Create an Employer

```http
POST /api/financial_profiles/3/employers HTTP/1.1
Accept: application/json
Host: roomeze.com

{
  "data": {
    "type": "employer",
    "attributes": {
      "name": "Google",
      "position": "Engineer",
      "monthly_income": "10000",
      "start_date": "2015-02-23",
      "end_date": "2019-02-23",
      "current": false,
      "contact_first": "Jimbob",
      "contact_last": "Cooter",
      "contact_email": "jimbob_cooter@gmail.com",
      "contact_phone": "+1 (718) 555-5555"
    }
  }
}
```
```http
HTTP/1.1 201 Created
Content-Type: application/json
Location: https://roomeze.com/api/employers/2

{
  "data": {
    "id": 2,
    "type": "employer",
    "attributes": {
      "name": "Google",
      "position": "Engineer",
      "monthly_income": "10000",
      "start_date": "2015-02-23",
      "end_date": "2019-02-23",
      "current": false,
      "contact_first": "Jimbob",
      "contact_last": "Cooter",
      "contact_email": "jimbob_cooter@gmail.com",
      "contact_phone": "+1 (718) 555-5555"
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

This endpoint creates an employer

<aside class="notice">
You must be signed in as the user who owns the financial profile for which the employer is being created or as a user with the <code>admin</code> role.
</aside>

### HTTP Request

`POST https://roomeze.com/api/financial_profiles/<FINANCIAL_PROFILE_ID>/employers`

### URL Parameters

Parameter            | Description
-------------------- | -----------
FINANCIAL_PROFILE_ID | The ID of the financial_profile to which the employer will belong

### Attributes

Parameter      | Type    | Description
-------------- | ------- | -----------
name           | String  | The name of the employer
position       | String  | The position held at the place of employment
monthly_income | Integer | The monthly income received from the employer
start_date     | String  | The starting date of the employment
end_date       | String  | The ending date of the employment. If <code>current</code> is set to <code>true</code>, this is not required
current        | Boolean | Whether or not this is the user's current place of employment
contact_first  | String  | The first name of a contact at the place of employment
contact_last   | String  | The last name of a contact at the place of employment
contact_email  | String  | The email address of a contact at the place of employment
contact_phone  | String  | The phone number of a contact at the place of employment

## Update an Employer

```http
PATCH /api/employers/2 HTTP/1.1
Accept: application/json
Host: roomeze.com

{
  "data": {
    "type": "employer",
    "attributes": {
      "name": "Google",
      "position": "Engineer",
      "monthly_income": "10000",
      "start_date": "2015-02-23",
      "end_date": "2019-02-23",
      "current": false,
      "contact_first": "Jimbob",
      "contact_last": "Cooter",
      "contact_email": "jimbob_cooter@gmail.com",
      "contact_phone": "+1 (718) 555-5555"
    }
  }
}
```
```http
HTTP/1.1 200 OK
Content-Type: application/json
Location: https://roomeze.com/api/employers/2

{
  "data": {
    "id": 2,
    "type": "employer",
    "attributes": {
      "name": "Google",
      "position": "Engineer",
      "monthly_income": "10000",
      "start_date": "2015-02-23",
      "end_date": "2019-02-23",
      "current": false,
      "contact_first": "Jimbob",
      "contact_last": "Cooter",
      "contact_email": "jimbob_cooter@gmail.com",
      "contact_phone": "+1 (718) 555-5555"
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

This endpoint updates an employer

<aside class="notice">
You must be signed in as the user who owns the financial profile for which the employer is being updated or as a user with the <code>admin</code> role.
</aside>

### HTTP Request

`PATCH https://roomeze.com/api/employers/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID        | The ID of the employer

### Attributes

Parameter      | Type    | Description
-------------- | ------- | -----------
name           | String  | The name of the employer
position       | String  | The position held at the place of employment
monthly_income | Integer | The monthly income received from the employer
start_date     | String  | The starting date of the employment. Format `YYYY-MM-DD`
end_date       | String  | The ending date of the employment. Format `YYYY-MM-DD`. If `current` is set to `true`, this field is not required.
current        | Boolean | Whether or not this is the user's current place of employment
contact_first  | String  | The first name of a contact at the place of employment
contact_last   | String  | The last name of a contact at the place of employment
contact_email  | String  | The email address of a contact at the place of employment
contact_phone  | String  | The phone number of a contact at the place of employment

## Delete an Employer

```http
DELETE /api/employers/2 HTTP/1.1
Accept: application/json
Host: roomeze.com
```
```http
HTTP/1.1 204 No Content
Content-Type: application/json
```

This endpoint deletes an employer

<aside class="notice">
You must be signed in as the user who owns the financial profile for which the employer is being deleted or as a user with the <code>admin</code> role.
</aside>

### HTTP Request

`DELETE https://roomeze.com/api/employers/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID        | The ID of the employer
