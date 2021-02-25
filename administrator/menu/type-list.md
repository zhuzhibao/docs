# 菜单类型列表

## 说明

* 功能说明：获取系统中所有菜单类型列表接口

## 请求接口

#### 请求地址

* `[host]/api/administrator/menu-type`

#### 请求方式

* `GET`

#### 请求头Header

* `Authorization:Bearer {token}` token 为用户授权登陆Token
* `Accept:application/json`

#### 请求参数

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |


## 请求示例

{% tabs %}
{% tab title="JavaScript" %}
```javascript
var axios = require('axios');
var data = '';

var config = {
  method: 'get',
  url: 'http://local.build-dream.cn/api/administrator/menu-type',
  headers: { 
    'Authorization': 'Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE', 
    'Accept': 'application/json', 
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
curl --location --request GET 'http://local.build-dream.cn/api/administrator/menu-type' \
--header 'Authorization: Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE' \
--header 'Accept: application/json' \
--header 'Cookie: PHPSESSID=171eee4ecf83ae527a5416c47ec3bf7f' \
--data-raw ''
```
{% endtab %}

{% tab title="HTTP" %}
```http
GET /api/administrator/menu-type HTTP/1.1
Host: local.build-dream.cn
Authorization: Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE
Accept: application/json
Cookie: PHPSESSID=171eee4ecf83ae527a5416c47ec3bf7f
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
| data | false | [MenuType](type-list.md#menutype-can-shu)\[\] | 响应内容 |
| msg | true | string | 响应描述 |

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
    "data": [
        {
            "id": 10,
            "role_type_id": 3,
            "role_type_name": "Business",
            "role_type_display_name": "企业用户",
            "name": "business-app-manager",
            "type": 1,
            "display_name": "企业用户企业管理相关菜单",
            "created_at": "2020-11-23T07:47:51.000000Z",
            "updated_at": "2020-11-23T07:47:51.000000Z"
        },
        {
            "id": 9,
            "role_type_id": 3,
            "role_type_name": "Business",
            "role_type_display_name": "企业用户",
            "name": "business-app-company",
            "type": 1,
            "display_name": "企业用户App企业相关菜单",
            "created_at": "2020-11-23T07:47:51.000000Z",
            "updated_at": "2020-11-23T07:47:51.000000Z"
        },
        {
            "id": 8,
            "role_type_id": 3,
            "role_type_name": "Business",
            "role_type_display_name": "企业用户",
            "name": "business-app-person",
            "type": 1,
            "display_name": "企业用户App个人相关菜单",
            "created_at": "2020-11-23T07:47:51.000000Z",
            "updated_at": "2020-11-23T07:47:51.000000Z"
        },
        {
            "id": 7,
            "role_type_id": 4,
            "role_type_name": "Consumer",
            "role_type_display_name": "个人用户",
            "name": "consumer-app-company",
            "type": 1,
            "display_name": "个人用户App企业相关菜单",
            "created_at": "2020-11-23T07:47:51.000000Z",
            "updated_at": "2020-11-23T07:47:51.000000Z"
        },
        {
            "id": 6,
            "role_type_id": 4,
            "role_type_name": "Consumer",
            "role_type_display_name": "个人用户",
            "name": "consumer-app-person",
            "type": 1,
            "display_name": "个人用户App个人相关菜单",
            "created_at": "2020-11-23T07:47:51.000000Z",
            "updated_at": "2020-11-23T07:47:51.000000Z"
        },
        {
            "id": 5,
            "role_type_id": 3,
            "role_type_name": "Business",
            "role_type_display_name": "企业用户",
            "name": "business-app",
            "type": 1,
            "display_name": "企业用户App首页菜单",
            "created_at": "2020-11-23T07:47:51.000000Z",
            "updated_at": "2020-11-23T07:47:51.000000Z"
        },
        {
            "id": 4,
            "role_type_id": 4,
            "role_type_name": "Consumer",
            "role_type_display_name": "个人用户",
            "name": "consumer-app",
            "type": 1,
            "display_name": "个人用户App首页菜单",
            "created_at": "2020-11-23T07:47:51.000000Z",
            "updated_at": "2020-11-23T07:47:51.000000Z"
        },
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



