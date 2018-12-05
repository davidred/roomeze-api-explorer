---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - http
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Roomeze API! You can use our API to access Roomeze API endpoints, which can get information on various rooms, users, and buildings in our database.

You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/lord/slate). Feel free to edit it and use it as a base for your own API's documentation.

# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Properties

## Get Property

```http
GET /api/properties/<id> HTTP/1.1
Accept: application/json
Host: roomeze.com
```
```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "data": {
    "id": 82,
    "type": "property",
    "attributes": {
      "bedrooms": 3,
      "bathrooms": 2,
      "available_at": "2018-12-15",
      "display": true,
      "virtual_tour_url": "https://my.matterport.com/show/?m=blaHBlah",
      "displayed_at": "2018-11-30",
      "image_urls": [
        "https://1234abcd.cloudfront.net/uploads/image/199/hOkeYpOkey_large_IMG_1234.JPG",
        "https://4567efgh.cloudfront.net/uploads/image/199/hOkeYpOkey_large_IMG_4567.JPG"
      ],
      "lease_period": "1 year",
      "highly_saved": false,
      "good_deal": true,
      "highly_viewed": false,
    },
    "relationships": {
      "rooms": {
        "data": [
          {
            "id": 175,
            "type": "room"
          }
        ]
      },
      "building": {
        "data": {
          "id": 24,
          "type": "building"
        }
      }
    }
  },
  "included": [
    {
      id: "24",
      type: "building",
      attributes: {
        description: "",
        latitude: 40.6744208,
        longitude: -73.9636529,
      },
      relationships: {
        address: {
          data: {
            id: 45,
            type: "address"
          }
        },
        management_company: {
          data: {
            id: 76,
            type: "management_company"
          }
        },
        building_stops: {
          data: [
            {
              id: 85,
              type: "building_stop"
            }
          ]
        },
        amenities: {
          data: [
            {
              id: 59,
              type: "amenity"
            }
          ]
        }
      }
    },
    {
      id: "175",
      type: "room",
      attributes: {
        name: "Red Room",
        price: 1000,
        room_type: "Comfy Room",
        image_urls: [
          "https://7890abcd.cloudfront.net/uploads/image/199/hOkeYpOkey_large_IMG_7890.JPG",
        ]
      },
      relationships: {
        user: {
          data: {
            id: 252,
            type: "user",
          }
        },
        couple: {
          data: {
            id: 253,
            type: "user",
          }
        },
        amenities: {
          data: [
            {
              id: 147,
              type: "amenity"
            }
          ]
        }
      }
    }
  ]
}
```

### HTTP Request

`GET https://roomeze.com/api/properties/2`

### Including Related Resources

`GET https://roomeze.com/api/properties/2?included[]=rooms.user`

Parameter    | Description
------------ | -----------
amenities    | The amenities belonging to the property
rooms.user   | The user occupying the room
rooms.couple | The couple (second user) occupying the room
rooms.amenities    | The amenities belonging to the associated rooms
building.amenities | The amenities belonging to the associated building
building.address.neighborhood | The neighborhood belonging to the associated address

## Get Properties

`GET https://roomeze.com/api/properties`

