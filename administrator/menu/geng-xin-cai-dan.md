# 更新菜单

## 说明

* 功能说明：更新菜单接口

## 请求接口

#### 请求地址

* `[host]/api/administrator/menu/{id}`
* `id` 为 Menu ID

#### 请求方式

* `PUT`

#### 请求头Header

* `Authorization:Bearer {token}` token 为用户授权登陆Token
* `Accept:application/json`

#### 请求参数

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| parent\_id | false | integer | 父菜单主键ID, 为0时无父菜单 |
| menu\_type\_id | true | integer | 菜单分类外键ID |
| need\_permissions | false | string\[\] | 菜单所需权限 |
| need\_role\_types | false | string\[\] | 菜单所需角色 |
| name | true | string | 菜单标示 |
| title | true | string | 菜单展示标题 |
| icon | false | string | 图标 |
| path | true | string | 路径 |
| redirect | false | string | 重定向路径 |
| component | false | string | 前端组件名称 |
| keepAlive | false | boolean | 是否常驻 |
| props | false | boolean | 是否使用 Vue Props 传递 Route 参数 |
| hidden | false | boolean | 是否隐藏菜单 |
| hideChildrenInMenu | false | boolean | 是否隐藏子菜单 |

## 请求示例

{% tabs %}
{% tab title="JavaScript" %}
```javascript
var axios = require('axios');
var data = JSON.stringify({"menu_type_id":3,"name":"TestPermission","title":"测试权限","path":"/test-permission"});

var config = {
  method: 'put',
  url: 'http://local.build-dream.cn/api/administrator/menu/167',
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
curl --location --request PUT 'http://local.build-dream.cn/api/administrator/menu/167' \
--header 'Authorization: Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \
--header 'Cookie: PHPSESSID=171eee4ecf83ae527a5416c47ec3bf7f' \
--data-raw '{
    "menu_type_id": 3,
    "name": "TestPermission",
    "title": "测试权限",
    "path": "/test-permission"
}'
```
{% endtab %}

{% tab title="HTTP" %}
```http
PUT /api/administrator/menu/167 HTTP/1.1
Host: local.build-dream.cn
Authorization: Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE
Accept: application/json
Content-Type: application/json
Cookie: PHPSESSID=171eee4ecf83ae527a5416c47ec3bf7f
Content-Length: 108

{
    "menu_type_id": 3,
    "name": "TestPermission",
    "title": "测试权限",
    "path": "/test-permission"
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
| data | false | string | 响应内容 |
| msg | true | string | 响应描述 |

## 响应示例

{% tabs %}
{% tab title="正确响应" %}
```javascript
{
    "code": 200,
    "data": "更新成功",
    "msg": "success"
}
```
{% endtab %}

{% tab title="表单验证错误响应" %}
```javascript
{
    "code": 403,
    "data": {
        "path": [
            "path 不能为空"
        ]
    },
    "msg": "请求数据验证失败!"
}
```
{% endtab %}

{% tab title="认证错误响应" %}
```javascript
{
    "code": 401,
    "msg": "请求未认证"
}
```
{% endtab %}
{% endtabs %}



