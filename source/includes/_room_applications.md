# Room Applications

Room applications are created when a user applies to live in a room. The room application has several stages including paying application fees and deposits, collecting user information that is necessary to apply to the apartment, as well as review and approval.

## Get a Specific Room Application

```http
GET /api/room_applications/<id> HTTP/1.1
Accept: application/json
Host: roomeze.com
```
```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "data": {
    "id": 12,
    "type": "room_application",
    "attributes": {
      "state": "submitted",
      "fees_and_deposits_complete": true,
      "education_and_employment_complete": true,
      "previous_residence_complete": true,
      "roommate_profile_complete": true,
      "legal_questions_complete": true,
      "document_center_complete": true,
      "created_at": "2017-01-29T21:59:30.064-05:00",
      "updated_at": "2019-02-13T02:55:58.659-05:00"
    },
    "relationships": {
      "user": {
        "data": [
          {
            "id": "9",
            "type": "user"
          }
        ]
      }
    }
  }
}
```

This endpoint retrieves a specific room application.

<aside class="notice">
You must be signed in as the user who the room application or as a user with the <code>admin</code> role.
</aside>

### HTTP Request

`GET https://roomeze.com/api/room_applications/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID        | The ID of the room application to fetch

### Attributes

Parameter                         | Type    | Description
--------------------------------- | ------- | -----------
state                             | String  | The state of the room application. Possible states include `initialized`, `submitted`, `roomeze_approved`, `landlord_approved`, `closed`, `lease_signed`
fees_and_deposits_complete        | Boolean | Whether or not all fees associated with the room application have been paid.
education_and_employment_complete | Boolean | At least one employer or additional income has been created. If the user's user_profile has `current_student` set to `true`, at least one school or employer or additional income has been created.
previous_residence_complete       | Boolean | At least one previous residence has been created.
roommate_profile_complete         | Boolean | An image has been uploaded, traits have been created, and the user profile about_me attribute has been completed.
legal_questions_complete          | Boolean | The user's financial_profile has a value for each of the booleans `convictions`, `refusal_to_pay_rent`, `eviction`, and `bankruptcy`
document_center_complete          | Boolean | The user has uploaded `pay_stubs`, `tax_return`, `bank_statement`, `letter_of_employment`, and `photo_id` documents. If the user's user_profile has `current_student` set to `true`, only a `photo_id` document is required.

### Including Related Resources

`GET https://roomeze.com/api/room_applications/2?include[]=user`

Parameter | Description
--------- | -----------
user      | The user who owns the room application