```http
GET /api/properties HTTP/1.1
Accept: application/json
Host: roomeze.com
```
```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "meta": {
    page_info: {
      total_pages: 5,
      current_page: 1,
      prev_page: null,
      next_page: 2,
      page_size: 25,
      total_count: 115
    }
  },
  "data": [
    {
      "id": 82,
      "type": "property",
      "attributes": {
        "bedrooms": 3,
        "bathrooms": 2,
        "available_at": "2018-12-15",
        "display": true,
        "virtual_tour_url": "https://my.matterport.com/show/?m=blaHBlah",
        "displayed_at": "2018-11-30",
        "image_urls": [
          "https://1234abcd.cloudfront.net/uploads/image/199/hOkeYpOkey_large_IMG_1234.JPG",
          "https://4567efgh.cloudfront.net/uploads/image/199/hOkeYpOkey_large_IMG_4567.JPG"
        ],
        "lease_period": "1 year",
        "highly_saved": false,
        "good_deal": true,
        "highly_viewed": false,
      },
      "relationships": {
        "rooms": {
          "data": [
            {
              "id": 175,
              "type": "room"
            }
          ]
        },
        "building": {
          "data": {
            "id": 24,
            "type": "building"
          }
        }
      }
    }
  ],
  "included": [
    {
      id: "24",
      type: "building",
      attributes: {
        description: "",
        latitude: 40.6744208,
        longitude: -73.9636529,
      },
      relationships: {
        address: {
          data: {
            id: 45,
            type: "address"
          }
        },
        management_company: {
          data: {
            id: 76,
            type: "management_company"
          }
        },
        building_stops: {
          data: [
            {
              id: 85,
              type: "building_stop"
            }
          ]
        },
        amenities: {
          data: [
            {
              id: 59,
              type: "amenity"
            }
          ]
        }
      }
    },
    {
      id: "175",
      type: "room",
      attributes: {
        name: "Red Room",
        price: 1000,
        room_type: "Comfy Room",
        image_urls: [
          "https://7890abcd.cloudfront.net/uploads/image/199/hOkeYpOkey_large_IMG_7890.JPG",
        ]
      },
      relationships: {
        user: {
          data: {
            id: 252,
            type: "user",
          }
        },
        couple: {
          data: {
            id: 253,
            type: "user",
          }
        },
        amenities: {
          data: [
            {
              id: 147,
              type: "amenity"
            }
          ]
        }
      }
    }
  ]
}
```

### Including Related Resources

See Get Property section for a list of possible properties

### Filter Parameters

`GET https://roomeze.com/api/properties?filter[display]=false`

Parameter          | Type    | Options                   | Example                            | Description
------------------ | ------- | ------------------------- | ---------------------------------- | -----------
active             | Boolean |                           | ?filter[active]=true               | Whether or not the property is set to active (Admin only)
display            | Boolean |                           | ?filter[display]=true              | Whether or not the property is displayed to website users (Admin only)
age_range          | CSV     |                           | ?filter[age_range]=18,24           | Return properties in which all roommates are within the specified age range
gender             | String  | male, female              | ?filter[gender]=female             | Return properties in which all roommates are of the specified gender
available          | Boolean |                           | ?filter[available]=true            | Whether or not the property has any rooms that are not occupied
bedrooms           | Integer |                           | ?filter[bedrooms]=3                | Return properties with the specified number of bedrooms
bathrooms          | Integer |                           | ?filter[bathrooms]=2               | Return properties with at least the specified number of bathrooms
max_bedrooms       | Integer |                           | ?filter[max_bedrooms]=3            | Return properties with less than the specified number of bedrooms
available_date     | String  |                           | ?filter[available_date]=2018-09-15 | Return properties that are available in the month and year specified
min_price          | Integer |                           | ?filter[min_price]=1000            | Return properties with an available room greater than or equal to the specified price
max_price          | Integer |                           | ?filter[max_price]=2000            | Return properties with an available room less than or equal to the specified price
open_rooms         | Integer |                           | ?filter[open_rooms]=2              | Return properties that have the specified number of available rooms
room_types         | CSV     | cozy, comfy, roomy, biggy | ?filter[room_types]=cozy,comfy     | Return properties that have available rooms of any of the specified sizes
neighborhoods      | Array   |                           | ?filter[neighborhoods][]=82        | Return properties that are in any of the specified neighborhoods
subway_lines       | CSV     |                           | ?filter[subway_lines][]=1,F,N      | Return properties that are within 1 mile of any of the specified subway lines
property_amenities | CSV     |                           | ?filter[amenities]=14,37           | Return properties that have all of the specified amenities
building_amenities | CSV     |                           | ?filter[building_amenities]=67,34  | Return properties that are associated with a building with all of the specified amenities
room_amenities     | CSV     |                           | ?filter[room_amenities]=25         | Return properties that have available rooms with all of the specified room amenities

# Kittens

## Get All Kittens

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete

