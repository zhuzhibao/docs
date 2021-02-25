# 搜索菜单类型

## 说明

* 功能说明：搜索系统中已有菜单类型接口

## 请求接口

#### 请求地址

* `[host]/api/administrator/menu-type/search`

#### 请求方式

* `POST`

#### 请求头Header

* `Authorization:Bearer {token}` token 为用户授权登陆Token
* `Accept:application/json`

#### 请求参数

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| page | fasle | integer | 页数 |
| pageSize | false | integer | 页码，默认20条数据每页 |
| display\_name | true | string | 菜单类型展示名称 |

## 请求示例

{% tabs %}
{% tab title="JavaScript" %}
```javascript
var axios = require('axios');
var data = JSON.stringify({"display_name":"后台"});

var config = {
  method: 'post',
  url: 'http://local.build-dream.cn/api/administrator/menu-type/search',
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
curl --location --request POST 'http://local.build-dream.cn/api/administrator/menu-type/search' \
--header 'Authorization: Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \
--header 'Cookie: PHPSESSID=171eee4ecf83ae527a5416c47ec3bf7f' \
--data-raw '{
    "display_name": "后台"
}'
```
{% endtab %}

{% tab title="HTTP" %}
```http
POST /api/administrator/menu-type/search HTTP/1.1
Host: local.build-dream.cn
Authorization: Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE
Accept: application/json
Content-Type: application/json
Cookie: PHPSESSID=171eee4ecf83ae527a5416c47ec3bf7f
Content-Length: 28

{
    "display_name": "后台"
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
| data | false | [Pagination](sou-suo-cai-dan-lei-xing.md#pagination-can-shu) | 响应内容 |
| msg | true | string | 响应描述 |

#### Pagination参数

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| current\_page | true | integer | 当前页数 |
| data | true | [MenuType](sou-suo-cai-dan-lei-xing.md#menutype-can-shu)\[\] | 角色数据 |
| per\_page | true | integer | 每页数据条数 |
| total | true | integer | 总数据量 |
| last\_page | true | integer | 总页数 |

#### MenuType参数

| **参数名** | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| id | true | integer | 主键ID |
| role\_type\_id | true | integer | 角色类型外键 |
| role\_type\_name | true | string | 绑定角色类型标示 |
| role\_type\_display\_name | true | integer | 绑定角色类型展示名称 |
| name | true | string | 菜单类型标示 |
| type | true | string | 类型，1 - APP菜单，0 - Web菜单 |
| display\_name | true | string | 菜单类型展示名称 |
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
                "id": 3,
                "role_type_id": 3,
                "role_type_name": "Business",
                "role_type_display_name": "企业用户",
                "name": "business-web",
                "type": 0,
                "display_name": "企业用户Web后台菜单",
                "created_at": "2020-11-23T07:47:51.000000Z",
                "updated_at": "2020-11-23T07:47:51.000000Z"
            },
            {
                "id": 2,
                "role_type_id": 2,
                "role_type_name": "Franchisee",
                "role_type_display_name": "加盟商",
                "name": "franchisee-web",
                "type": 0,
                "display_name": "加盟商Web后台菜单",
                "created_at": "2020-11-23T07:47:51.000000Z",
                "updated_at": "2020-11-23T07:47:51.000000Z"
            },
            {
                "id": 1,
                "role_type_id": 1,
                "role_type_name": "Administrator",
                "role_type_display_name": "管理员",
                "name": "administrator-web",
                "type": 0,
                "display_name": "管理员Web后台菜单",
                "created_at": "2020-11-23T07:47:50.000000Z",
                "updated_at": "2020-11-23T07:47:50.000000Z"
            }
        ],
        "first_page_url": "http://local.build-dream.cn/api/administrator/menu-type/search?page=1",
        "from": 1,
        "last_page": 1,
        "last_page_url": "http://local.build-dream.cn/api/administrator/menu-type/search?page=1",
        "links": [
            {
                "url": null,
                "label": "&laquo; 上一页",
                "active": false
            },
            {
                "url": "http://local.build-dream.cn/api/administrator/menu-type/search?page=1",
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
        "path": "http://local.build-dream.cn/api/administrator/menu-type/search",
        "per_page": 20,
        "prev_page_url": null,
        "to": 3,
        "total": 3
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



