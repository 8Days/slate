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
          "is_open": false,
          "sido": "서울",
          "gungu": "강남구",
          "total_goods": "25",
          "brand_category": {
            "no": 1,
            "option": 1
          }
        },
        {
          "no": 2,
          "email": "test_account@test.com",
          "owner_name": "사업자명",
          "title": "베드렌",
          "charge": "5",
          "settle_date": "30",
          "state": true,
          "contract_date": "2017.05.15",
          "reg_date": "2017.05.16",
          "is_open": false,
          "sido": "서울",
          "gungu": "강남구",
          "total_goods": "40",
          "brand_category": {
            "no": 1,
            "option": 1
          }
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

| Name | Value or key | Description | Type |
| :--- | ----- | ----------- | :--: |
| `email` |  | 계정 | string |
| `charge` |  | 가맹점명 | string |
| `settle_date` |  | 정산일 | string |
| `state` |  | 계약완료 여부 | string |
| `is_open` |  | 노출상태 | bool |
| `brand_category` |  | 가맹점 유형 | object |
|  | `no` | 가맹점 카테고리 번호 | int |
|  | `option` | 가맹점 카테고리 옵션 번호 | int |
| `sido` |  | 시도 | string |
| `gungu` |  | 군구 | string |
| `owner_name` |  | 사업자명 | string |
| `total_goods` |  | 상품수 | int |
| `shop_no` |  | 가맹점 번호 | int |



## 매장 정보 확인

> **/api/admin/goods/info/check?shop_no={shop_no}**

```json
{
  "error": null,
  "result": {
    "data": {
      "is_goods_info": true,
      "brand_category": {
        "no": 1,
        "option": 1
      },
      "shop_no": 25,
      "title": "베드렌",
      "owner_name": "김대표",
      "licence_number": "123-43-12345",
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
- `/api/admin/goods/info/check/shop_no={shop_no}`

### Request Query Param
| Name | Value | Description | Type |
| :--- | ----- | ----------- | :--: |
| `shop_no` |  | 가맹점 번호 | int |

### Response
| Name | Value | Description | Type |
| :--- | ----- | ----------- | :--: |
| `shop_no` |  | 가맹점 번호 | int |
| `brand_category` |  | 가맹점 유형 | object |
|  | `no` | 가맹점 카테고리 번호 | int |
|  | `option` | 가맹점 카테고리 옵션 번호 | int |
| `is_goods_info` |  | 가맹점 정보 입력 여부 | bool |
| `title` |  | 가맹점명 | string |
| `owner_name` |  | 사업자명 | string |
| `licence_number` |  | 사업자번호 | string |



## 매장 정보 등록

> **/api/admin/goods/info**

```json
{
  "error": null,
  "result": {
    "data": {
      "is_goods_info": true,
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
- `/api/admin/goods/info`

### Request body

| Name | Value | Description | Type |
| :--- | ----- | ----------- | :--: |
| `shop_no` |  | 가맹점 번호 | int |
| `title` |  | 가맹점명 | string |
| `brand_category` |  | 가맹점 유형 | object |
|  | `no` | 가맹점 카테고리 번호 | int |
|  | `option` | 가맹점 카테고리 옵션 번호 | int |
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
| `shop_no` |  | 가맹점 번호 | int |



## 매장 부가 정보 등록

> **/api/admin/goods/additional**

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
- `/api/admin/goods/additional`


### Request body
| Name | Value | Description | Type |
| :--- | ----- | ----------- | :--: |
| `shop_no` |  | 가맹점 번호 | int |
| `companies` |  | 노출 기업 | object |
| `run_time` |  | 영업시간 | object |
| `day_off` |  | 휴무일 정보 | string |
| `options` |  | 부가 정보 | object |
| `info` |  | 한줄 소개 | string |

### Response
| Name | Value | Description | Type |
| :--- | ----- | ----------- | :--: |
| `shop_no` |  | 가맹점 번호 | int |


## 가맹점 이미지 등록

> **/api/admin/goods/image**

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
- `/api/admin/goods/image`

### Request body
| Name | Value | Description | Type |
| :--- | ----- | ----------- | :--: |
| `shop_no` |  | 가맹점 번호 | int |
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



## 상품 리스트

> **/api/admin/goods/list/shop_no={shop_no}**

```json
{
  "error": null,
  "result": {
    "data": {
      "goods_category": [
        {
          "index": 1,
          "titls": "음료",
          "category_no": 1
        }
      ],
      "goods": [
        {
          "index": 1,
          "goods_no": 1,
          "title": "콜라",
          "recommendation": true,
          "category": "음료",
          "price": 3000,
          "discount_rate": 5,
          "discount_mount": 150,
          "benefit_price": 2850
        }
      ]
    }
  },
  "timestamp": 1478598656,
  "success": true
}
```

### Method
- **GET**

### URL Schema
- `/api/admin/goods/list/shop_no={shop_no}`

### Request url Param

| Name | Value | Description | Type |
| :--- | ----- | ----------- | :--: |
| `shop_no` | 0 | 가맹점 번호 | int |
### Response

| Name | key | Description | Type |
| :--- | --- | ----------- | :--: |
| `goods_category` |  | 상품 분류 | object |
|  | `index` | 상품 분류 인덱스 | int |
|  | `title` | 상품 분류 이름 | string |
|  | `category_no` | 상품 분류 번호  | int |
| `goods` |  | 상품 목록 | object |
|  | `index` | 상품 인덱스 | int |
|  | `goods_no` | 상품 번호 | int |
|  | `title` | 상품명 | string |
|  | `recommendation` | 추천상품 | bool |
|  | `category` | 분류 | string |
|  | `price` | 정상가 | int |
|  | `discount_rate` | 할인율 | int |
|  | `discount_mount` | 할인액 | int |
|  | `benefit_price` | 할인가 | int |
