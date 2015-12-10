---
title: API Reference

language_tabs:
  - shell

toc_footers:
  - <a href='http://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Internal API documentation for integralvision.com


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

<aside class="notice">
Authentication not required
</aside>

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
TBD

```

> The above command returns JSON structured like this:

```json
unkown
```

This endpoint returns the user object and token on successful authentication.

### HTTP Request

`POST https://50.16.201.24/pmivapi/v1/projectlist`

### Query Parameters

Parameter | Default | Description | Required
--------- | ------- | ----------- | --------
token | n/a | The authenticated user's token | true
guid | n/a | The user's unique id | true


# Diaries

## Project diaries

```shell
TBD

```

> The above command returns JSON structured like this:

```json
TBD
```

### HTTP Request

`POST https://50.16.201.24/pmivapi/v1/ddr/ddrlist`


### Query Parameters

Parameter | Default | Description | Required
--------- | ------- | ----------- | --------
projid | n/a | The project id | true
token | n/a | The authenticated user's token | true
guid | n/a | The user's unique id | true




