---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

You can use our API to access Suffolk CostLab Telemetry API endpoints, which can get information on project, estimates, line items and session data.

You can view code examples in the dark area to the right.

# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl --header "Content-Type: application/json" \
  --request POST \
  --data '{"password":"WhereIsNavarro"}' \
  "https://statscostlab-api.cleverbuild.biz/api/account/login"
```

> It will return:

```json
{
    "user": {
        "username": "User",
        "firstName": "Default",
        "lastName": "User",
        "email": "user@costlab.com",
        "id": "269bcc50-ab51-446b-b8fd-4d1f22ada0a9"
    },
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6IlVzZXIiLCJmaXJzdE5hbWUiOiJEZWZhdWx0IiwibGFzdE5hbWUiOiJVc2VyIiwiZW1haWwiOiJ1c2VyQGNvc3RsYWIuY29tIiwiaWQiOiIyNjliY2M1MC1hYjUxLTQ0NmItYjhmZC00ZDFmMjJhZGEwYTkiLCJhdXRoZW50aWNhdGVkIjp0cnVlLCJpYXQiOjE1MzgxNTk4MTN9.CjjaPqmVdwlLCbg_WV0ycY3KN4ShWcXsAoM1BxwNLOs",
    "authenticated": true,
    "twofactor": null,
    "twofactorPhone": ""
}
```

We use a default password to authenticate: "WhereIsNavarro"

We expect for the returned token to be included in all API requests to the server in a header that looks like the following:

`Authorization: Bearer#Token`

<aside class="notice">
You must replace <code>#Token</code> with the returned token.
</aside>

# Projects

## Get Projects total count

```shell
curl "https://statscostlab-api.cleverbuild.biz/api/projects/total"
  -H "Authorization: Bearer#Token"
```

> The above command returns JSON structured like this:

```json
{
    "total": "78"
}
```

This endpoint retrieves the total number of projects.

### HTTP Request

`GET https://statscostlab-api.cleverbuild.biz/api/projects/total`

## Get Projects summary by date and filter type

```shell
curl "https://statscostlab-api.cleverbuild.biz/api/projects/summary?startDate=2018-07-30&endDate=2018-09-28&filterType=regions"
  -H "Authorization: Bearer#Token"
```

> The above command returns JSON structured like this:

```json
{
    "records": [
        [
            "Boston",
            "13"
        ],
        [
            "Miami",
            "1"
        ],
        [
            "San Francisco",
            "2"
        ]
    ]
}
```

This endpoint gets a summary of projects data.

### HTTP Request

`GET https://statscostlab-api.cleverbuild.biz/api/projects/summary`

### Query Parameters

Parameter  | Required | Description
---------  | ------- | -----------
startDate  | true    | Date you want to start filtering your data.
endDate    | true    | Date you want to stop filtering your data.
filterType | true    | Attribute you want to use to group your data. Available options are: 'regions', 'sectors', 'owners'

# Estimates

## Get Estimates total count

```shell
curl "https://statscostlab-api.cleverbuild.biz/api/estimates/total"
  -H "Authorization: Bearer#Token"
```

> The above command returns JSON structured like this:

```json
{
    "total": "78"
}
```

This endpoint retrieves the total number of estimates.

### HTTP Request

`GET https://statscostlab-api.cleverbuild.biz/api/estimates/total`

## Get Estimates summary by date and filter type

```shell
curl "https://statscostlab-api.cleverbuild.biz/api/estimates/summary?startDate=2018-07-30&endDate=2018-09-28&filterType=regions"
  -H "Authorization: Bearer#Token"
```

> The above command returns JSON structured like this:

```json
{
    "records": [
        [
            "Boston",
            "22"
        ],
        [
            "Miami",
            "2"
        ],
        [
            "San Francisco",
            "2"
        ]
    ]
}
```

This endpoint gets a summary of estimates data.

### HTTP Request

`GET https://statscostlab-api.cleverbuild.biz/api/estimates/summary`

### Query Parameters

Parameter  | Required | Description
---------  | ------- | -----------
startDate  | true    | Date you want to start filtering your data.
endDate    | true    | Date you want to stop filtering your data.
filterType | true    | Attribute you want to use to group your data. Available options are: 'regions', 'sectors', 'owners', 'highlevels'

# Line Items

## Get Line Items total count

```shell
curl "https://statscostlab-api.cleverbuild.biz/api/line_items/total"
  -H "Authorization: Bearer#Token"
```

> The above command returns JSON structured like this:

```json
{
    "total": "78"
}
```

This endpoint retrieves the total number of line items.

