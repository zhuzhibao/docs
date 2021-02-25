# 公司角色列表

## 说明

* 功能说明：获取系统中所有公司角色列表接口

## 请求接口

#### 请求地址

* `[host]/api/administrator/company/{companyId}/role`
* `companyId` 为 Company ID

#### 请求方式

* `GET`

#### 请求头Header

* `Authorization:Bearer {token}` token 为用户授权登陆Token
* `Accept:application/json`

#### 请求参数

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| page | false | integer | 页数 |
| pageSize | false | integer | 页码，默认20条数据每页 |
| id | false | integer | 角色主键ID |
| name | false | string | 模糊搜索角色名称 |

## 请求示例

{% tabs %}
{% tab title="JavaScript" %}
```javascript
var axios = require('axios');
var data = JSON.stringify({"paeg":1,"pageSize":5});

var config = {
  method: 'get',
  url: 'http://local.build-dream.cn/api/administrator/company/1/role',
  headers: { 
    'Authorization': 'Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE', 
    'Accept': 'application/json', 
    'Content-Type': 'application/json', 
    'Cookie': 'PHPSESSID=171eee4ecf83ae527a5416c47ec3bf7f'
  },
  data : data
};

axios(config)
.then(function (response) {
  console.log(JSON.stringify(response.data));
})
.catch(function (error) {
  console.log(error);
});

```
{% endtab %}

{% tab title="cURL" %}
```bash
curl --location --request GET 'http://local.build-dream.cn/api/administrator/company/1/role' \
--header 'Authorization: Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \
--header 'Cookie: PHPSESSID=171eee4ecf83ae527a5416c47ec3bf7f' \
--data-raw '{
    "paeg": 1,
    "pageSize": 5
}'
```
{% endtab %}

{% tab title="HTTP" %}
```http
GET /api/administrator/company/1/role HTTP/1.1
Host: local.build-dream.cn
Authorization: Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE
Accept: application/json
Content-Type: application/json
Cookie: PHPSESSID=171eee4ecf83ae527a5416c47ec3bf7f
Content-Length: 36

{
    "paeg": 1,
    "pageSize": 5
}
```
{% endtab %}
{% endtabs %}

## 响应接口

#### 响应Header

* `Content-Type:application/json`

#### 响应参数

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| code | true | integer | HTTP响应代码, 成功返回200 |
| data | false | [Pagination](../../jian-li/list.md#pagination-can-shu) | 响应内容 |
| msg | true | string | 响应描述 |

#### Pagination参数

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| current\_page | true | integer | 当前页数 |
| data | true | [CompanyRole](gong-si-jiao-se-lie-biao.md#companyrole-can-shu)\[\] | 角色数据 |
| per\_page | true | integer | 每页数据条数 |
| total | true | integer | 总数据量 |
| last\_page | true | integer | 总页数 |

#### CompanyRole参数

| **参数名** | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| id | true | integer | 主键ID |
| role\_type\_id | true | integer | 角色类型外键 |
| role\_type\_name | true | string | 角色类型标识 |
| role\_type\_display\_name | true | integer | 角色类型展示名称 |
| company\_id | true | string | 公司外键 |
| display\_name | true | string\[\] | 角色展示名称 |
| name | true | string | 角色标识 |
| guard\_name | true | integer | 守卫标识 |
| created\_at | true | string | 创建时间 |
| updated\_at | true | string | 更新时间 |

## 响应示例

{% tabs %}
{% tab title="正确响应" %}
```javascript
{
    "code": 200,
    "data": {
        "current_page": 1,
        "data": [
            {
                "id": 45,
                "role_type_id": 4,
                "role_type_name": "Consumer",
                "role_type_display_name": "个人用户",
                "company_id": 1,
                "display_name": "个人用户",
                "name": "Consumer",
                "guard_name": "api",
                "created_at": "2020-10-19T07:48:16.000000Z",
                "updated_at": "2020-10-19T07:48:16.000000Z"
            },
            {
                "id": 44,
                "role_type_id": 3,
                "role_type_name": "Business",
                "role_type_display_name": "企业用户",
                "company_id": 1,
                "display_name": "企业用户",
                "name": "Business",
                "guard_name": "api",
                "created_at": "2020-10-19T07:48:10.000000Z",
                "updated_at": "2020-10-19T07:48:10.000000Z"
            },
            {
                "id": 43,
                "role_type_id": 2,
                "role_type_name": "Franchisee",
                "role_type_display_name": "加盟商",
                "company_id": 1,
                "display_name": "加盟商",
                "name": "Franchisee",
                "guard_name": "api",
                "created_at": "2020-10-19T07:48:06.000000Z",
                "updated_at": "2020-10-19T07:48:06.000000Z"
            },
            {
                "id": 42,
                "role_type_id": 1,
                "role_type_name": "Administrator",
                "role_type_display_name": "管理员",
                "company_id": 1,
                "display_name": "管理员",
                "name": "Administrator",
                "guard_name": "api",
                "created_at": "2020-10-19T07:47:59.000000Z",
                "updated_at": "2020-10-19T07:47:59.000000Z"
            }
        ],
        "first_page_url": "http://local.build-dream.cn/api/administrator/company/1/role?page=1",
        "from": 1,
        "last_page": 1,
        "last_page_url": "http://local.build-dream.cn/api/administrator/company/1/role?page=1",
        "links": [
            {
                "url": null,
                "label": "&laquo; 上一页",
                "active": false
            },
            {
                "url": "http://local.build-dream.cn/api/administrator/company/1/role?page=1",
                "label": 1,
                "active": true
            },
            {
                "url": null,
                "label": "下一页 &raquo;",
                "active": false
            }
        ],
        "next_page_url": null,
        "path": "http://local.build-dream.cn/api/administrator/company/1/role",
        "per_page": 5,
        "prev_page_url": null,
        "to": 4,
        "total": 4
    },
    "msg": "success"
}
```
{% endtab %}

{% tab title="认证失败响应" %}
```javascript
{
    "code": 401,
    "msg": "请求未认证"
}
```
{% endtab %}
{% endtabs %}

