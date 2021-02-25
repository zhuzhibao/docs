# 公司角色详情

## 说明

* 功能说明：查询公司角色详情接口

## 请求接口

#### 请求地址

* `[host]/api/administrator/company/{companyId}/role/{roleId}`
* `companyId` 为 Company ID
* `roleId` 为 Role ID

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
  url: 'http://local.build-dream.cn/api/administrator/company/23/role/54',
  headers: { 
    'Authorization': 'Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE', 
    'Accept': 'application/json'
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
curl --location --request GET 'http://local.build-dream.cn/api/administrator/company/23/role/54' \
--header 'Authorization: Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE' \
--header 'Accept: application/json' \
--data-raw ''
```
{% endtab %}

{% tab title="HTTP" %}
```http
GET /api/administrator/company/23/role/54 HTTP/1.1
Host: local.build-dream.cn
Authorization: Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE
Accept: application/json
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
| data | false | [Role](gong-si-jiao-se-xiang-qing.md#role-can-shu) | 响应内容 |
| msg | true | string | 响应描述 |

#### Role参数

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| id | true | integer | 主键ID |
| role\_type\_id | true | integer | 角色类型外键 |
| role\_type\_name | true | string | 角色类型标识 |
| role\_type\_display\_name | true | string | 角色类型展示名称 |
| company\_id | true | integer | 公司外键 |
| display\_name | true | string | 角色展示名称 |
| name | true | string | 角色标识 |
| guard\_name | true | string | 守卫标识 |
| created\_at | true | string | 创建时间 |
| updated\_at | true | string | 更新时间 |
| company | true | [Company](gong-si-jiao-se-xiang-qing.md#company-can-shu) | 公司信息 |
| role\_type | true | [RoleType](gong-si-jiao-se-xiang-qing.md#roletype-can-shu) | 角色类型信息 |
| user | true | [User](gong-si-jiao-se-xiang-qing.md#user-can-shu)\[\] | 使用此角色用户 |

#### Company参数

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| id | true | integer | 主键ID |
| service\_company\_id | true | integer | 服务提供公司外键 |
| name | true | string | 公司名称 |
| logo\_material\_id | true | integer | Logo素材ID |
| logo | true | string | Logo链接 |
| images | true | string\[\] | 图片链接数组 |
| desc | true | string | 描述 |
| license\_material\_id | true | integer | 营业执照素材ID |
| license | true | string | 营业执照链接 |
| province\_id | true | integer | 省份ID |
| province\_name | true | string | 省份名称 |
| city\_id | true | integer | 城市ID |
| city\_name | true | string | 城市名称 |
| country\_id | true | integer | 区县ID |
| country\_name | true | string | 区县名称 |
| permission\_level\_id | true | integer | 会员等级ID |
| permission\_level\_name | true | name | 会员等级名称 |
| has\_verify | true | integer | 是否验证 |
| created\_at | true | string | 创建时间 |
| updated\_at | true | string | 更新时间 |

#### RoleType参数

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| id | true | integer | 角色类型主键ID |
| name | true | string | 角色类型标示 |
| display\_name | true | string | 角色类型展示名称 |
| created\_at | true | string | 创建时间 |
| updated\_at | true | string | 更新时间 |

#### User参数

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| id | true | integer | 主键ID |
| name | true | string | 用户名 |
| nickname | true | string | 昵称 |
| real\_name | true | string | 真实姓名 |
| email | true | string | 邮箱 |
| phone | true | string | 手机号 |
| avatar | true | string | 头像 |
| email\_verified\_at | true | string \| null | 邮箱验证时间 |
| phone\_verified\_at | true | string \| null | 手机验证时间 |
| type | true | integer | 类型 |
| status | true | integer | 状态 |
| created\_at | true | string | 创建时间 |
| updated\_at | true | string | 更新时间 |

## 响应示例

{% tabs %}
{% tab title="正确响应" %}
```javascript
{
    "code": 200,
    "data": {
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
        "company": {
            "id": 23,
            "service_company_id": 0,
            "name": "浙江测试股份制有限公司2",
            "logo_material_id": 1,
            "logo": "https://ui-avatars.com/api/浙江无罪开释股份有限公司",
            "images": [],
            "desc": "测试公司描述",
            "license_material_id": 2,
            "license": "http://qgh192mzc.hd-bkt.clouddn.com/images/OHdSjojPBTkOrZK1lPNTMjo7qxvsZh6McUnuNXhh.jpeg",
            "province_id": 0,
            "province_name": "",
            "city_id": 0,
            "city_name": "",
            "country_id": 0,
            "country_name": "",
            "permission_level_id": 0,
            "permission_level_name": "默认等级",
            "has_verify": false,
            "deleted_at": null,
            "created_at": "2020-09-27T03:14:42.000000Z",
            "updated_at": "2020-09-27T03:14:42.000000Z"
        },
        "role_type": {
            "id": 3,
            "name": "Business",
            "display_name": "企业用户",
            "created_at": "2020-10-20T05:09:27.000000Z",
            "updated_at": "2020-10-20T05:09:27.000000Z"
        },
        "user": [
            {
                "id": 100,
                "name": "用户rJpQwh",
                "nickname": "冯贾斌",
                "real_name": "冯贾斌",
                "email": "18967793199@qq.com",
                "phone": "18967793199",
                "avatar": "https://ui-avatars.com/api/用户rJpQwh",
                "email_verified_at": null,
                "phone_verified_at": "2020-12-07 14:07:26",
                "type": 0,
                "status": 1,
                "deleted_at": null,
                "created_at": "2020-12-07T06:07:26.000000Z",
                "updated_at": "2020-12-07T09:50:08.000000Z",
                "rong_cloud_token": null,
                "pivot": {
                    "role_id": 54,
                    "model_id": 100,
                    "model_type": "App\\Models\\User"
                }
            },
            {
                "id": 105,
                "name": "用户名WpLtJfJep46tdJQz",
                "nickname": "严美凤",
                "real_name": "严美凤",
                "email": "13958111940@qq.com",
                "phone": "13958111941",
                "avatar": "https://ui-avatars.com/api/用户名WpLtJfJep46tdJQz",
                "email_verified_at": null,
                "phone_verified_at": null,
                "type": 0,
                "status": 1,
                "deleted_at": null,
                "created_at": "2020-12-07T09:48:13.000000Z",
                "updated_at": "2020-12-07T09:48:13.000000Z",
                "rong_cloud_token": null,
                "pivot": {
                    "role_id": 54,
                    "model_id": 105,
                    "model_type": "App\\Models\\User"
                }
            },
            {
                "id": 106,
                "name": "用户名HMHJ2nXuxQEeJrOA",
                "nickname": "黄应",
                "real_name": "黄应",
                "email": "13819190858@qq.com",
                "phone": "13819190859",
                "avatar": "https://ui-avatars.com/api/用户名HMHJ2nXuxQEeJrOA",
                "email_verified_at": null,
                "phone_verified_at": null,
                "type": 0,
                "status": 1,
                "deleted_at": null,
                "created_at": "2020-12-07T09:48:13.000000Z",
                "updated_at": "2020-12-07T09:48:13.000000Z",
                "rong_cloud_token": null,
                "pivot": {
                    "role_id": 54,
                    "model_id": 106,
                    "model_type": "App\\Models\\User"
                }
            },
            {
                "id": 107,
                "name": "用户名rwl0kO5szc9Rvc0c",
                "nickname": "张智佶",
                "real_name": "张智佶",
                "email": "15888895905@qq.com",
                "phone": "15888895906",
                "avatar": "https://ui-avatars.com/api/用户名rwl0kO5szc9Rvc0c",
                "email_verified_at": null,
                "phone_verified_at": null,
                "type": 0,
                "status": 1,
                "deleted_at": null,
                "created_at": "2020-12-07T09:48:13.000000Z",
                "updated_at": "2020-12-07T09:48:13.000000Z",
                "rong_cloud_token": "9MCG5/K4ruoAk5O+HIfeCvn/TWvyx+aX4Z8PqpQNyO0=@kee7.cn.rongnav.com;kee7.cn.rongcfg.com",
                "pivot": {
                    "role_id": 54,
                    "model_id": 107,
                    "model_type": "App\\Models\\User"
                }
            },
            {
                "id": 108,
                "name": "用户名k4JpLg4LnkOnpmrO",
                "nickname": "张治欣",
                "real_name": "张治欣",
                "email": "13666615704@qq.com",
                "phone": "13666615705",
                "avatar": "https://ui-avatars.com/api/用户名k4JpLg4LnkOnpmrO",
                "email_verified_at": null,
                "phone_verified_at": null,
                "type": 0,
                "status": 1,
                "deleted_at": null,
                "created_at": "2020-12-07T09:48:13.000000Z",
                "updated_at": "2020-12-07T09:48:13.000000Z",
                "rong_cloud_token": null,
                "pivot": {
                    "role_id": 54,
                    "model_id": 108,
                    "model_type": "App\\Models\\User"
                }
            }
        ]
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



