# 菜单列表

## 说明

* 功能说明：获取系统中所有菜单列表接口

## 请求接口

#### 请求地址

* `[host]/api/administrator/menu`

#### 请求方式

* `GET`

#### 请求头Header

* `Authorization:Bearer {token}` token 为用户授权登陆Token
* `Accept:application/json`

#### 请求参数

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| menu\_type\_id | true | integer | 菜单类型外键ID |

## 请求示例

{% tabs %}
{% tab title="JavaScript" %}
```javascript
var axios = require('axios');
var data = JSON.stringify({"menu_type_id":3});

var config = {
  method: 'get',
  url: 'http://local.build-dream.cn/api/administrator/menu',
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
curl --location --request GET 'http://local.build-dream.cn/api/administrator/menu' \
--header 'Authorization: Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \
--header 'Cookie: PHPSESSID=171eee4ecf83ae527a5416c47ec3bf7f' \
--data-raw '{
    "menu_type_id": 3
}'
```
{% endtab %}

{% tab title="HTTP" %}
```http
GET /api/administrator/menu HTTP/1.1
Host: local.build-dream.cn
Authorization: Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE
Accept: application/json
Content-Type: application/json
Cookie: PHPSESSID=171eee4ecf83ae527a5416c47ec3bf7f
Content-Length: 25

{
    "menu_type_id": 3
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
| data | false | [Menu](list.md#menu-can-shu)\[\] | 响应内容 |
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
| key | true | integer | 键，同主键ID |
| value | true | integer | 值，同主键ID |

## 响应示例

{% tabs %}
{% tab title="正确响应" %}
```javascript
{
    "code": 200,
    "data": [
        {
            "id": 145,
            "parent_id": 0,
            "menu_type_id": 3,
            "need_permissions": [],
            "need_role_types": [
                "Business"
            ],
            "name": "Dashboard",
            "title": "menu.dashboard",
            "icon": "dashboard",
            "path": "/dashboard",
            "redirect": "/dashboard/workspace",
            "component": "RouteView",
            "keepAlive": false,
            "props": false,
            "hidden": false,
            "hideChildrenInMenu": false,
            "sort": 5,
            "deleted_at": null,
            "created_at": "2021-01-04T05:54:39.000000Z",
            "updated_at": "2021-01-06T01:19:24.000000Z",
            "children": [
                {
                    "id": 148,
                    "parent_id": 145,
                    "menu_type_id": 3,
                    "need_permissions": [],
                    "need_role_types": [
                        "Business"
                    ],
                    "name": "DashboardWorkplace",
                    "title": "menu.dashboard.workplace",
                    "icon": "",
                    "path": "/dashboard/workplace",
                    "redirect": "",
                    "component": "Workplace",
                    "keepAlive": true,
                    "props": true,
                    "hidden": false,
                    "hideChildrenInMenu": false,
                    "sort": 0,
                    "deleted_at": null,
                    "created_at": "2021-01-04T06:21:55.000000Z",
                    "updated_at": "2021-01-06T01:19:24.000000Z",
                    "key": 148,
                    "value": 148
                }
            ],
            "key": 145,
            "value": 145
        },
        {
            "id": 164,
            "parent_id": 0,
            "menu_type_id": 3,
            "need_permissions": [],
            "need_role_types": [
                "Business"
            ],
            "name": "Company",
            "title": "menu.company",
            "icon": "apartment",
            "path": "/company",
            "redirect": "/company/detail",
            "component": "RouteView",
            "keepAlive": false,
            "props": false,
            "hidden": false,
            "hideChildrenInMenu": false,
            "sort": 4,
            "deleted_at": null,
            "created_at": "2021-01-06T01:19:18.000000Z",
            "updated_at": "2021-01-06T02:00:47.000000Z",
            "children": [
                {
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
                    "key": 165,
                    "value": 165
                }
            ],
            "key": 164,
            "value": 164
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



