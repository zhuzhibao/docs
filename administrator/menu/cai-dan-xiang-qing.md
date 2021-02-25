# 菜单详情

## 说明

* 功能说明：获取系统中菜单详情接口

## 请求接口

#### 请求地址

* `[host]/api/administrator/menu/{id}`
* `id` 为 Menu ID

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
  url: 'http://local.build-dream.cn/api/administrator/menu/165',
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
curl --location --request GET 'http://local.build-dream.cn/api/administrator/menu/165' \
--header 'Authorization: Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE' \
--header 'Accept: application/json' \
--header 'Cookie: PHPSESSID=171eee4ecf83ae527a5416c47ec3bf7f' \
--data-raw ''
```
{% endtab %}

{% tab title="HTTP" %}
```http
GET /api/administrator/menu/165 HTTP/1.1
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
| data | false | [Menu](list.md#menu-can-shu) | 响应内容 |
| msg | true | string | 响应描述 |

#### Menu参数

| **参数名** | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| id | true | integer | 主键ID |
| parent\_id | true | integer | 父菜单主键ID, 为0时无父菜单 |
| menu\_type\_id | true | integer | 菜单分类外键ID |
| need\_permissions | true | string\[\] | 菜单所需权限 |
| need\_role\_types | true | string\[\] | 菜单所需角色 |
| name | true | string | 菜单标示 |
| title | true | string | 菜单展示标题 |
| icon | true | string | 图标 |
| path | true | string | 路径 |
| redirect | true | string | 重定向路径 |
| component | true | string | 前端组件名称 |
| keepAlive | true | boolean | 是否常驻 |
| props | true | boolean | 是否使用 Vue Props 传递 Route 参数 |
| hidden | true | boolean | 是否隐藏菜单 |
| hideChildrenInMenu | true | boolean | 是否隐藏子菜单 |
| sort | true | boolean | 排序 |
| created\_at | true | string | 创建时间 |
| upadted\_at | true | string | 更新时间 |
| children | false | [Menu](list.md#menu-can-shu)\[\] | 子菜单，数据结构同父菜单 |
| menu\_type | true | [MenuType](cai-dan-xiang-qing.md#menutype-can-shu) | 菜单类型 |

#### MenuType参数

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| id | true | integer | 主键ID |
| role\_type\_id | true | integer | 角色类型外键ID |
| role\_type\_name | true | string | 角色类型标示 |
| role\_type\_display\_name | true | string | 角色类型展示名称 |
| name | true | string | 菜单类型标示 |
| type | true | string | 类型：1 - App菜单，0 - Web菜单 |
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
        "id": 165,
        "parent_id": 164,
        "menu_type_id": 3,
        "need_permissions": [],
        "need_role_types": [
            "Business"
        ],
        "name": "CompanyDetail",
        "title": "menu.company.detail",
        "icon": "",
        "path": "/company/:id?/detail",
        "redirect": "",
        "component": "company/CompanyDetail",
        "keepAlive": true,
        "props": true,
        "hidden": false,
        "hideChildrenInMenu": false,
        "sort": 0,
        "deleted_at": null,
        "created_at": "2021-01-06T02:00:38.000000Z",
        "updated_at": "2021-01-06T02:00:38.000000Z",
        "menu_type": {
            "id": 3,
            "role_type_id": 3,
            "role_type_name": "Business",
            "role_type_display_name": "企业用户",
            "name": "business-web",
            "type": 0,
            "display_name": "企业用户Web后台菜单",
            "created_at": "2020-11-23T07:47:51.000000Z",
            "updated_at": "2020-11-23T07:47:51.000000Z"
        }
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

