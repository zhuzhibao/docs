# 更新权限

## 说明

* 功能说明：更新权限接口

## 请求接口

#### 请求地址

* `[host]/api/administrator/role/{id}`
* `id` 为 Role ID 

#### 请求方式

* `PUT`

#### 请求头Header

* `Authorization:Bearer {token}` token 为用户授权登陆Token
* `Accept:application/json`

#### 请求参数

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| display\_name | true | string | 角色展示名称 |
| permissions | true | string\[\] | 权限数组 |

## 请求示例

{% tabs %}
{% tab title="JavaScript" %}
```javascript
var axios = require('axios');
var data = JSON.stringify({"display_name":"软件测试员","permissions":["resume.viewAny","resume.view","resume.delivery","recruitment.viewAny","recruitment.view","recruitment.create","recruitment.update","recruitment.delete","talentCategory.viewAny","talentCategory.view","licenseCategory.viewAny","licenseCategory.view"]});

var config = {
  method: 'put',
  url: 'http://local.build-dream.cn/api/administrator/role/54',
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
curl --location --request PUT 'http://local.build-dream.cn/api/administrator/role/54' \
--header 'Authorization: Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \
--header 'Cookie: PHPSESSID=171eee4ecf83ae527a5416c47ec3bf7f' \
--data-raw '{
    "display_name": "软件测试员",
    "permissions": [
                    "resume.viewAny",
                    "resume.view",
                    "resume.delivery",
                    "recruitment.viewAny",
                    "recruitment.view",
                    "recruitment.create",
                    "recruitment.update",
                    "recruitment.delete",
                    "talentCategory.viewAny",
                    "talentCategory.view",
                    "licenseCategory.viewAny",
                    "licenseCategory.view"
                ]
}'
```
{% endtab %}

{% tab title="HTTP" %}
```http
PUT /api/administrator/role/54 HTTP/1.1
Host: local.build-dream.cn
Authorization: Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE
Accept: application/json
Content-Type: application/json
Cookie: PHPSESSID=171eee4ecf83ae527a5416c47ec3bf7f
Content-Length: 571

{
    "display_name": "软件测试员",
    "permissions": [
                    "resume.viewAny",
                    "resume.view",
                    "resume.delivery",
                    "recruitment.viewAny",
                    "recruitment.view",
                    "recruitment.create",
                    "recruitment.update",
                    "recruitment.delete",
                    "talentCategory.viewAny",
                    "talentCategory.view",
                    "licenseCategory.viewAny",
                    "licenseCategory.view"
                ]
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
        "display_name": [
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



