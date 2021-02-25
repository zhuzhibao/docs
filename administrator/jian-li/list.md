# 简历列表

## 说明

* 功能说明：获取系统中所有简历列表接口

## 请求接口

#### 请求地址

* `[host]/api/administrator/resume`

#### 请求方式

* `GET`

#### 请求头Header

* `Authorization:Bearer {token}` token 为用户授权登陆Token
* `Accept:application/json`

#### 请求参数

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| page | false | integer | 页数 |
| pageSize | false | integer | 页码，默认20条数据每页 |

## 请求示例

{% tabs %}
{% tab title="JavaScript" %}
```javascript
var axios = require('axios');
var data = JSON.stringify({"page":1,"pageSize":5});

var config = {
  method: 'get',
  url: 'http://local.build-dream.cn/api/administrator/resume',
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
curl --location --request GET 'http://local.build-dream.cn/api/administrator/resume' \
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
GET /api/administrator/resume HTTP/1.1
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
| data | false | [Pagination](list.md#pagination-can-shu) | 响应内容 |
| msg | true | string | 响应描述 |

#### Pagination参数

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| current\_page | true | integer | 当前页数 |
| data | true | [Resume](list.md#resume-can-shu)\[\] | 角色数据 |
| per\_page | true | integer | 每页数据条数 |
| total | true | integer | 总数据量 |
| last\_page | true | integer | 总页数 |

#### Resume参数

| **参数名** | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| id | true | integer | 主键ID |
| real\_name | true | string | 真实姓名 |
| birthday | true | string | 生日 |
| eduction | true | string | 教育程度 |
| major | true | string | 专业 |
| job\_hope | true | [JobHope](list.md#jobhope-can-shu)\[\] | 职位期望 |
| license | true | [License](list.md#license-can-shu)\[\] | 证书 |
| desc | true | string | 描述 |
| status | true | integer | 状态 |
| annex\_url | true | string | 附件链接 |
| graduated\_at | true | string | 毕业时间 |
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
        "current_page": 1,
        "data": [
            {
                "id": 19,
                "real_name": "",
                "birthday": null,
                "eduction": "",
                "major": null,
                "job_hope": [
                    {
                        "id": 46,
                        "user_id": 103,
                        "resume_id": 19,
                        "type": 1,
                        "talent_category_id": 1,
                        "talent_category_name": "安全员",
                        "city_id": 330103006,
                        "province_id": 0,
                        "min_salary": 3000,
                        "max_salary": 5000,
                        "created_at": "2021-01-08T10:20:27.000000Z",
                        "updated_at": "2021-01-08T10:20:27.000000Z",
                        "deleted_at": null
                    }
                ],
                "license": [
                    {
                        "id": 4,
                        "user_id": 103,
                        "material_id": 0,
                        "license_category_id": 1149,
                        "license_category_name": "暖通空调",
                        "title": "暖通空调",
                        "url": "https://sss",
                        "expire_at": "0000-00-00 00:00:00",
                        "has_verify": false,
                        "deleted_at": null,
                        "created_at": "2021-01-04T05:43:02.000000Z",
                        "updated_at": "2021-01-04T05:43:02.000000Z"
                    }
                ],
                "desc": "",
                "status": 1,
                "annex_url": null,
                "graduated_at": null,
                "created_at": "2021-01-08T10:20:27.000000Z",
                "updated_at": "2021-01-08T10:20:27.000000Z"
            },
            {
                "id": 18,
                "real_name": "王亚杰测试",
                "birthday": null,
                "eduction": "博士",
                "major": "计算机",
                "job_hope": [],
                "license": [],
                "desc": "好好好",
                "status": 1,
                "annex_url": "http://cdn.build-dream.cn/files/Acv8ldwOwVYrfmiESoKXUyIXlap8HGjml4nkjJgz.jpeg",
                "graduated_at": "2021-01-08 00:00:00",
                "created_at": "2021-01-08T06:47:52.000000Z",
                "updated_at": "2021-01-08T06:47:52.000000Z"
            },
            {
                "id": 17,
                "real_name": "憨批黎",
                "birthday": "1960-08-20 00:00:00",
                "eduction": "初中及以下",
                "major": "扫地僧",
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
                ],
                "license": [],
                "desc": "孩子测试哭了",
                "status": 1,
                "annex_url": "https://cdn.build-dream.cn/files/Bg8LwaEIHdRX6FcwMc2vPVEzPo5iYD4bZMZxgKT9.jpeg",
                "graduated_at": "2021-01-28 00:00:00",
                "created_at": "2018-06-22T11:31:56.000000Z",
                "updated_at": "2021-01-08T03:15:28.000000Z"
            },
            {
                "id": 16,
                "real_name": "杨龙",
                "birthday": null,
                "eduction": "中转/中技",
                "major": "给排水",
                "job_hope": [
                    {
                        "id": 40,
                        "user_id": 97,
                        "resume_id": 16,
                        "type": 1,
                        "talent_category_id": 2,
                        "talent_category_name": "土建",
                        "city_id": 110101001,
                        "province_id": 0,
                        "min_salary": 1000,
                        "max_salary": 2000,
                        "created_at": "2020-12-07T06:16:17.000000Z",
                        "updated_at": "2020-12-07T06:16:17.000000Z",
                        "deleted_at": null
                    },
                    {
                        "id": 41,
                        "user_id": 97,
                        "resume_id": 16,
                        "type": 1,
                        "talent_category_id": 1,
                        "talent_category_name": "建筑工程",
                        "city_id": 330102001,
                        "province_id": 0,
                        "min_salary": 1000,
                        "max_salary": 2000,
                        "created_at": "2020-12-07T06:17:16.000000Z",
                        "updated_at": "2020-12-07T06:17:16.000000Z",
                        "deleted_at": null
                    },
                    {
                        "id": 42,
                        "user_id": 97,
                        "resume_id": 16,
                        "type": 1,
                        "talent_category_id": 2,
                        "talent_category_name": "建筑工程",
                        "city_id": 330102001,
                        "province_id": 0,
                        "min_salary": 1000,
                        "max_salary": 2000,
                        "created_at": "2020-12-08T10:25:41.000000Z",
                        "updated_at": "2020-12-08T10:25:41.000000Z",
                        "deleted_at": null
                    }
                ],
                "license": [],
                "desc": "版本测试",
                "status": 1,
                "annex_url": "https://cdn.build-dream.cn/files/Bg8LwaEIHdRX6FcwMc2vPVEzPo5iYD4bZMZxgKT9.jpeg",
                "graduated_at": "2019-09-19 00:00:00",
                "created_at": "2020-12-07T06:16:17.000000Z",
                "updated_at": "2020-12-07T06:16:17.000000Z"
            },
            {
                "id": 15,
                "real_name": "杨龙",
                "birthday": null,
                "eduction": "中转/中技",
                "major": "给排水",
                "job_hope": [
                    {
                        "id": 39,
                        "user_id": 76,
                        "resume_id": 15,
                        "type": 1,
                        "talent_category_id": 2,
                        "talent_category_name": "动力",
                        "city_id": 110101001,
                        "province_id": 0,
                        "min_salary": 1000,
                        "max_salary": 2000,
                        "created_at": "2020-12-04T08:18:31.000000Z",
                        "updated_at": "2020-12-04T08:18:31.000000Z",
                        "deleted_at": null
                    }
                ],
                "license": [],
                "desc": "版本测试版本测试",
                "status": 1,
                "annex_url": "https://cdn.build-dream.cn/files/Bg8LwaEIHdRX6FcwMc2vPVEzPo5iYD4bZMZxgKT9.jpeg",
                "graduated_at": "2019-09-19 00:00:00",
                "created_at": "2020-12-07T06:15:23.000000Z",
                "updated_at": "2020-12-07T06:19:12.000000Z"
            }
        ],
        "first_page_url": "http://local.build-dream.cn/api/administrator/resume?page=1",
        "from": 1,
        "last_page": 3,
        "last_page_url": "http://local.build-dream.cn/api/administrator/resume?page=3",
        "links": [
            {
                "url": null,
                "label": "&laquo; 上一页",
                "active": false
            },
            {
                "url": "http://local.build-dream.cn/api/administrator/resume?page=1",
                "label": 1,
                "active": true
            },
            {
                "url": "http://local.build-dream.cn/api/administrator/resume?page=2",
                "label": 2,
                "active": false
            },
            {
                "url": "http://local.build-dream.cn/api/administrator/resume?page=3",
                "label": 3,
                "active": false
            },
            {
                "url": "http://local.build-dream.cn/api/administrator/resume?page=2",
                "label": "下一页 &raquo;",
                "active": false
            }
        ],
        "next_page_url": "http://local.build-dream.cn/api/administrator/resume?page=2",
        "path": "http://local.build-dream.cn/api/administrator/resume",
        "per_page": 5,
        "prev_page_url": null,
        "to": 5,
        "total": 13
    },
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



