---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
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

Welcome to the Kittn API! You can use our API to access Kittn API endpoints, which can get information on various cats, smittens, and breeds in our database.

We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/slatedocs/slate). Feel free to edit it and use it as a base for your own API's documentation.

# Authentication

> To authorize, use this code:

```ruby
require 'smittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import smittn

api = smittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const smittn = require('smittn');

let api = smittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Smittens

## Get All Smittens

```ruby
require 'smittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.smittens.get
```

```python
import smittn

api = smittn.authorize('meowmeowmeow')
api.smittens.get()
```

```shell
curl "http://example.com/api/smittens" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const smittn = require('smittn');

let api = smittn.authorize('meowmeowmeow');
let smittens = api.smittens.get();
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

This endpoint retrieves all smittens.

### HTTP Request

`GET http://example.com/api/smittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include smittens that have already been adopted.

<aside class="success">
Remember — a happy smitten is an authenticated smitten!
</aside>

## Get a Specific Smitten

```ruby
require 'smittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.smittens.get(2)
```

```python
import smittn

api = smittn.authorize('meowmeowmeow')
api.smittens.get(2)
```

```shell
curl "http://example.com/api/smittens/2" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const smittn = require('smittn');

let api = smittn.authorize('meowmeowmeow');
let max = api.smittens.get(2);
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

This endpoint retrieves a specific smitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/smittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the smitten to retrieve

## Delete a Specific Smitten

```ruby
require 'smittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.smittens.delete(2)
```

```python
import smittn

api = smittn.authorize('meowmeowmeow')
api.smittens.delete(2)
```

```shell
curl "http://example.com/api/smittens/2" \
  -X DELETE \
  -H "Authorization: meowmeowmeow"
```

```javascript
const smittn = require('smittn');

let api = smittn.authorize('meowmeowmeow');
let max = api.smittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific smitten.

### HTTP Request

`DELETE http://example.com/smittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the smitten to delete

