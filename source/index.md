---
title: API Reference

language_tabs:
  - shell
  - ruby

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='http://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Kittn API! You can use our API to access Kittn API endpoints, which can get information on various cats, kittens, and breeds in our database.

We have language bindings in Shell, Ruby, and Python! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](http://github.com/tripit/slate). Feel free to edit it and use it as a base for your own API's documentation.

# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

> Make sure to replace `meowmeowmeow` with your API key.

Tipper uses an Authorization header composed from a base64 encoded string of `<twitterUserId>:<twitterAuthToken>`.

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: Basic <base64 encoded string>`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Me

## Get current user

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```


```shell
curl 'https://api.trytipper.com/api/me/refresh' -H 'Pragma: no-cache' -H 'Origin: https://www.trytipper.com' -H 'Accept-Encoding: gzip, deflate, sdch' -H 'X-CSRF-Token: dD+UTRUvo24Bz93XoG4f+SUC3V3j+xvlEzBNX84NsEyNQtsEqdZIsaVz+IUi6bEbIwhxd+TYplfFZnwdbc9Mgw==' -H 'Accept-Language: en,en-US;q=0.8' -H 'User-Agent: Mozilla/5.0 (iPhone; CPU iPhone OS 8_0 like Mac OS X) AppleWebKit/600.1.3 (KHTML, like Gecko) Version/8.0 Mobile/12A4345d Safari/600.1.4' -H 'Accept: application/json, text/javascript, */*; q=0.01' -H 'Cache-Control: no-cache' -H 'Authorization: Basic MTQwNzg4Mjc6MTQwNzg4MjctTkFDeDEzeUZZbkl3Q09GT1pIbDlKbDZuVFBTaGJtdzdiUGdlWGV2OTk=' -H 'Connection: keep-alive' -H 'Referer: https://www.trytipper.com/' --compressed
```

> The above command returns JSON structured like this:

```json
{  
   "me":{  
      "id":"1e6b27ea-3570-4bd5-854e-af7dc5e1bed8",
      "bitcoinAddress":"1G8f1EeFKq1ueXCSHJ8zwoZ6YBCrnCpaAP",
      "twitterUserId":"14078827",
      "twitterUsername":"rromanchuk",
      "profileImage":"http://pbs.twimg.com/profile_images/1779344853/_DSC5171-r_normal.jpg",
      "userId":"1e6b27ea-3570-4bd5-854e-af7dc5e1bed8",
      "bitcoinBalanceBtc":"0.04055",
      "isAutomaticTippingEnabled":true
   }
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

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Isis",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">If you're not using an administrator API key, note that some kittens will return 403 Forbidden if they are hidden for admins only.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

