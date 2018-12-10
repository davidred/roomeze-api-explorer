# Users

## Create a User

```http
POST /api/users HTTP/1.1
Accept: application/json
Authorization: Token tOQ4mkzlsJJYX1CWoxvuNPOdeNJjZGOTJ
Host: roomeze.com

{
  "data": {
    "attributes": {
      "email": "david@example.com",
      "first_name": "JimBob",
      "last_name": "Cooter"
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