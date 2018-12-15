# Pagination

The Roomeze API accepts the following pagination parameters for most index routes.

### Example HTTP Request

`GET https://roomeze.com/api/properties?page=3&per_page=100`

### URL Parameters

Parameter | Description
--------- | -----------
page      | The page number being requested
per_page  | The number of results to return per page (25 by default)
