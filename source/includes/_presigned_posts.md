# Presigned Posts

## Get a Presigned Post url for images

```http
GET /api/presigned_post_images HTTP/1.1
Accept: application/json
Host: roomeze.com
```
```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "url": "https://roomeze.s3.amazon.com",
  "url_fields": {
    "key": "uploads/images/35674c61-86b0-4fe8-b7ae-d0b4f77fba67/${filename}",
    "success_action_status": "201",
    "acl": "public-read",
    "policy": ""eyJleHBpcmF0aW9uIjoiMjAxOS0wNS0xNb25kaXRpb25zIjpbeyJidWNrZXQiOiJy",
    "x-amz-credential": "YMMS7Q/20190516/us-east-1/s3/aws4_request",
    "x-amz-algorithm": "AWS4-HMAC-SHA256",
    "x-amz-date": "20190516T213911Z",
    "x-amz-signature": "8d21f681fb3e8c670aaf037ba71e543"
  }
}
```

This endpoint gets a presigned post for uploading images

### HTTP Request

`GET https://roomeze.com/api/presigned_post_images`

## Get a Presigned Post url for documents

```http
GET /api/presigned_post_images HTTP/1.1
Accept: application/json
Host: roomeze.com
```
```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "url": "https://roomeze.s3.amazon.com",
  "url_fields": {
    "key": "uploads/documents/35674c61-86b0-4fe8-b7ae-d0b4f77fba67/${filename}",
    "success_action_status": "201",
    "acl": "private",
    "policy": ""eyJleHBpcmF0aW9uIjoiMjAxOS0wNS0xNb25kaXRpb25zIjpbeyJidWNrZXQiOiJy",
    "x-amz-credential": "YMMS7Q/20190516/us-east-1/s3/aws4_request",
    "x-amz-algorithm": "AWS4-HMAC-SHA256",
    "x-amz-date": "20190516T213911Z",
    "x-amz-signature": "8d21f681fb3e8c670aaf037ba71e543"
  }
}
```

This endpoint gets a presigned post for uploading documents

### HTTP Request

`GET https://roomeze.com/api/presigned_post_documents`
