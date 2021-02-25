# 更新第三方登陆绑定接口

## 说明

* 功能说明：更新第三方登陆方式绑定记录接口

## 请求接口

#### 请求地址

* `[host]/api/administrator/user/oauth-binding/{type}`
* `type` 值为 `WECHAT` 或 `DING_TALK`

#### 请求方式

* `PUT`

#### 请求头Header

* `Authorization:Bearer {token}` token 为用户授权登陆Token
* `Accept:application/json`

#### 请求参数

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| state | true | boolean | 更新指示状态，`true` 为解除绑定，`false` 为重新获取绑定 |

## 请求示例

{% tabs %}
{% tab title="JavaScript" %}
```javascript
var axios = require('axios');
var data = JSON.stringify({"state":false});

var config = {
  method: 'put',
  url: 'http://local.build-dream.cn/api/administrator/user/oauth-binding/WECHAT',
  headers: { 
    'Authorization': 'Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE', 
    'Accept': 'application/json', 
    'Content-Type': 'application/json',
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
curl --location --request PUT 'http://local.build-dream.cn/api/administrator/user/oauth-binding/WECHAT' \
--header 'Authorization: Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \
--header 'Cookie: PHPSESSID=171eee4ecf83ae527a5416c47ec3bf7f' \
--data-raw '{
    "state": false
}'
```
{% endtab %}

{% tab title="HTTP" %}
```http
PUT /api/administrator/user/oauth-binding/WECHAT HTTP/1.1
Host: local.build-dream.cn
Authorization: Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE
Accept: application/json
Content-Type: application/json
Cookie: PHPSESSID=171eee4ecf83ae527a5416c47ec3bf7f
Content-Length: 22

{
    "state": false
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
| data | false | string | 响应内容 或 重新绑定跳转链接 |
| msg | true | string | 响应描述 |

## 响应示例

{% tabs %}
{% tab title="正确响应" %}
```javascript
{
    "code": 200,
    "data": "操作成功",
    "msg": "success"
}

or

{
    "code": 200,
    "data": "https://open.weixin.qq.com/connect/qrconnect?appid=wx64b522a7ca7bf76d&redirect_uri=http%3A%2F%2Flocalhost%3A8000%2F%23%2Faccount%2Fsettings%2Fbinding%2Fwechat&response_type=code&scope=snsapi_login&state=0c28af8d1e9394906b0c4e622dcdb747&connect_redirect=1#wechat_redirect",
    "msg": "success"
}

```
{% endtab %}

{% tab title="表单验证错误响应" %}
```javascript
{
    "code": 403,
    "data": {
        "state": [
            "state 不能为空。"
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



