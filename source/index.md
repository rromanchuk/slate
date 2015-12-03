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

Welcome to the Tipper internal API.

# Authentication

> To authorize, use this code:


```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

> Make sure to replace `meowmeowmeow` with your API key.

Tipper uses an Authorization header composed from a base64 encoded string of `<twitterUserId>:<twitterAuthToken>`.

For method calls that require authentication the header should look like the following:

`Authorization: Basic <base64 encoded string>`

# Users

## Get current user


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

This returns the user object the authenticated user.

### HTTP Request

`GET https://api.trytipper.com/api/me/refresh`


## Get specific user

```shell
curl 'https://api.trytipper.com/api/users/5d13d184-7946-45ab-8e58-cbad3ae26c65' -H 'Pragma: no-cache' -H 'Origin: https://www.trytipper.com' -H 'Accept-Encoding: gzip, deflate, sdch' -H 'X-CSRF-Token: koP9psBYOKIQaiaPP+ns8B6ozSdeujQblJqse0PSKeVr/rLvfKHTfbTWA929bkISGKJhDVmZialCzJ054BDVKg==' -H 'Accept-Language: en,en-US;q=0.8' -H 'User-Agent: Mozilla/5.0 (iPhone; CPU iPhone OS 8_0 like Mac OS X) AppleWebKit/600.1.3 (KHTML, like Gecko) Version/8.0 Mobile/12A4345d Safari/600.1.4' -H 'Accept: application/json, text/javascript, */*; q=0.01' -H 'Cache-Control: no-cache' -H 'Authorization: Basic MTQwNzg4Mjc6MTQwNzg4MjctTkFDeDEzeUZZbkl3Q09GT1pIbDlKbDZuVFBTaGJtdzdiUGdlWGV2OTk=' -H 'Connection: keep-alive' -H 'Referer: https://www.trytipper.com/tip/9760059bfc51c1203d855e82c5c9c6868ee7e65aa6a50d6bf2ce914aa7f11cf0' --compressed
```

> The above command returns JSON structured like this:

```json
{  
   "user":{  
      "id":"5d13d184-7946-45ab-8e58-cbad3ae26c65",
      "bitcoinAddress":"14jnsfMhGGch7i3CQ5jynuMeU2ZdBnqo2P",
      "twitterUserId":"14764725",
      "twitterUsername":"msiegs",
      "profileImage":"http://pbs.twimg.com/profile_images/654353684491452416/QTiO4axY_normal.jpg",
      "userId":"5d13d184-7946-45ab-8e58-cbad3ae26c65",
      "bitcoinBalanceBtc":"0.01926"
   }
}
```

### HTTP Request

`GET https://api.trytipper.com/api/users/<ID>`

# Tips

## Get a specific tip

```shell
curl 'https://api.trytipper.com/api/tips/9760059bfc51c1203d855e82c5c9c6868ee7e65aa6a50d6bf2ce914aa7f11cf0' -X OPTIONS -H 'Pragma: no-cache' -H 'Access-Control-Request-Method: GET' -H 'Origin: https://www.trytipper.com' -H 'Accept-Encoding: gzip, deflate, sdch' -H 'Accept-Language: en,en-US;q=0.8' -H 'User-Agent: Mozilla/5.0 (iPhone; CPU iPhone OS 8_0 like Mac OS X) AppleWebKit/600.1.3 (KHTML, like Gecko) Version/8.0 Mobile/12A4345d Safari/600.1.4' -H 'Accept: */*' -H 'Cache-Control: no-cache' -H 'Referer: https://www.trytipper.com/tip/9760059bfc51c1203d855e82c5c9c6868ee7e65aa6a50d6bf2ce914aa7f11cf0' -H 'Connection: keep-alive' -H 'Access-Control-Request-Headers: accept, authorization, x-csrf-token' --compressed
```

> The above command returns JSON structured like this:

```json
{  
   "tip":{  
      "id":"9760059bfc51c1203d855e82c5c9c6868ee7e65aa6a50d6bf2ce914aa7f11cf0",
      "txid":"9760059bfc51c1203d855e82c5c9c6868ee7e65aa6a50d6bf2ce914aa7f11cf0",
      "fromTwitterId":"14764725",
      "toTwitterId":"15999465",
      "fromTwitterUsername":"msiegs",
      "toTwitterUsername":"ZackShapiro",
      "toTwitterProfileImage":"http://pbs.twimg.com/profile_images/378800000418101090/fc7162b0f1aa511f1f5c9261757cd8ae_normal.png",
      "fromTwitterProfileImage":"http://pbs.twimg.com/profile_images/654353684491452416/QTiO4axY_normal.jpg",
      "objectId":"672530671185866754",
      "transaction":"9760059bfc51c1203d855e82c5c9c6868ee7e65aa6a50d6bf2ce914aa7f11cf0",
      "fromUser":"5d13d184-7946-45ab-8e58-cbad3ae26c65",
      "toUser":"0bdf18e1-232c-4d97-a252-9fadaf7e6f30",
      "tippedAt":"2015-12-03T21:55:16+00:00"
   }
}
```

