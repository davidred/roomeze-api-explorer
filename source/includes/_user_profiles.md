# User Profiles

## Update a User Profile

```http
PATCH /api/user_profiles/2 HTTP/1.1
Accept: application/json
Host: roomeze.com

{
  "data": {
    "id": 2,
    "type": "user_profile",
    "attributes": {
      "gender": "female",
      "budget": "1400",
      "move_in_date": "2019-09-01",
      "date_of_birth": "1990-03-22",
      "has_cat": false,
      "has_dog": true,
      "no_cats": true,
      "no_dogs": false,
      "income": 50000,
      "applying_with_guarantor": false,
      "can_sign_one_year_lease": true,
      "occupation": "Engineer",
      "university": "Boston University",
      "smoker": false,
      "about_me": "I keep my room clean and I like to party.",
      "current_student": false,
    }
    "relationships": {
      "traits": [
        {
          "type": "traits",
          "id": "1"
        },
        {
          "type": "traits",
          "id": "3"
        }
      ]
    }
  },
}
```
```http
HTTP/1.1 200 OK
Content-Type: application/json
Location: https://roomeze.com/api/users/2

{
  "data": {
    "id": 2,
    "type": "user_profile",
    "attributes": {
      "gender": "female",
      "budget": "1400",
      "move_in_date": "2019-09-01",
      "date_of_birth": "1990-03-22",
      "has_cat": false,
      "has_dog": true,
      "no_cats": true,
      "no_dogs": false,
      "income": 50000,
      "applying_with_guarantor": false,
      "can_sign_one_year_lease": true,
      "occupation": "Engineer",
      "university": "Boston University",
      "smoker": false,
      "about_me": "I keep my room clean and I like to party.",
      "current_student": false,
    }
    "relationships": {
      "traits": [
        {
          "type": "traits",
          "id": "1"
        },
        {
          "type": "traits",
          "id": "3"
        }
      ]
    }
  }
}
```

This endpoint updates a user profile

### HTTP Request

`PATCH https://roomeze.com/api/user_profiles/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID        | The ID of the user profile to update

### Parameters

Parameter  | Type   | Description
---------- | ------ | -----------
first_name | String | The first name of the user
last_name  | String | The last name of the user
email      | String | The email address of the user
phone      | String | The phone number of the user

### Related Resources

User profiles can be updated with associated traits. These can be added the the `user_profile` object under `relationships`.

#### Traits

Parameter | Type    | Description
--------- | ------- | -----------
type      | String  | The type of related resource. The value should be `trait`
id        | Integer | The id of the related trait
