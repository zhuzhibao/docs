# 搜索公司角色

## 说明

* 功能说明：查询公司角色详情接口

## 请求接口

#### 请求地址

* `[host]/api/administrator/company/{companyId}/role/search`
* `companyId` 为 Company ID

#### 请求方式

* `GET`

#### 请求头Header

* `Authorization:Bearer {token}` token 为用户授权登陆Token
* `Accept:application/json`

#### 请求参数

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| id | false | integer | 主键ID |
| name | false | string | 模糊搜索角色标识 |

## 请求示例

{% tabs %}
{% tab title="JavaScript" %}
```javascript
var axios = require('axios');
var data = JSON.stringify({"name":"a"});

var config = {
  method: 'post',
  url: 'http://local.build-dream.cn/api/administrator/company/23/role/search',
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
curl --location --request POST 'http://local.build-dream.cn/api/administrator/company/23/role/search' \
--header 'Authorization: Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \
--data-raw '{
    "name": "a"
}'
```
{% endtab %}

{% tab title="HTTP" %}
```http
POST /api/administrator/company/23/role/search HTTP/1.1
Host: local.build-dream.cn
Authorization: Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE
Accept: application/json
Content-Type: application/json
Content-Length: 19

{
    "name": "a"
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
| data | false | [RoleType](sou-suo-gong-si-jiao-se.md#roletype-can-shu)\[\] | 响应内容 |
| msg | true | string | 响应描述 |

#### RoleType参数

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| id | true | integer | 角色类型主键ID |
| role\_type\_id | true | integer | 角色类型外键 |
| role\_type\_name | true | string | 角色类型标识 |
| role\_type\_display\_name | true | string | 角色类型展示名称 |
| company\_id | true | integer | 公司外键 |
| display\_name | true | string | 展示名称 |
| name | true | string | 标识符 |
| guard\_name | true | string | 守卫标识符 |
| title | true | string | 标题 |
| key | true | integer | 键，同ID |
| value | true | integer | 值，同ID |
| permissions | true | string\[\] | 权限数组 |
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
            "id": 54,
            "role_type_id": 3,
            "role_type_name": "Business",
            "role_type_display_name": "企业用户",
            "company_id": 23,
            "display_name": "软件测试员",
            "name": "42.raylfR9e",
            "guard_name": "api",
            "created_at": "2020-12-07T09:46:22.000000Z",
            "updated_at": "2021-01-27T05:12:04.000000Z",
            "title": "软件测试员",
            "key": 54,
            "value": 54,
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
        },
        {
            "id": 52,
            "role_type_id": 3,
            "role_type_name": "Business",
            "role_type_display_name": "企业用户",
            "company_id": 23,
            "display_name": "吴国黎",
            "name": "35.ZjBhksiD",
            "guard_name": "api",
            "created_at": "2020-11-18T05:39:39.000000Z",
            "updated_at": "2020-11-18T05:39:39.000000Z",
            "title": "吴国黎",
            "key": 52,
            "value": 52,
            "permissions": [
                "recruitment.viewAny",
                "recruitment.view",
                "recruitment.create",
                "recruitment.update",
                "recruitment.delete",
                "talentCategory.viewAny",
                "talentCategory.view"
            ]
        }
    ],
    "msg": "success"
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



