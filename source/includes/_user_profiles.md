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
      "move_in_period": "browsing",
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
      "preferred_room_types": ['comfy', 'biggy']
    },
    "relationships": {
      "traits": {
        "data": [
          {
            "type": "trait",
            "id": "1"
          },
          {
            "type": "trait",
            "id": "3"
          }
        ]
      }
    }
  }
}
```
```http
HTTP/1.1 200 OK
Content-Type: application/json
Location: https://roomeze.com/api/user_profiles/2

{
  "data": {
    "id": 2,
    "type": "user_profile",
    "attributes": {
      "gender": "female",
      "budget": "1400",
      "move_in_date": "2019-09-01",
      "move_in_period": "browsing",
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
      "preferred_room_types": ['comfy', 'biggy']
    },
    "relationships": {
      "traits": {
        "data": [
          {
            "type": "trait",
            "id": "1"
          },
          {
            "type": "trait",
            "id": "3"
          }
        ]
      }
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

Parameter               | Type    | Description
----------------------- | ------- | -----------
gender                  | String  | The gender of the user. Possible options are: `male`, `female`
date_of_birth           | String  | The date of birth of the user. Format: `YYYY-MM-DD`
move_in_date            | String  | The date the user is planning to move in. Format `YYYY-MM-DD`
move_in_period          | String  | The timeframe in which the user plans to move. Possible options are: <code>month</code>, <code>year</code>, <code>browsing</code>.
budget                  | Integer | The estimated monthly budget for an apartment
has_cat                 | Boolean | Whether or not the user has a cat
has_dog                 | Boolean | Whether or not the user has a dog
no_cats                 | Boolean | Whether or not the user can live with a cat
no_dogs                 | Boolean | Whether or not the user can live with a dog
can_sign_one_year_lease | Boolean | Whether or not the user can sign a one year lease
applying_with_guarantor | Boolean | Whether or not the user is applying with a guarantor
income                  | Integer | The income of the user
preferred_room_types    | Array   | The set of preferred room types. Valid options are: <code>cozy</code>, <code>comfy</code>, <code>roomy</code>, <code>biggy</code>.

### Related Resources

User profiles can be updated with associated traits. These can be added the the `user_profile` object under `relationships`.

#### Traits

Parameter | Type    | Description
--------- | ------- | -----------
type      | String  | The type of related resource. The value should be `trait`
id        | Integer | The id of the related trait
