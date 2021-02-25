# 角色列表

## 说明

* 功能说明：获取所有角色列表接口

## 请求接口

#### 请求地址

* `[host]/api/administrator/role`

#### 请求方式

* `GET`

#### 请求头Header

* `Authorization:Bearer {token}` token 为用户授权登陆Token
* `Accept:application/json`

#### 请求参数

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| page | false | integer | 页数 |
| pageSize | false | integer | 页码, 默认为20条数据每页 |

## 请求示例

{% tabs %}
{% tab title="JavaScript" %}
```javascript
var axios = require('axios');
var data = JSON.stringify({"page":1,"pageSize":5});

var config = {
  method: 'get',
  url: 'http://local.build-dream.cn/api/administrator/role',
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
curl --location --request GET 'http://local.build-dream.cn/api/administrator/role' \
--header 'Authorization: Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \
--header 'Cookie: PHPSESSID=171eee4ecf83ae527a5416c47ec3bf7f' \
--data-raw '{
    "page": 1,
    "pageSize": 5
}'
```
{% endtab %}

{% tab title="HTTP" %}
```http
GET /api/administrator/role HTTP/1.1
Host: local.build-dream.cn
Authorization: Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE
Accept: application/json
Content-Type: application/json
Cookie: PHPSESSID=171eee4ecf83ae527a5416c47ec3bf7f
Content-Length: 36

{
    "page": 1,
    "pageSize": 5
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
| data | false | [Pagination](jiao-se-lie-biao.md#pagination-can-shu) | 响应内容 |
| msg | true | string | 响应描述 |

#### Pagination参数

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| current\_page | true | integer | 当前页数 |
| data | true | [Role](jiao-se-lie-biao.md#role-can-shu)\[\] | 角色数据 |
| per\_page | true | integer | 每页数据条数 |
| total | true | integer | 总数据量 |
| last\_page | true | integer | 总页数 |

#### Role参数

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| id | true | integer | 主键ID |
| role\_type\_id | true | integer | 角色类型ID |
| role\_type\_name | true | string | 角色类型标示 |
| role\_type\_display\_name | true | string | 角色类型展示名称 |
| company\_id | true | integer | 公司主键ID |
| company\_name | true | string | 公司名称 |
| display\_name | true | string | 角色展示名称 |
| name | true | string | 角色标示 |
| created\_at | true | string | 创建时间 |
| updated\_at | true | string | 更新时间 |
| permissions | true | string\[\] | 拥有权限列表，值为权限标示数组 |

## 响应示例

{% tabs %}
{% tab title="正确响应" %}
```javascript
{
    "code": 200,
    "data": {
        "current_page": 1,
        "data": [
            {
                "id": 54,
                "role_type_id": 3,
                "role_type_name": "Business",
                "role_type_display_name": "企业用户",
                "company_id": 23,
                "company_name": "浙江测试股份制有限公司2",
                "display_name": "测试员",
                "name": "42.raylfR9e",
                "created_at": "2020-12-07T09:46:22.000000Z",
                "updated_at": "2020-12-07T09:46:22.000000Z",
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
                "id": 53,
                "role_type_id": 3,
                "role_type_name": "Business",
                "role_type_display_name": "企业用户",
                "company_id": 42,
                "company_name": "杭州南杭网络科技有限公司",
                "display_name": "管理员",
                "name": "Admin",
                "created_at": "2020-12-07T09:44:04.000000Z",
                "updated_at": "2020-12-07T09:44:04.000000Z",
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
                    "licenseCategory.view",
                    "information.viewAny",
                    "information.view",
                    "information.star",
                    "informationCategory.viewAny",
                    "informationCategory.view",
                    "product.viewAny",
                    "product.view",
                    "product.create",
                    "product.update",
                    "product.delete",
                    "productCategory.viewAny",
                    "productCategory.view",
                    "productCategory.create",
                    "productCategory.update",
                    "productCategory.delete",
                    "company.viewAny",
                    "company.view",
                    "shopOrder.viewAny",
                    "shopOrder.view",
                    "shopOrder.create",
                    "shopOrder.update",
                    "course.viewAny",
                    "course.view",
                    "course.create",
                    "course.update",
                    "course.delete",
                    "courseCategory.viewAny",
                    "courseCategory.view",
                    "courseCategory.create",
                    "courseCategory.update",
                    "courseCategory.delete",
                    "courseOrder.viewAny",
                    "courseOrder.view",
                    "courseOrder.create",
                    "courseOrder.update",
                    "courseOrder.delete",
                    "contract.viewAny",
                    "contract.view",
                    "contract.create",
                    "contract.update",
                    "contract.delete",
                    "contractTemplate.restore",
                    "contractTemplate.delete",
                    "contractTemplate.update",
                    "contractTemplate.create",
                    "contractTemplate.view",
                    "companyQualification.viewAny",
                    "companyQualification.view",
                    "companyQualification.create",
                    "companyQualification.update",
                    "companyQualification.delete",
                    "jobHope.viewAny",
                    "jobHope.view",
                    "jobHope.create",
                    "jobHope.update",
                    "jobHope.delete"
                ]
            },
            {
                "id": 52,
                "role_type_id": 3,
                "role_type_name": "Business",
                "role_type_display_name": "企业用户",
                "company_id": 23,
                "company_name": "浙江测试股份制有限公司2",
                "display_name": "吴国黎",
                "name": "35.ZjBhksiD",
                "created_at": "2020-11-18T05:39:39.000000Z",
                "updated_at": "2020-11-18T05:39:39.000000Z",
                "permissions": [
                    "recruitment.viewAny",
                    "recruitment.view",
                    "recruitment.create",
                    "recruitment.update",
                    "recruitment.delete",
                    "talentCategory.viewAny",
                    "talentCategory.view"
                ]
            },
            {
                "id": 51,
                "role_type_id": 3,
                "role_type_name": "Business",
                "role_type_display_name": "企业用户",
                "company_id": 35,
                "company_name": "浙江易顺带网络科技有限公司",
                "display_name": "管理员",
                "name": "35.ttycqpyS",
                "created_at": "2020-11-17T06:15:47.000000Z",
                "updated_at": "2020-11-17T06:15:47.000000Z",
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
                    "licenseCategory.view",
                    "information.viewAny",
                    "information.view",
                    "information.star",
                    "informationCategory.viewAny",
                    "informationCategory.view",
                    "product.viewAny",
                    "product.view",
                    "product.create",
                    "product.update",
                    "product.delete",
                    "productCategory.viewAny",
                    "productCategory.view",
                    "productCategory.create",
                    "productCategory.update",
                    "productCategory.delete",
                    "company.viewAny",
                    "company.view",
                    "shopOrder.viewAny",
                    "shopOrder.view",
                    "shopOrder.create",
                    "shopOrder.update",
                    "course.viewAny",
                    "course.view",
                    "course.create",
                    "course.update",
                    "course.delete",
                    "courseCategory.viewAny",
                    "courseCategory.view",
                    "courseCategory.create",
                    "courseCategory.update",
                    "courseCategory.delete",
                    "courseOrder.viewAny",
                    "courseOrder.view",
                    "courseOrder.create",
                    "courseOrder.update",
                    "courseOrder.delete",
                    "contract.viewAny",
                    "contract.view",
                    "contract.create",
                    "contract.update",
                    "contract.delete",
                    "contractTemplate.restore",
                    "contractTemplate.delete",
                    "contractTemplate.update",
                    "contractTemplate.create",
                    "contractTemplate.view"
                ]
            },
            {
                "id": 50,
                "role_type_id": 3,
                "role_type_name": "Business",
                "role_type_display_name": "企业用户",
                "company_id": 41,
                "company_name": "杭州大大大大大地好建设有限公司",
                "display_name": "测试角色",
                "name": "41.N5YGdwcG",
                "created_at": "2020-11-17T06:09:27.000000Z",
                "updated_at": "2020-11-17T06:09:27.000000Z",
                "permissions": [
                    "courseCategory.viewAny",
                    "courseCategory.view",
                    "courseCategory.create",
                    "courseCategory.update",
                    "courseCategory.delete"
                ]
            }
        ],
        "first_page_url": "http://local.build-dream.cn/api/administrator/role?page=1",
        "from": 1,
        "last_page": 3,
        "last_page_url": "http://local.build-dream.cn/api/administrator/role?page=3",
        "links": [
            {
                "url": null,
                "label": "&laquo; 上一页",
                "active": false
            },
            {
                "url": "http://local.build-dream.cn/api/administrator/role?page=1",
                "label": 1,
                "active": true
            },
            {
                "url": "http://local.build-dream.cn/api/administrator/role?page=2",
                "label": 2,
                "active": false
            },
            {
                "url": "http://local.build-dream.cn/api/administrator/role?page=3",
                "label": 3,
                "active": false
            },
            {
                "url": "http://local.build-dream.cn/api/administrator/role?page=2",
                "label": "下一页 &raquo;",
                "active": false
            }
        ],
        "next_page_url": "http://local.build-dream.cn/api/administrator/role?page=2",
        "path": "http://local.build-dream.cn/api/administrator/role",
        "per_page": 5,
        "prev_page_url": null,
        "to": 5,
        "total": 13
    },
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



