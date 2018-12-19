# Users

## Create a User

```http
POST /api/users HTTP/1.1
Accept: application/json
Authorization: Token tOQ4mkzlsJJYX1CWoxvuNPOdeNJjZGOTJ
Host: roomeze.com

{
  "data": {
    "type": "user",
    "attributes": {
      "email": "david@example.com",
      "first_name": "JimBob",
      "last_name": "Cooter",
      "city_ids": [14, 15]
    },
    "relationships": {
      "user_profile": {
        "data": {
          "attributes": {
            "gender": "male",
            "date_of_birth": "1980-12-20"
          }
        }
      }
    }
  }
}
```
```http
HTTP/1.1 201 Created
Content-Type: application/json
Location: https://roomeze.com/api/users/2

{
  "data": {
    "id": 2,
    "type": "user",
    "attributes": {
      "first_name": "JimBob",
      "last_initial": "C",
      "age": 39,
      "role": "user",
      "questionnaire_complete": false,
      "showing_request_questionnaire_complete": false
    },
    "relationships": {
      "user_profile": {
        "data": {
          "id": 3,
          "type": "user_profile"
        }
      }
    }
  }
}
```

This endpoint creates a user

### HTTP Request

`POST https://roomeze.com/api/users`

### Attributes

Parameter  | Type   | Description
---------- | ------ | -----------
first_name | String | The first name of the user
last_name  | String | The last name of the user
email      | String | The email address of the user
phone      | String | The phone number of the user
city_ids   | Array  | The list of ids of cities in which the user wants to live

### Related Resources

Users can be created with associated user profile parameters provided. These can be added the the `user_profile` object under `relationships`. Valid user profile parameters are described below.

#### User Profiles

Parameter               | Type    | Description
----------------------- | ------- | -----------
gender                  | String  | The gender of the user. Possible options are: `male`, `female`
date_of_birth           | String  | The date of birth of the user. Format: `YYYY-MM-DD`
move_in_date            | String  | The date the user is planning to move in. Format `YYYY-MM-DD`
budget                  | Integer | The estimated monthly budget for an apartment
has_cat                 | Boolean | Whether or not the user has a cat
has_dog                 | Boolean | Whether or not the user has a dog
no_cats                 | Boolean | Whether or not the user can live with a cat
no_dogs                 | Boolean | Whether or not the user can live with a dog
can_sign_one_year_lease | Boolean | Whether or not the user can sign a one year lease
applying_with_guarantor | Boolean | Whether or not the user is applying with a guarantor
income                  | Integer | The income of the user

## Update a User

```http
PATCH /api/users/2 HTTP/1.1
Accept: application/json
Authorization: Token tOQ4mkzlsJJYX1CWoxvuNPOdeNJjZGOTJ
Host: roomeze.com

{
  "data": {
    "id": 2,
    "type": "user",
    "attributes": {
      "email": "david@example.com",
      "first_name": "JimBob",
      "last_name": "Cooter",
      "phone": "+1 212 555 6789",
      "city_ids": [2, 14]
    }
    "relationships": {
      "user_profile": {
        "data": {
          "attributes": {
            "gender": "male",
            "date_of_birth": "1980-12-20"
          }
        }
      }
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
    "type": "user",
    "attributes": {
      "first_name": "JimBob",
      "last_initial": "C",
      "age": 39,
      "role": "user",
      "questionnaire_complete": false,
      "showing_request_questionnaire_complete": false
    },
    "relationships": {
      "user_profile": {
        "data": {
          "id": 3,
          "type": "user_profile"
        }
      }
    }
  }
}
```

This endpoint updates a user

### HTTP Request

`PATCH https://roomeze.com/api/users/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID        | The ID of the user to update

### Parameters

Parameter  | Type   | Description
---------- | ------ | -----------
first_name | String | The first name of the user
last_name  | String | The last name of the user
email      | String | The email address of the user
phone      | String | The phone number of the user
city_ids   | Array  | The list of ids of cities in which the user wants to live

### Related Resources

Users can be created with associated user profile parameters provided. These can be added the the `user_profile` object under `relationships`. Valid user profile parameters are described below.

#### User Profiles

Parameter               | Type    | Description
----------------------- | ------- | -----------
gender                  | String  | The gender of the user. Possible options are: `male`, `female`
date_of_birth           | String  | The date of birth of the user. Format: `YYYY-MM-DD`
move_in_date            | String  | The date the user is planning to move in. Format `YYYY-MM-DD`
budget                  | Integer | The estimated monthly budget for an apartment
has_cat                 | Boolean | Whether or not the user has a cat
has_dog                 | Boolean | Whether or not the user has a dog
no_cats                 | Boolean | Whether or not the user can live with a cat
no_dogs                 | Boolean | Whether or not the user can live with a dog
can_sign_one_year_lease | Boolean | Whether or not the user can sign a one year lease
applying_with_guarantor | Boolean | Whether or not the user is applying with a guarantor
income                  | Integer | The income of the user
