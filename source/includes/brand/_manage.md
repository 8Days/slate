# 가맹점 정보 / 상품 관리

## 1. 가맹점 리스트

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

#### Method
- **GET**

#### URL Schema
- `/api/admin/brand/list?page={page}&limit={limit}`

Request Query Param

| Name | Value | Description | Type |
| :--- | ----- | ----------- | :--: |
| `page` | 0 | 요청 페이지 | int |
| limit | 20 | 페이지당 개수 | int |

#### Response

| Name | Value | Description | Type |
| :--- | ----- | ----------- | :--: |
| title |  | 가맹점명 | string |
| is_open |  | 노출상태 | bool |
| category |  | 유형 | int |
| category_option |  | 유형2 | int |
| sido |  | 시도 | string |
| gungu |  | 군구 | string |
| owner_name |  | 사업자명 | string |
| total_goods |  | 상품수 | int |
| shop_no |  | 가맹점 번호 | int |