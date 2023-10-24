---
title: API Reference

language_tabs: # must be one of https://github.com/rouge-ruby/rouge/wiki/List-of-supported-languages-and-lexers
  - shell
  - ruby
  - python
  - javascript
  - csharp

toc_footers:
  - <a href='#'>This is a IQPro documentation site</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the Kittn API
---

# Introduction

Welcome to BASYS IQPro Documentation built using slate. Here Business can find and use this tool for thier operations.

We have language bindings in Shell, Ruby, Python, JavaScript and Csharp! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/slatedocs/slate). Feel free to edit it and use it as a base for your own API's documentation.

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
curl "api_endpoint_here" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> 
IQPro uses tokens to validate and to process a request.
Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: Tokenex`

<aside class="notice">
You must replace <code>tokenex</code> with your new Tokenex key for every 45minutes.
</aside>

# Customer

## Get Customer

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
curl "http://example.com/api/kittens" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
{
  "statusCode": "Continue",
  "statusDetails": [
    "string"
  ],
  "data": {
    "name": "string",
    "description": "string",
    "createdDateTime": "2023-10-23T20:05:51.848Z",
    "modifiedDateTime": "2023-10-23T20:05:51.848Z",
    "sourceReferenceId": "string",
    "addresses": [
      {
        "isPhysical": true,
        "isShipping": true,
        "isBilling": true,
        "firstName": "string",
        "lastName": "string",
        "company": "string",
        "email": "string",
        "phone": "string",
        "fax": "string",
        "addressLine1": "string",
        "addressLine2": "string",
        "city": "string",
        "state": "string",
        "postalCode": "string",
        "country": "string",
        "sourceReferenceId": "string",
        "customerAddressId": "3fa85f64-5717-4562-b3fc-2c963f66afa6"
      }
    ],
    "paymentMethods": [
      {
        "ach": {
          "achId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
          "maskedAccount": "string",
          "accountType": "Checking",
          "secCode": "PPD",
          "token": "string",
          "sourceReferenceId": "string"
        },
        "card": {
          "cardId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
          "maskedCard": "string",
          "token": "string",
          "cardType": "Visa",
          "expirationDate": "string",
          "sourceReferenceId": "string"
        },
        "isDefault": true,
        "paymentMethodId": "3fa85f64-5717-4562-b3fc-2c963f66afa6"
      }
    ],
    "customFieldEntries": [
      {
        "customFieldId": 0,
        "name": "string",
        "value": "string",
        "modifiedByUserId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
        "modifiedDateTime": "2023-10-23T20:05:51.849Z",
        "type": "string",
        "customFieldCategoryName": "string",
        "customFieldCategoryId": 0,
        "dataType": "string"
      }
    ],
    "statistics": {
      "addressesCount": 0,
      "paymentMethodsCount": 0
    },
    "customerId": "3fa85f64-5717-4562-b3fc-2c963f66afa6"
  },
  "byteData": "string",
  "contentType": "string"
}
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
curl "http://example.com/api/kittens/2" \
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
curl "http://example.com/api/kittens/2" \
  -X DELETE \
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

