# Documents

## Create a Document

```http
POST /api/documents HTTP/1.1
Accept: application/json
Host: roomeze.com

{
  "data": {
    "type": "document",
    "attributes": {
      "remote_url": "https://new_document.cloudfront.net/documents/new_document.jpg"
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
```http
HTTP/1.1 201 Created
Content-Type: application/json
Location: https://roomeze.com/api/documents/2

{
  "data": {
    "id": 2,
    "type": "document",
    "attributes": {
      "document_type": "pay_stub",
      "title": "Pay Stub",
      "file_name": "new_document.jpg"
      "created_at": "2019-01-29T21:59:30.064-05:00",
      "updated_at": "2019-01-29T21:59:30.064-05:00",
    },
    "relationships": {
      "documentable": {
        "id": 3,
        "type": "financial_profile"
      }
    }
  }
}
```

This endpoint creates an document

<aside class="notice">
You must be signed in as the user for which the document is being created or as a user with the <code>admin</code> role.
</aside>

### HTTP Request

`POST https://roomeze.com/api/documents`

### Attributes

Parameter   | Type   | Description
----------- | ------ | -----------
remote_url  | String | The remote_url of the document

### Related Resources

documents must be created with a related resource. This will associate the document with the passed related resource. These resources can be added the the `relationships` object.

Parameter | Type    | Description
--------- | ------- | -----------
type      | String  | The type of related resource. The possible options are <code>financial_profile</code>
id        | Integer | The id of the related resource.

## Delete a Document

```http
DELETE /api/documents/2 HTTP/1.1
Accept: application/json
Host: roomeze.com
```
```http
HTTP/1.1 204 No Content
Content-Type: application/json
```

This endpoint deletes an document

<aside class="notice">
You must be signed in as the user to whom the document belongs or as a user with the <code>admin</code> role.
</aside>

### HTTP Request

`DELETE https://roomeze.com/api/documents/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID        | The ID of the document