### HTTP Request

`GET https://statscostlab-api.cleverbuild.biz/api/line_items/total`

## Get Line Items summary by date and filter type

```shell
curl "https://statscostlab-api.cleverbuild.biz/api/line_items/summary?startDate=2018-07-30&endDate=2018-09-28&filterType=regions"
  -H "Authorization: Bearer#Token"
```

> The above command returns JSON structured like this:

```json
{
    "records": [
        [
            "Boston",
            "1841"
        ],
        [
            "Miami",
            "423"
        ],
        [
            "San Francisco",
            "435"
        ]
    ]
}
```

This endpoint gets a summary of line items data.

### HTTP Request

`GET https://statscostlab-api.cleverbuild.biz/api/line_items/summary`

### Query Parameters

Parameter  | Required | Description
---------  | ------- | -----------
startDate  | true    | Date you want to start filtering your data.
endDate    | true    | Date you want to stop filtering your data.
filterType | true    | Attribute you want to use to group your data. Available options are: 'regions', 'sectors', 'owners'

# High-level Assemblies

## Get High-level Assemblies total count

```shell
curl "https://statscostlab-api.cleverbuild.biz/api/high_level_assemblies/total"
  -H "Authorization: Bearer#Token"
```

> The above command returns JSON structured like this:

```json
{
    "total": "78"
}
```

This endpoint retrieves the total number of high-level assemblies.

### HTTP Request

`GET https://statscostlab-api.cleverbuild.biz/api/high_level_assemblies/total`

## Get Line Items summary by date and filter type

```shell
curl "https://statscostlab-api.cleverbuild.biz/api/high_level_assemblies/summary?startDate=2018-07-30&endDate=2018-09-28&filterType=regions"
  -H "Authorization: Bearer#Token"
```

> The above command returns JSON structured like this:

```json
{
    "records": [
        [
            "Miami",
            "1"
        ],
        [
            "San Francisco",
            "1"
        ],
        [
            "Boston",
            "6"
        ]
    ]
}
```

This endpoint gets a summary of high-level assemblies data.

### HTTP Request

`GET https://statscostlab-api.cleverbuild.biz/api/high_level_assemblies/summary`

### Query Parameters

Parameter  | Required | Description
---------  | ------- | -----------
startDate  | true    | Date you want to start filtering your data.
endDate    | true    | Date you want to stop filtering your data.
filterType | true    | Attribute you want to use to group your data. Available options are: 'regions', 'sectors', 'owners'

# Sessions

## Get Sessions total count by event

```shell
curl "https://statscostlab-api.cleverbuild.biz/api/sessions/total?filterType=login"
  -H "Authorization: Bearer#Token"
```

> The above command returns JSON structured like this:

```json
{
    "total": 35
}
```

This endpoint retrieves the total number of high-level assemblies.

### HTTP Request

`GET https://statscostlab-api.cleverbuild.biz/api/sessions/total`

### Query Parameters

Parameter  | Required | Description
---------  | ------- | -----------
filterType | true    | Attribute you want to use to group your data. Available option is: 'login'

## Get Line Items summary by date and filter type

```shell
curl "https://statscostlab-api.cleverbuild.biz/api/sessions/summary?startDate=2018-09-15&endDate=2018-09-28&filterType=login"
  -H "Authorization: Bearer#Token"
```

> The above command returns JSON structured like this:

```json
{
    "records": [
        [
            "2018-09-15",
            0
        ],
        [
            "2018-09-16",
            0
        ],
        [
            "2018-09-17",
            0
        ],
        [
            "2018-09-18",
            0
        ],
        [
            "2018-09-19",
            0
        ],
        [
            "2018-09-20",
            0
        ],
        [
            "2018-09-21",
            0
        ],
        [
            "2018-09-22",
            0
        ],
        [
            "2018-09-23",
            0
        ],
        [
            "2018-09-24",
            0
        ],
        [
            "2018-09-25",
            0
        ],
        [
            "2018-09-26",
            0
        ],
        [
            "2018-09-27",
            12
        ],
        [
            "2018-09-28",
            25
        ]
    ]
}
```

This endpoint gets a summary of sessions data by day.

### HTTP Request

`GET https://statscostlab-api.cleverbuild.biz/api/sessions/summary`

### Query Parameters

Parameter  | Required | Description
---------  | ------- | -----------
startDate  | true    | Date you want to start filtering your data.
endDate    | true    | Date you want to stop filtering your data.
filterType | true    | Attribute you want to use to group your data. Available options are: 'regions', 'sectors', 'owners'
