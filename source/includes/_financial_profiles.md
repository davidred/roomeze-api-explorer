# Financial Profiles

## Accept credit check

```http
PATCH /api/financial_profiles/2/accept_credit_check HTTP/1.1
Accept: application/json
Host: roomeze.com
```
```http
HTTP/1.1 200 OK
Content-Type: application/json
Location: https://roomeze.com/api/financial_profiles/2

{
  "data": {
    "id": 2,
    "type": "financial_profile",
    "attributes": {
      "credit_check_accepted_at": "2019-02-13T02:55:58.659-05:00",
      "terms_accepted_at": "2019-02-13T02:55:58.659-05:00",
      "non_us_citizen": true
      "has_domestic_guarantor": true
      "willing_to_pay_additional_security": true
      "ssn": "111 11 1111",
      "street_name": "54th",
      "street_number": "123",
      "street_direction": "E",
      "street_type": "street",
      "city": "New York",
      "subregion": "New York",
      "zip_code": "10010",
      "bankruptcy": true,
      "eviction": true,
      "refusal_to_pay_rent": true,
      "convictions": true,
      "background_explanation": "Ipsum Lorem"
    },
    "relationships": {
      "permanent_address": {
        "data": {
          "type": "place",
          "id": "1"
        }
      }
    }
  }
}
```

This endpoint allows a user to authorize roomeze to run a credit check

### HTTP Request

`PATCH https://roomeze.com/api/financial_profiles/<ID>/accept_credit_check`

### URL Parameters

Parameter | Description
--------- | -----------
ID        | The ID of the financial profile to update

## Accept terms of service

```http
PATCH /api/financial_profiles/2/accept_terms HTTP/1.1
Accept: application/json
Host: roomeze.com
```
```http
HTTP/1.1 200 OK
Content-Type: application/json
Location: https://roomeze.com/api/financial_profiles/2

{
  "data": {
    "id": 2,
    "type": "financial_profile",
    "attributes": {
      "credit_check_accepted_at": "2019-02-13T02:55:58.659-05:00",
      "terms_accepted_at": "2019-02-13T02:55:58.659-05:00",
      "non_us_citizen": true
      "has_domestic_guarantor": true
      "willing_to_pay_additional_security": true
      "ssn": "111 11 1111",
      "street_name": "54th",
      "street_number": "123",
      "street_direction": "E",
      "street_type": "street",
      "city": "New York",
      "subregion": "New York",
      "zip_code": "10010",
      "bankruptcy": true,
      "eviction": true,
      "refusal_to_pay_rent": true,
      "convictions": true,
      "background_explanation": "Ipsum Lorem"
    },
    "relationships": {
      "permanent_address": {
        "data": {
          "type": "place",
          "id": "1"
        }
      }
    }
  }
}
```

This endpoint allows a user to authorize roomeze to accept payment

### HTTP Request

`PATCH https://roomeze.com/api/financial_profiles/<ID>/accept_terms`

### URL Parameters

Parameter | Description
--------- | -----------
ID        | The ID of the financial profile to update

## Update a Financial Profile

```http
PATCH /api/financial_profiles/2 HTTP/1.1
Accept: application/json
Host: roomeze.com

{
  "data": {
    "id": 2,
    "type": "financial_profile",
    "attributes": {
      "non_us_citizen": true
      "has_domestic_guarantor": true
      "willing_to_pay_additional_security": true
      "ssn": "111 11 1111",
      "street_name": "54th",
      "street_number": "123",
      "street_direction": "E",
      "street_type": "street",
      "city": "New York",
      "subregion": "New York",
      "zip_code": "10010",
      "bankruptcy": true,
      "eviction": true,
      "refusal_to_pay_rent": true,
      "convictions": true,
      "background_explanation": "Ipsum Lorem"
    },
    "relationships": {
      "permanent_address": {
        "data": {
          "type": "place",
          "id": "1"
        }
      }
    }
  }
}
```
```http
HTTP/1.1 200 OK
Content-Type: application/json
Location: https://roomeze.com/api/financial_profiles/2

{
  "data": {
    "id": 2,
    "type": "financial_profile",
    "attributes": {
      "non_us_citizen": true
      "has_domestic_guarantor": true
      "willing_to_pay_additional_security": true
      "ssn": "111 11 1111",
      "street_name": "54th",
      "street_number": "123",
      "street_direction": "E",
      "street_type": "street",
      "city": "New York",
      "subregion": "New York",
      "zip_code": "10010",
      "bankruptcy": true,
      "eviction": true,
      "refusal_to_pay_rent": true,
      "convictions": true,
      "background_explanation": "Ipsum Lorem"
    },
    "relationships": {
      "permanent_address": {
        "data": {
          "type": "place",
          "id": "1"
        }
      }
    }
  }
}
```

This endpoint updates a financial profile

### HTTP Request

`PATCH https://roomeze.com/api/financial_profiles/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID        | The ID of the financial profile to update

### Parameters

Parameter              | Type    | Description
---------------------- | ------- | -----------
non_us_citizen         | Boolean | Boolean indicating whether or not the user is a US citizen.
has_domestic_guarantor | Boolean | Whether or not the user has a guarantor who is living in the United States
willing_to_pay_additional_security | String  | Whether or not the user is willing to pay an additional security deposit
ssn                    | String  | The users social security number
street_name            | String  | The estimated monthly budget for an apartment
street_number          | String  | Whether or not the user has a cat
street_direction       | String  | The street direction of the users permanent address. This can be one of the following: ` `, `E`, `N`, `S`, `W`, `NE`, `NW`, `SE`, `SW`
street_type            | String  | The street type of the users permanent address. This can be one of the following: ` `, `Street`, `Alley`, `Avenue`, `Boulevard`, `Building`, `Center`, `Circle`, `Court`, `Crescent`, `Dale`, `Drive`, `Expressway`, `Freeway`, `Garden`, `Grove`, `Heights`, `Highway`, `Hill`, `Knoll`, `Lane`, `Mall`, `Oval`, `Park`, `Parkway`, `Path`, `Pike`, `Place`, `Plaza`, `Point`, `Road`, `Route`, `Row`, `Run`, `Rural Route`, `Square`, `Terrace`, `Throughway`, `Trail`, `Turnpike`, `Vaiduct`, `View`, `Walk`, `Way` 
city                   | String  | The city of the users permanent address
subregion              | String  | The subregion of the users permanent address
zip_code               | String  | The zip code of the users permanent address
bankruptcy             | Boolean | Whether or not the user has declared bankruptcy
eviction               | Boolean | Whether or not the user has been evicted
refusal_to_pay_rent    | Boolean | Whether or not the user has ever refused to pay rent
convictions            | Boolean | Whether or not the user has ever been convicted of a crime
background_explanation | String  | An explanation if any of the legal questions has been declared false

### Related Resources

Financial profiles can be updated with associated permanent addresses. These can be added the the `financial_profile` object under `relationships`.

#### Permanent Address

Parameter | Type    | Description
--------- | ------- | -----------
type      | String  | The type of related resource. The value should be `place`
id        | Integer | The id of the permanent address
