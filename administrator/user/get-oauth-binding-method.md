# 获取第三方登陆列表接口

## 说明

* 功能说明：获取系统支持第三方登陆方式接口

## 请求接口

#### 请求地址

* `[host]/api/administrator/user/oauth-binding`

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
  url: 'http://local.build-dream.cn/api/administrator/user/oauth-binding',
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
curl --location --request GET 'http://local.build-dream.cn/api/administrator/user/oauth-binding' \
--header 'Authorization: Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE' \
--header 'Accept: application/json' \
--header 'Cookie: PHPSESSID=171eee4ecf83ae527a5416c47ec3bf7f' \
--data-raw ''
```
{% endtab %}

{% tab title="HTTP" %}
```http
GET /api/administrator/user/oauth-binding HTTP/1.1
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
| data | false | [Oauth](get-oauth-binding-method.md#oauth-can-shu)\[\] | 响应内容 |
| msg | true | string | 响应描述 |

#### Oauth参数

| **参数名** | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| name | true | string | 登陆方式标识 |
| display\_name | true | string | 登陆方式字段 |
| url | true | string | 跳转地址 |
| icon | true | string | 图标名称 |
| has\_binding | true | boolean | 是否绑定过此登陆方式 |

## 响应示例

{% tabs %}
{% tab title="正确响应" %}
```javascript
{
    "code": 200,
    "data": [
        {
            "name": "ding_talk",
            "display_name": "钉钉快捷登录",
            "url": "https://oapi.dingtalk.com/connect/qrconnect?appid=dingoaeikmikr2q56h8uym&response_type=code&scope=snsapi_login&state=4eYsaSOVDa8ZCW0MhsDmnFFz4LYQwHk1yzmJJwO1lDGXj0jhnx4WVy6vL9tGxljT&redirect_uri=http%3A%2F%2Flocalhost%3A8000%2F%23%2Faccount%2Fsettings%2Fbinding%2Fding-talk",
            "icon": "dingding",
            "has_binding": false
        },
        {
            "name": "wechat",
            "display_name": "微信快捷登录",
            "url": "https://open.weixin.qq.com/connect/qrconnect?appid=wx64b522a7ca7bf76d&redirect_uri=http%3A%2F%2Flocalhost%3A8000%2F%23%2Fauth%2Flogin%2Fwechat&response_type=code&scope=snsapi_login&state=56c3c0d7f0311ed13a0e56f8834c23b2&connect_redirect=1#wechat_redirect",
            "icon": "wechat",
            "has_binding": true
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



