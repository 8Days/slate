# 가맹점 등록 / 관리



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

<aside class="notice">
	매장 정보 관리 리스트와 동일
</aside>

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
| :--- | ------------ | ----------- | :--: |
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

## 가맹점 계정 정보 등록

> **/api/admin/brand/account

```json
{
  "error": null,
  "result": {
    "data": {
      "contract_no": 1,
      "owner_name": "사업자명"
    }
  },
  "timestamp": 1478598656,
  "success": true
}
```
### Method
- **POST**

### URL Schema
- `/api/admin/brand/account`

### Request body
| Name | Value or key | Description | Type |
| :--- | ------------ | ----------- | :--: |
| `email` |  | 계정 | string |
| `password` |  | 계정 비밀번호 | string |
| `owner_name` |  | 사업자명 | string |

### Response
| Name | Value or key | Description | Type |
| :--- | ------------ | ----------- | :--: |
| `owner_name` |  | 사업자명 | string |
| `contract_no` |  | 계약 번호 | int |



## 가맹점 정보 등록

> **/api/admin/brand/info/contract_no={contract_no}

```json
{
  "error": null,
  "result": {
    "data": {
      "contract_no": 1,
    }
  },
  "timestamp": 1478598656,
  "success": true
}
```

### Method
- **POST**

### URL Schema
- `/api/admin/brand/info/contract_no={contract_no}`


### Request url Param
| Name | Value | Description | Type |
| :--- | ----- | ----------- | :--: |
| `contract_no` |  | 계약 번호 | int |

### Request body

| Object Name or key | Value or key | Description | Type |
| :----------------- | ------------ | ----------- | :--: |
| `title` |  | 가맹점명 | string |
| `licence_number` |  | 사업자 등록 번호 | int |
| `licence_img` |  | 사업자 등록증 이미지 | object |
|  | `file` | 사업자 등록증 이미지 파일 | file |
|  | `url` | 사업자 등록증 이미지 url | sting |
| `type` |  | 업종/업태 | string |
| `brand_category` |  | 가맹점 유형 | object |
|  | `no` | 가맹점 카테고리 번호 | int |
|  | `option` | 가맹점 카테고리 옵션 번호 | int |

### Response
| Object Name or key | Value or key | Description | Type |
| :----------------- | ------------ | ----------- | :--: |
| `contract_no` |  | 계약 번호 | int |




## 계약 정보 등록

> **/api/admin/brand/contract/contract_no={contract_no}

```json
{
  "error": null,
  "result": {
    "data": {
      "contract_no": 1,
    }
  },
  "timestamp": 1478598656,
  "success": true
}
```

### Method
- **POST**

### URL Schema
- `/api/admin/brand/info/contract_no={contract_no}`


### Request Query Param
| Name | Value | Description | Type |
| :--- | ----- | ----------- | :--: |
| `contract_no` |  | 계약 번호 | int |

### Request body

| Object name | Value or key | Description | Type |
| :----------------- | ------------ | ----------- | :--: |
| `state` |  | 계약 상태 | bool |
| `contract_start` |  | 계약 시작일 | string |
| `contract_end` |  | 계약 종료일 | string |
| `settle_date` |  | 정산일 | string |
| `bank_account_name` |  | 은행명 | string |
| `bank_title` |  | 명의자명 | string |
| `bank_account` |  | 계좌번호 | string |
| `bank_img` |  | 통장사본 | object |
|  | `file` | 사업자 등록증 이미지 파일 | file |
|  | `url` | 사업자 등록증 이미지 url | sting |
| `manager_no` |  | 담당자 | string |
| `contractor_no` |  | 계약자 | string |
| `charge` |  | 수수료 | int |
| `discount` |  | 상품 할인율 | int |
| `contract_file` |  | 계약서 | string |
|  | `file` | 사업자 등록증 이미지 파일 | file |
|  | `url` | 사업자 등록증 이미지 url | sting |

### Response
| Object Name | Value or key | Description | Type |
| :----------------- | ------------ | ----------- | :--: |
| `contract_no` |  | 계약 번호 | int |
