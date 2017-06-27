# 가맹점 정보 / 상품 관리



## 가맹점 리스트

> **/api/admin/brand/list?page={page}&limit={limit}**

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
          "email": "test_account@test.com",
          "owner_name": "사업자명",
          "title": "소로길",
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

### Method
- **GET**

### URL Schema
- `/api/admin/brand/list?page={page}&limit={limit}`

### Request Query Param

| Name | Value | Description | Type |
| :--- | ----- | ----------- | :--: |
| `page` | 0 | 요청 페이지 | int |
| `limit` | 20 | 페이지당 개수 | int |

### Response

| Name | Value | Description | Type |
| :--- | ----- | ----------- | :--: |
| `title` |  | 가맹점명 | string |
| `is_open` |  | 노출상태 | bool |
| `category` |  | 가맹점 유형1 | int |
| `category_option` |  | 가맹점 유형2 | int |
| `sido` |  | 시도 | string |
| `gungu` |  | 군구 | string |
| `owner_name` |  | 사업자명 | string |
| `total_goods` |  | 상품수 | int |
| `shop_no` |  | 가맹점 번호 | int |



## 매장 정보 확인

> **/api/admin/goods/{shop_no}/info/check**

```json
{
  "error": null,
  "result": {
    "data": {
      "is_goods_info": true,
      "category": 1,
      "category_option": 2,
      "shop_no": 25
    }
  },
  "timestamp": 1478598656,
  "success": true
}
```
<aside class="notice">
  매장 유형 및 매장 정보 입력 여부 확인
</aside>

### Method
- **GET**

### URL Schema
- `/api/admin/goods/{shop_no}/info/check`

### Request url Param
| Name | Value | Description | Type |
| :--- | ----- | ----------- | :--: |
| `shop_no` |  | 가맹점 번호 | int |

### Response
| Name | Value | Description | Type |
| :--- | ----- | ----------- | :--: |
| `shop_no` |  | 가맹점 번호 | int |
| `category` |  | 가맹점 유형 | int |
| `category_option` |  | 가맹점 유형 2 | int |
| `is_goods_info` |  | 가맹점 정보 입력 여부 | bool |



## 매장 정보 등록

> **/api/admin/goods/{shop_no}/info**

```json
{
  "error": null,
  "result": {
    "data": {
      "is_goods_info": true,
      "category": 1,
      "category_option": 2,
      "shop_no": 25
    }
  },
  "timestamp": 1478598656,
  "success": true
}
```

### Method
- **POST**

### URL Schema
- `/api/admin/goods/{shop_no}/info`

### Request url Param

| Name | Value | Description | Type |
| :--- | ----- | ----------- | :--: |
| `shop_no` |  | 가맹점 번호 | int |

### Request body

| Name | Value | Description | Type |
| :--- | ----- | ----------- | :--: |
| `title` |  | 가맹점명 | string |
| `category` |  | 가맹점 유형 1 | int |
| `category_option` |  | 가맹점 유형 2 | int |
| `is_open` |  | 영업상태 | bool |
| `sido` |  | 시도 | string |
| `gugun` |  | 구군 | string |
| `zipcode` |  | 우편번호 | int |
| `addr1` |  | 주소 | string |
| `addr2` |  | 상세주소 | string |
| `tel` |  | 전화번호 | string |
| `web` |  | 홈페이지 | string |

### Response

| Name | Value | Description | Type |
| :--- | ----- | ----------- | :--: |
| `is_goods_info` |  | 가맹점 정보 입력 여부 | bool |
| `category` |  | 가맹점 유형 1 | int |
| `category_option` |  | 가맹점 유형 2 | int |
| `shop_no` |  | 가맹점 번호 | int |



## 매장 부가 정보 등록

> **/api/admin/goods/{shop_no}/additional**

```json
{
  "error": null,
  "result": {
    "data": {
      "day_off": "연중 무휴",
      "info": "한줄 소개 입니다.",
      "companies": [
        {
          "text": "한화생명",
          "id": 1
        }, {
          "text": "한화손해보험",
          "id": 2
        }
      ],
      "options": [
        {
          "parking": true,
          "title": "주차"
        }, {
          "reservation": false,
          "title": "예약"
        }
      ],
      "run_time": [
        {
          "title": "주중",
          "start": "11:00",
          "end": "24:00",
          "break": [
            {
              "start": "14:00",
              "end": "15:00"
            }
          ]
        }, {
          "title": "주말",
          "start": "14:00",
          "end": "24:00",
          "break": []
        }
      ]
    }
  },
  "timestamp": 1478598656,
  "success": true
}
```

### Method
- **POST**

### URL Schema
- `/api/admin/goods/{shop_no}/additional`

### Request url Param
| Name | Value | Description | Type |
| :--- | ----- | ----------- | :--: |
| `shop_no` |  | 가맹점 번호 | int |

### Request body
| Name | Value | Description | Type |
| :--- | ----- | ----------- | :--: |
| `companies` |  | 노출 기업 | object |
| `run_time` |  | 영업시간 | object |
| `day_off` |  | 휴무일 정보 | string |
| `options` |  | 부가 정보 | object |
| `info` |  | 한줄 소개 | string |

### Response
| Name | Value | Description | Type |
| :--- | ----- | ----------- | :--: |
| `companies` |  | 노출 기업 | object |
| `run_time` |  | 영업시간 | object |
| `day_off` |  | 휴무일 정보 | string |
| `options` |  | 부가 정보 | object |
| `info` |  | 한줄 소개 | string |



## 가맹점 이미지 등록

> **/api/admin/goods/{shop_no}/image**

```json
{
  "error": null,
  "result": {
    "data": {
      "images": [{
        "image_idx": 1,
        "image_url": "https://www.8days.com/...",
        "image_no": 25
      }, {
        "image_idx": 2,
        "image_url": "https://www.8days.com/...",
        "image_no": 26
      }]
    }
  },
  "timestamp": 1478598656,
  "success": true
}
```

### Method
- **POST**

### URL Schema
- `/api/admin/goods/{shop_no}/image`

### Request url Param
| Name | Value | Description | Type |
| :--- | ----- | ----------- | :--: |
| `shop_no` |  | 가맹점 번호 | int |

### Request body
| Name | Value | Description | Type |
| :--- | ----- | ----------- | :--: |
| `images` |  | 가맹점 이미지 | object |
| `image` |  | 이미지 파일 | file |
| `image_url` |  | 이미지 주소 | string |
| `image_idx` |  | 이미지 인덱스 | int |

### Response
| Name | Value | Description | Type |
| :--- | ----- | ----------- | :--: |
| `images` |  | 가맹점 이미지 | object |
| `image_no` |  | 이미지 번호 | int |
| `image_url` |  | 이미지 주소 | string |
| `image_idx` |  | 이미지 인덱스 | int |



## 상품 분류 리스트

> **/api/admin/goods/category/{shop_no}/list**

```json
{
  "error": null,
  "result": {
    "data": {

    }
  },
  "timestamp": 1478598656,
  "success": true
}
```

### Method
- **GET**

### URL Schema
- `/api/admin/goods/category/{shop_no}/list`

### Request url Param

| Name | Value | Description | Type |
| :--- | ----- | ----------- | :--: |
| `shop_no` | 0 | 가맹점 번호 | int |

### Response

| Name | Value | Description | Type |
| :--- | ----- | ----------- | :--: |
| `categories` |  | 상품 분류 | object |
