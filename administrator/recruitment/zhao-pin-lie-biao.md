# 招聘列表

## 说明

* 功能说明：获取系统中所有招聘列表接口

## 请求接口

#### 请求地址

* `[host]/api/administrator/recruitment`

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
| id | false | integer | 主键ID |
| title | false | string | 模糊搜索标题 |
| min\_salary | false | integer | 最低期望薪资 |
| max\_salary | false | integer | 最高期望薪资 |
| status | false | integer | 状态 |
| talent\_category\_id | false | integer | 职位分类ID |
| company\_id | false | integer | 公司ID |
| license\_category\_ids | false | integer\[\] | 证书分类ID数组 |
| user\_id | false | integer | 用户ID |
| address\_id | false | integer\[\] | 地址ID数组 |

## 请求示例

{% tabs %}
{% tab title="JavaScript" %}
```javascript
var axios = require('axios');
var data = JSON.stringify({"page":1,"pageSize":5});

var config = {
  method: 'get',
  url: 'http://local.build-dream.cn/api/administrator/recruitment',
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
curl --location --request GET 'http://local.build-dream.cn/api/administrator/recruitment' \
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
GET /api/administrator/recruitment HTTP/1.1
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
| data | false | [Pagination](../jian-li/list.md#pagination-can-shu) | 响应内容 |
| msg | true | string | 响应描述 |

#### Pagination参数

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| current\_page | true | integer | 当前页数 |
| data | true | [Recruitment](zhao-pin-lie-biao.md#recruitment-can-shu)\[\] | 角色数据 |
| per\_page | true | integer | 每页数据条数 |
| total | true | integer | 总数据量 |
| last\_page | true | integer | 总页数 |

#### Recruitment参数

| **参数名** | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| id | true | integer | 主键ID |
| license\_category\_ids | true | integer | 证书分类ID数组 |
| talent\_category\_id | true | integer | 职业分类ID |
| talent\_category\_name | true | string | 职业分类名称 |
| address\_id | true | integer | 地址ID数组 |
| country\_id | true | integer | 区县ID |
| country\_name | true | string | 区县名称 |
| city\_id | true | integer | 城市ID |
| city\_name | true | string | 城市名称 |
| province\_id | true | integer | 省份ID |
| province\_name | true | string | 省份名称 |
| company\_id | true | integer | 公司ID |
| company\_name | true | string | 公司名称 |
| user\_id | true | integer | 用户ID |
| user\_name | true | string | 用户名称 |
| title | true | string | 标题 |
| type | true | integer | 类型 |
| desc | true | string | 描述 |
| work\_time | true | string | 工作时间 |
| min\_salary | true | integer | 最低期望薪资 |
| max\_salary | true | integer | 最高期望薪资 |
| status | true | integer | 状态 |
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
                "id": 69,
                "license_category_ids": [
                    1149
                ],
                "talent_category_id": 1149,
                "talent_category_name": "暖通空调",
                "address_id": [
                    0,
                    0,
                    0
                ],
                "country_id": null,
                "country_name": null,
                "city_id": null,
                "city_name": null,
                "province_id": null,
                "province_name": null,
                "company_id": 1,
                "company_name": "浙江测试股份制有限公司",
                "user_id": 5,
                "user_name": "432591",
                "title": "11111",
                "type": 2,
                "desc": "123123",
                "work_time": "双休",
                "min_salary": 1000,
                "max_salary": 2000,
                "status": 1,
                "updated_at": "2021-01-25T05:56:04.000000Z"
            },
            {
                "id": 68,
                "license_category_ids": [
                    1149
                ],
                "talent_category_id": 1149,
                "talent_category_name": "暖通空调",
                "address_id": [
                    0,
                    0,
                    0
                ],
                "country_id": null,
                "country_name": null,
                "city_id": null,
                "city_name": null,
                "province_id": null,
                "province_name": null,
                "company_id": 1,
                "company_name": "浙江测试股份制有限公司",
                "user_id": 73,
                "user_name": "用户jgaWfI",
                "title": "暖通",
                "type": 2,
                "desc": "测试暖通",
                "work_time": "双休",
                "min_salary": 1000,
                "max_salary": 2000,
                "status": 1,
                "updated_at": "2021-01-08T03:19:12.000000Z"
            },
            {
                "id": 67,
                "license_category_ids": [],
                "talent_category_id": 1151,
                "talent_category_name": "动力",
                "address_id": [
                    0,
                    0,
                    0
                ],
                "country_id": null,
                "country_name": null,
                "city_id": null,
                "city_name": null,
                "province_id": null,
                "province_name": null,
                "company_id": 35,
                "company_name": "浙江易顺带网络科技有限公司",
                "user_id": 39,
                "user_name": "吴国黎",
                "title": "测试岗",
                "type": 2,
                "desc": "别问我，我也不知道",
                "work_time": "双休",
                "min_salary": 1000,
                "max_salary": 7000,
                "status": 1,
                "updated_at": "2020-12-11T07:44:36.000000Z"
            },
            {
                "id": 66,
                "license_category_ids": [],
                "talent_category_id": 1151,
                "talent_category_name": "动力",
                "address_id": [
                    0,
                    0,
                    0
                ],
                "country_id": null,
                "country_name": null,
                "city_id": null,
                "city_name": null,
                "province_id": null,
                "province_name": null,
                "company_id": 35,
                "company_name": "浙江易顺带网络科技有限公司",
                "user_id": 39,
                "user_name": "吴国黎",
                "title": "测试岗",
                "type": 2,
                "desc": "别问我，我也不知道",
                "work_time": "双休",
                "min_salary": 1000,
                "max_salary": 7000,
                "status": 1,
                "updated_at": "2020-12-11T07:44:36.000000Z"
            },
            {
                "id": 65,
                "license_category_ids": [],
                "talent_category_id": 1149,
                "talent_category_name": "暖通空调",
                "address_id": [
                    0,
                    0,
                    0
                ],
                "country_id": null,
                "country_name": null,
                "city_id": null,
                "city_name": null,
                "province_id": null,
                "province_name": null,
                "company_id": 2,
                "company_name": "浙江测试大儿子股份制有限公司",
                "user_id": 5,
                "user_name": "linaqi",
                "title": "1233333",
                "type": 2,
                "desc": "32133333",
                "work_time": "双休",
                "min_salary": 1000,
                "max_salary": 2000,
                "status": 0,
                "updated_at": "2021-01-08T03:40:38.000000Z"
            }
        ],
        "first_page_url": "http://local.build-dream.cn/api/administrator/recruitment?page=1",
        "from": 1,
        "last_page": 12,
        "last_page_url": "http://local.build-dream.cn/api/administrator/recruitment?page=12",
        "links": [
            {
                "url": null,
                "label": "&laquo; 上一页",
                "active": false
            },
            {
                "url": "http://local.build-dream.cn/api/administrator/recruitment?page=1",
                "label": 1,
                "active": true
            },
            {
                "url": "http://local.build-dream.cn/api/administrator/recruitment?page=2",
                "label": 2,
                "active": false
            },
            {
                "url": "http://local.build-dream.cn/api/administrator/recruitment?page=3",
                "label": 3,
                "active": false
            },
            {
                "url": "http://local.build-dream.cn/api/administrator/recruitment?page=4",
                "label": 4,
                "active": false
            },
            {
                "url": "http://local.build-dream.cn/api/administrator/recruitment?page=5",
                "label": 5,
                "active": false
            },
            {
                "url": "http://local.build-dream.cn/api/administrator/recruitment?page=6",
                "label": 6,
                "active": false
            },
            {
                "url": "http://local.build-dream.cn/api/administrator/recruitment?page=7",
                "label": 7,
                "active": false
            },
            {
                "url": "http://local.build-dream.cn/api/administrator/recruitment?page=8",
                "label": 8,
                "active": false
            },
            {
                "url": "http://local.build-dream.cn/api/administrator/recruitment?page=9",
                "label": 9,
                "active": false
            },
            {
                "url": "http://local.build-dream.cn/api/administrator/recruitment?page=10",
                "label": 10,
                "active": false
            },
            {
                "url": "http://local.build-dream.cn/api/administrator/recruitment?page=11",
                "label": 11,
                "active": false
            },
            {
                "url": "http://local.build-dream.cn/api/administrator/recruitment?page=12",
                "label": 12,
                "active": false
            },
            {
                "url": "http://local.build-dream.cn/api/administrator/recruitment?page=2",
                "label": "下一页 &raquo;",
                "active": false
            }
        ],
        "next_page_url": "http://local.build-dream.cn/api/administrator/recruitment?page=2",
        "path": "http://local.build-dream.cn/api/administrator/recruitment",
        "per_page": 5,
        "prev_page_url": null,
        "to": 5,
        "total": 56
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



