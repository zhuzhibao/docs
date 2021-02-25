# 更新用户信息接口

## 说明

* 功能说明：更新手机号码、密码或邮箱接口

## 请求接口

#### 请求地址

* `[host]/api/administrator/user/security`

#### 请求方式

* `PUT`

#### 请求头Header

* `Authorization:Bearer {token}` token 为用户授权登陆Token
* `Accept:application/json`

#### 请求参数

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| verification\_code | true | int | 短信验证码 |
| new\_phone | false | int | 新手机号码，不可与系统中已有号码相同 |
| new\_email | false | string | 新邮箱地址，不可与系统中已有邮箱相同 |
| new\_password | false | string | 新密码 |

## 请求示例

{% tabs %}
{% tab title="JavaScript" %}
```javascript
var axios = require('axios');
var data = JSON.stringify({"verification_code":123456,"new_phone":13157175994,"new_email":"zlvjlasdjfklajsdf@build-dream.cn","new_password":"123123123123"});

var config = {
  method: 'put',
  url: 'http://local.build-dream.cn/api/administrator/user/security',
  headers: { 
    'Authorization': 'Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE', 
    'Accept': 'application/json', 
    'Content-Type': 'application/json'
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
curl --location --request PUT 'http://local.build-dream.cn/api/administrator/user/security' \
--header 'Authorization: Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \
--data-raw '{
    "verification_code": 123456,
    "new_phone": 13157175994,
    "new_email": "zlvjlasdjfklajsdf@build-dream.cn",
    "new_password": "123123123123"
}'
```
{% endtab %}

{% tab title="HTTP" %}
```http
PUT /api/administrator/user/security HTTP/1.1
Host: local.build-dream.cn
Authorization: Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE
Accept: application/json
Content-Type: application/json
Content-Length: 154

{
    "verification_code": 123456,
    "new_phone": 13157175994,
    "new_email": "zlvjlasdjfklajsdf@build-dream.cn",
    "new_password": "123123123123"
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
        "verification_code": [
            "verification_code 不能为空"
        ]
    },
    "msg": "请求数据验证失败!"
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

