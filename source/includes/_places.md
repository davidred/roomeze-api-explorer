# Places

## Create a Place

```http
POST /api/places HTTP/1.1
Accept: application/json
Host: roomeze.com

{
  "data": {
    "type": "place",
    "attributes": {
      "floor": "3",
      "street_number": "123",
      "route": "East 54th Street",
      "locality": "Midtown",
      "administrative_area_level_2": "Brooklyn",
      "administrative_area_level_1": "New York",
      "administrative_area_level_1_short_name": "NY",
      "country": "United States",
      "country_short_name": "US",
      "postal_code": 10001,
      "latitude": "-33.866651",
      "longitude": "151.195827",
      "place_id": "ChIJN1t_tDeuEmsRUsoyG83frY4",
      "name": "Roomeze",
      "icon": "https://maps.gstatic.com/mapfiles/place_api/icons/generic_business-71.png",
      "formatted_address": "123 East 54th Street, New York, NY",
      "formatted_phone_number": "(02) 9374 4000",
      "international_phone_number": "+61 2 9374 4000"
    }
  }
}
```
```http
HTTP/1.1 201 Created
Content-Type: application/json
Location: https://roomeze.com/api/pets/2

{
  "data": {
    "id": 2,
    "type": "place",
    "attributes": {
      "floor": "3",
      "street_number": "123",
      "route": "East 54th Street",
      "locality": "Midtown",
      "administrative_area_level_2": "Brooklyn",
      "administrative_area_level_1": "New York",
      "administrative_area_level_1_short_name": "NY",
      "country": "United States",
      "country_short_name": "US",
      "postal_code": 10001,
      "latitude": "-33.866651",
      "longitude": "151.195827",
      "place_id": "ChIJN1t_tDeuEmsRUsoyG83frY4",
      "name": "Roomeze",
      "icon": "https://maps.gstatic.com/mapfiles/place_api/icons/generic_business-71.png",
      "formatted_address": "123 East 54th Street, New York, NY",
      "formatted_phone_number": "(02) 9374 4000",
      "international_phone_number": "+61 2 9374 4000"
    }
  }
}
```

This endpoint creates a pet

<aside class="notice">
You must be signed in to create a place
</aside>

### HTTP Request

`POST https://roomeze.com/api/places`

### Attributes

Parameter                              | Type   | Description
-------------------------------------- | ------ | -----------
name                                   | String | The name of the place
floor                                  | String | The floor
street_number                          | String | The street number
route                                  | String | The street address
locality                               | String | The neighborhood or locality
administrative_area_level_2            | String | Usually the city name
administrative_area_level_2_short_name | String | Abbreviation of administrative_area_level_2
administrative_area_level_1            | String | Usually the state name
administrative_area_level_1_short_name | String | Abbreviation of administrative_area_level_1
country                                | String | The country
postal_code                            | String | The zip code or postal code
latitude                               | String | The latitude
longitude                              | String | The longitude
place_id                               | String | The unique place_id provided by Google Places Api
icon                                   | String | The icon
formatted_address                      | String | The formatted address
formatted_phone_number                 | String | The formatted phone number
international_phone_number             | String | the international phone number with country code