Given a bitcoin transaction id, this method returns a tipper tip representation. This object represents a 'like' action on the twitter platform.

### HTTP Request

`GET https://api.trytipper.com/api/tips/<ID>`

# Transactions

## Returns a bitcoin transaction

```shell
curl 'https://api.trytipper.com/api/transactions/9760059bfc51c1203d855e82c5c9c6868ee7e65aa6a50d6bf2ce914aa7f11cf0' -H 'Pragma: no-cache' -H 'Origin: https://www.trytipper.com' -H 'Accept-Encoding: gzip, deflate, sdch' -H 'X-CSRF-Token: koP9psBYOKIQaiaPP+ns8B6ozSdeujQblJqse0PSKeVr/rLvfKHTfbTWA929bkISGKJhDVmZialCzJ054BDVKg==' -H 'Accept-Language: en,en-US;q=0.8' -H 'User-Agent: Mozilla/5.0 (iPhone; CPU iPhone OS 8_0 like Mac OS X) AppleWebKit/600.1.3 (KHTML, like Gecko) Version/8.0 Mobile/12A4345d Safari/600.1.4' -H 'Accept: application/json, text/javascript, */*; q=0.01' -H 'Cache-Control: no-cache' -H 'Authorization: Basic MTQwNzg4Mjc6MTQwNzg4MjctTkFDeDEzeUZZbkl3Q09GT1pIbDlKbDZuVFBTaGJtdzdiUGdlWGV2OTk=' -H 'Connection: keep-alive' -H 'Referer: https://www.trytipper.com/tip/9760059bfc51c1203d855e82c5c9c6868ee7e65aa6a50d6bf2ce914aa7f11cf0' --compressed
```

> The above command returns JSON structured like this:

```json
{  
   "transaction":{  
      "id":"9760059bfc51c1203d855e82c5c9c6868ee7e65aa6a50d6bf2ce914aa7f11cf0",
      "amount":"0.0",
      "details":"[{\"account\":\"\",\"address\":\"14jnsfMhGGch7i3CQ5jynuMeU2ZdBnqo2P\",\"category\":\"send\",\"amount\":-0.01926,\"vout\":0,\"fee\":-1.0e-05},{\"account\":\"\",\"address\":\"19Y73qQJCd21PnjsB54g8UZ64DEu1F51Vg\",\"category\":\"send\",\"amount\":-0.0003,\"vout\":1,\"fee\":-1.0e-05},{\"account\":\"tipper_users\",\"address\":\"14jnsfMhGGch7i3CQ5jynuMeU2ZdBnqo2P\",\"category\":\"receive\",\"amount\":0.01926,\"vout\":0},{\"account\":\"tipper_users\",\"address\":\"19Y73qQJCd21PnjsB54g8UZ64DEu1F51Vg\",\"category\":\"receive\",\"amount\":0.0003,\"vout\":1}]",
      "fee":"-0.00001",
      "txid":"9760059bfc51c1203d855e82c5c9c6868ee7e65aa6a50d6bf2ce914aa7f11cf0",
      "tipAmount":"0.0003",
      "confirmations":"4.0",
      "tip":"9760059bfc51c1203d855e82c5c9c6868ee7e65aa6a50d6bf2ce914aa7f11cf0",
      "time":"2015-12-03T21:55:16+00:00",
      "relayedBy":"217.111.66.79",
      "size":"226.0",
      "inputs":"[{\"n\":0,\"value\":1957000,\"address\":\"14jnsfMhGGch7i3CQ5jynuMeU2ZdBnqo2P\",\"tx_index\":114227020,\"type\":0,\"script\":\"76a9142900241808a4ba9701de1b0f79992478ada65ee788ac\",\"script_sig\":\"483045022100dae6eefa69f59a99738ea252c0c3b7269b369a607bf7bd8f012356b4413323c10220239c26c53c32cef2ca5d2b5f522c78fcd30d16e9600733b16135010b0fcfe2c2012103bae072d232765ef25d9d6aeb9b83af212846f18f1b12d2d561261368562d6694\",\"sequence\":4294967295}]",
      "outputs":"[{\"n\":0,\"value\":1926000,\"address\":\"14jnsfMhGGch7i3CQ5jynuMeU2ZdBnqo2P\",\"tx_index\":114227136,\"script\":\"76a9142900241808a4ba9701de1b0f79992478ada65ee788ac\",\"spent\":false},{\"n\":1,\"value\":30000,\"address\":\"19Y73qQJCd21PnjsB54g8UZ64DEu1F51Vg\",\"tx_index\":114227136,\"script\":\"76a9145da2f34f4da310cd8c164810f59dd2988b0c127788ac\",\"spent\":false}]"
   }
}
```

Given a bitcoin transaction id, this method returns a modified representation of a bitcoin transaction on the blockchain.

### HTTP Request

`GET https://api.trytipper.com/api/transactions/<ID>`

