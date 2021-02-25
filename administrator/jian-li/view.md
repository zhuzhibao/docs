# 简历详情

## 说明

* 功能说明：查看简历详情接口

## 请求接口

#### 请求地址

* `[host]/api/administrator/resume/{id}`
* `id` 为 Resume ID

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
  url: 'http://local.build-dream.cn/api/administrator/resume/17',
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
curl --location --request GET 'http://local.build-dream.cn/api/administrator/resume/17' \
--header 'Authorization: Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE' \
--header 'Accept: application/json' \
--header 'Cookie: PHPSESSID=171eee4ecf83ae527a5416c47ec3bf7f' \
--data-raw ''
```
{% endtab %}

{% tab title="HTTP" %}
```http
GET /api/administrator/resume/17 HTTP/1.1
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
| data | false | [Resume](view.md#resume-can-shu) | 响应内容 |
| msg | true | string | 响应描述 |

#### Resume参数

| **参数名** | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| id | true | integer | 主键ID |
| real\_name | true | string | 真实姓名 |
| birthday | true | string | 生日 |
| eduction | true | string | 教育程度 |
| major | true | string | 专业 |
| user | true | User | 用户信息 |
| job\_hope | true | [JobHope](list.md#jobhope-can-shu)\[\] | 职位期望 |
| license | true | [License](list.md#license-can-shu)\[\] | 证书 |
| desc | true | string | 描述 |
| status | true | integer | 状态 |
| annex\_url | true | string | 附件链接 |
| graduated\_at | true | string | 毕业时间 |
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

#### JobHope参数

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| id | true | integer | 主键ID |
| user\_id | true | integer | 用户外键 |
| resume\_id | true | integer | 简历外键 |
| type | true | integer | 类型 |
| talent\_category\_id | true | integer | 职业分类外键 |
| talent\_category\_name | true | string | 职业分类名称 |
| city\_id | true | integer | 城市外键 |
| province\_id | true | integer | 省份外键 |
| min\_salary | true | integer | 最低期望薪资 |
| max\_salary | true | integer | 最高期望薪资 |
| created\_at | true | string | 创建时间 |
| updated\_at | true | string | 更新时间 |

#### License参数

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| id | true | integer | 主键ID |
| user\_id | true | integer | 用户外键 |
| material\_id | true | integer | 素材外键 |
| license\_category\_id | true | integer | 证书分类外键 |
| license\_category\_name | true | string | 证书分类名称 |
| title | true | string | 标题 |
| url | true | string | 附件链接 |
| expire\_at | true | string | 过期时间 |
| has\_verify | true | boolean | 是否验证 |
| created\_at | true | string | 创建时间 |
| updated\_at | true | string | 更新时间 |

## 响应示例

{% tabs %}
{% tab title="正确响应" %}
```javascript
{
    "code": 200,
    "data": {
        "id": 17,
        "user_id": 116,
        "real_name": "憨批黎",
        "birthday": "1960-08-20 00:00:00",
        "eduction": "初中及以下",
        "major": "扫地僧",
        "desc": "孩子测试哭了",
        "status": 1,
        "annex_url": "https://cdn.build-dream.cn/files/Bg8LwaEIHdRX6FcwMc2vPVEzPo5iYD4bZMZxgKT9.jpeg",
        "graduated_at": "2021-01-28 00:00:00",
        "deleted_at": null,
        "created_at": "2018-06-22T11:31:56.000000Z",
        "updated_at": "2021-01-08T03:15:28.000000Z",
        "user": {
            "id": 116,
            "name": "用户v1gU8o",
            "nickname": "昵称AaL9ka",
            "real_name": null,
            "email": "JXKM3f@zzm6.com",
            "phone": "13543859557",
            "avatar": "https://ui-avatars.com/api/用户v1gU8o",
            "email_verified_at": null,
            "phone_verified_at": "2020-12-31 17:57:41",
            "type": 0,
            "status": 1,
            "deleted_at": null,
            "created_at": "2020-12-31T09:57:41.000000Z",
            "updated_at": "2021-01-06T05:19:21.000000Z",
            "rong_cloud_token": "6qqgf7KlVZsAk5O+HIfeCvdJjrZS/iPr4Z8PqpQNyO0=@kee7.cn.rongnav.com;kee7.cn.rongcfg.com"
        },
        "license": [],
        "job_hope": [
            {
                "id": 43,
                "user_id": 116,
                "resume_id": 17,
                "type": 1,
                "talent_category_id": 2,
                "talent_category_name": "交通部",
                "city_id": 110101001,
                "province_id": 0,
                "min_salary": 1000,
                "max_salary": 2000,
                "created_at": "2018-06-22T11:32:58.000000Z",
                "updated_at": "2018-06-22T11:32:58.000000Z",
                "deleted_at": null
            },
            {
                "id": 44,
                "user_id": 116,
                "resume_id": 17,
                "type": 1,
                "talent_category_id": 2,
                "talent_category_name": "暖通空调",
                "city_id": 110101001,
                "province_id": 0,
                "min_salary": 1000,
                "max_salary": 2000,
                "created_at": "2021-01-08T03:16:37.000000Z",
                "updated_at": "2021-01-08T03:16:37.000000Z",
                "deleted_at": null
            },
            {
                "id": 45,
                "user_id": 116,
                "resume_id": 17,
                "type": 1,
                "talent_category_id": 2,
                "talent_category_name": "暖通空调",
                "city_id": 110101001,
                "province_id": 0,
                "min_salary": 1000,
                "max_salary": 2000,
                "created_at": "2021-01-08T03:17:29.000000Z",
                "updated_at": "2021-01-08T03:17:29.000000Z",
                "deleted_at": null
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



