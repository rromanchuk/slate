---
title: API Reference

language_tabs:
  - shell

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


# Users

## Login


```shell
curl -i \
-X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-H "Accept-Encoding: gzip;q=1.0,compress;q=0.5" \
-H "User-Agent: DailyDiary/com.integralvision.DailyDiary (12; OS Version 9.2 (Build 13C75))" \
-H "Accept-Language: en-US;q=1.0" \
-d "{\"password\":\"jlm@3176\",\"username\":\"jlm\"}" \
"https://50.16.201.24/pmivapi/v1/authenticate"

```

> The above command returns JSON structured like this:

```json
{
    "message":"Login successfully.",
    "token":"6e6f3734bf67f9f1ca00508abff7837df4efc331",
    "user":{
        "login":"jlm",
        "email":"jhuang@integralvision.com",
        "who":"jhuang"
    },
    "success":true
}
```

This endpoint returns the user object and token on successful authentication.

### HTTP Request

`POST https://50.16.201.24/pmivapi/v1/authenticate`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
password | n/a | Login password
username | n/a | Login username


# Projects

## Get the projectlist 


```shell
curl -i \
-X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-H "Accept-Encoding: gzip;q=1.0,compress;q=0.5" \
-H "User-Agent: DailyDiary/com.integralvision.DailyDiary (12; OS Version 9.2 (Build 13C75))" \
-H "Accept-Language: en-US;q=1.0" \
-d "{\"password\":\"jlm@3176\",\"username\":\"jlm\"}" \
"https://50.16.201.24/pmivapi/v1/authenticate"

```

> The above command returns JSON structured like this:

```json
unkown
```

This endpoint returns the user object and token on successful authentication.

### HTTP Request

`POST https://50.16.201.24/pmivapi/v1/authenticate`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
password | n/a | Login password
username | n/a | Login username



