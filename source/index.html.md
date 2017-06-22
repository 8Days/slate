---
title: API Reference

language_tabs:
  - json

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - brandManage
  - errors

search: true
---

# Introduction

단지 테스트  
오웬 테스트
Welcome to the Kittn API! You can use our API to access Kittn API endpoints, which can get information on various cats, kittens, and breeds in our database.

We have language bindings in Shell, Ruby, and Python! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/tripit/slate). Feel free to edit it and use it as a base for your own API's documentation.

# 가맹점 상품 관리

## 가맹점 리스트

```shell
# With shell, you can just pass the correct header with each request
curl "api.8days.com/v1/api/admin/brand/list?page={page}&limit{limit}"
```

```json
{
  "error": null,
  "result": {
    "data": {
      "brands": [
        {
          "no": 1,
          "email": "test_account@test.com",
          "owner_name": "사업자명",
          "title": "베드렌",
          "charge": "5",
          "settle_date": "30",
          "state": true,
          "contract_date": "2017.05.15",
          "reg_date": "2017.05.16",
        }, {
          "no": 2,
          "email": "동인동",
          "owner_name": "사업자명",
          "title": "",
          "charge": "3",
          "settle_date": "30",
          "state": true,
          "contract_date": "2017.05.26",
          "reg_date": "2017.05.27",
        },
      ],
      "total": 12,
      "page": 0,
      "limit": 20,
    }
  },
  "timestamp": 1478598656,
  "success": true
}
```

### HTTP Request

`GET http://api.the8days.com/api/admin/brand/list?page={page}&limit={limit}`


### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
page | 0 | int, 요청 페이지
limit | 20 | int, 페이지당 개수

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>


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
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>
