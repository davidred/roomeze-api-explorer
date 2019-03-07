# Images

## Create an Image

```http
POST /api/images HTTP/1.1
Accept: application/json
Host: roomeze.com

{
  "data": {
    "type": "image",
    "attributes": {
      "remote_url": "https://new_image.cloudfront.net/images/new_image.jpg"
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
```http
HTTP/1.1 201 Created
Content-Type: application/json
Location: https://roomeze.com/api/images/2

{
  "data": {
    "id": 2,
    "type": "image",
    "attributes": {
      "image_url": "https://new_image.cloudfront.net/images/new_image.jpg",
      "thumb_url": "https://new_image_thumb.cloudfront.net/images/new_image.jpg",
      "preview_url": "https://new_image_preview.cloudfront.net/images/new_image.jpg",
      "full_url": "https://new_image_full.cloudfront.net/images/new_image.jpg",
      "image_type": "main",
      "created_at": "2019-01-29T21:59:30.064-05:00",
      "updated_at": "2019-01-29T21:59:30.064-05:00",
    }
  }
}
```

This endpoint creates an image

<aside class="notice">
You must be signed in as the user for which the image is being created or as a user with the <code>admin</code> role.
</aside>

### HTTP Request

`POST https://roomeze.com/api/images`

### Attributes

Parameter   | Type   | Description
----------- | ------ | -----------
remote_url  | String | The remote_url of the image

## Delete an Image

```http
DELETE /api/images/2 HTTP/1.1
Accept: application/json
Host: roomeze.com
```
```http
HTTP/1.1 204 No Content
Content-Type: application/json
```

This endpoint deletes an image

<aside class="notice">
You must be signed in as the user to whom the image belongs or as a user with the <code>admin</code> role.
</aside>

### HTTP Request

`DELETE https://roomeze.com/api/images/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID        | The ID of the image
