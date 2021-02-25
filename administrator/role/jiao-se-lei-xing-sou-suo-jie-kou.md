# 角色类型搜索接口

## 说明

* 功能说明：搜索角色类型接口

## 请求接口

#### 请求地址

* `[host]/api/administrator/role/serach-type`

#### 请求方式

* `POST`

#### 请求头Header

* `Authorization:Bearer {token}` token 为用户授权登陆Token
* `Accept:application/json`

#### 请求参数

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| displayName | true | string | 角色类型展示名称 |

## 请求示例

{% tabs %}
{% tab title="JavaScript" %}
```javascript
var axios = require('axios');
var data = JSON.stringify({"displayName":"个人"});

var config = {
  method: 'post',
  url: 'http://local.build-dream.cn/api/administrator/role/search-type',
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
curl --location --request POST 'http://local.build-dream.cn/api/administrator/role/search-type' \
--header 'Authorization: Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \
--header 'Cookie: PHPSESSID=171eee4ecf83ae527a5416c47ec3bf7f' \
--data-raw '{
    "displayName": "个人"
}'
```
{% endtab %}

{% tab title="HTTP" %}
```http
POST /api/administrator/role/search-type HTTP/1.1
Host: local.build-dream.cn
Authorization: Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE
Accept: application/json
Content-Type: application/json
Cookie: PHPSESSID=171eee4ecf83ae527a5416c47ec3bf7f
Content-Length: 27

{
    "displayName": "个人"
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
| data | false | [RoleType](jiao-se-lei-xing-sou-suo-jie-kou.md#roletype-can-shu)\[\] | 响应内容 |
| msg | true | string | 响应描述 |

#### RoleType参数

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| id | true | integer | 角色类型主键ID |
| name | true | string | 角色类型标示 |
| display\_name | true | string | 角色类型展示名称 |
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
            "id": 4,
            "name": "Consumer",
            "display_name": "个人用户",
            "created_at": "2020-10-20T05:09:27.000000Z",
            "updated_at": "2020-10-20T05:09:27.000000Z"
        }
    ],
    "msg": "success"
}
```
{% endtab %}

{% tab title="表单验证错误响应" %}
```javascript
{
    "code": 403,
    "data": {
        "displayName": [
            "display name 不能为空"
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



