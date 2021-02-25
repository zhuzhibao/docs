# 人才职业分类

**说明**

* 功能说明：获取人才分类列表接口

## 请求接口

#### 请求地址

* `[host]/api/business/talent-category`

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
  url: 'http://local.build-dream.cn/api/administrator/permission-level',
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
curl --location --request GET 'http://local.build-dream.cn/api/administrator/permission-level' \
--header 'Authorization: Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE' \
--header 'Accept: application/json' \
--header 'Cookie: PHPSESSID=171eee4ecf83ae527a5416c47ec3bf7f' \
--data-raw ''
```
{% endtab %}

{% tab title="HTTP" %}
```http
GET /api/administrator/permission-level HTTP/1.1
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
| data | false | items\[\] | 响应内容 |
| msg | true | string | 响应描述 |

#### PermissionLevel参数

| **参数名** | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| id | true | integer | 主键ID |
| name | true | string | 人才名称  |
| parent\_id | true | string | 父类ID |
| image | true | string | 图片链接 |
| child | true | array | 子集（结构同父级） |
| created\_at | true | string | 创建时间 |
| updated\_at | true | string | 更新时间 |

## 响应示例

{% tabs %}
{% tab title="正确响应" %}
```javascript
{
    "code": 200,
    "data": {
        "items": [
            {
                "id": 1148,
                "parent_id": 0,
                "material_id": 9,
                "name": "公用设备工程师",
                "thumb": "https://cdn.build-dream.cn/FhqrVxzpIcX5jTossXTT-ZGGca6C",
                "image": "https://cdn.build-dream.cn/FhqrVxzpIcX5jTossXTT-ZGGca6C",
                "status": 1,
                "deleted_at": null,
                "created_at": "2020-11-19T01:22:02.000000Z",
                "updated_at": "2020-11-19T01:22:02.000000Z",
                "children": [
                    {
                        "id": 1149,
                        "parent_id": 1148,
                        "material_id": 9,
                        "name": "暖通空调",
                        "thumb": "https://cdn.build-dream.cn/FhqrVxzpIcX5jTossXTT-ZGGca6C",
                        "image": "https://cdn.build-dream.cn/FhqrVxzpIcX5jTossXTT-ZGGca6C",
                        "status": 1,
                        "deleted_at": null,
                        "created_at": "2020-11-19T01:22:02.000000Z",
                        "updated_at": "2020-11-19T01:22:02.000000Z",
                        "children": []
                    },
                    {
                        "id": 1150,
                        "parent_id": 1148,
                        "material_id": 9,
                        "name": "给水排水",
                        "thumb": "https://cdn.build-dream.cn/FhqrVxzpIcX5jTossXTT-ZGGca6C",
                        "image": "https://cdn.build-dream.cn/FhqrVxzpIcX5jTossXTT-ZGGca6C",
                        "status": 1,
                        "deleted_at": null,
                        "created_at": "2020-11-19T01:22:02.000000Z",
                        "updated_at": "2020-11-19T01:22:02.000000Z",
                        "children": []
                    },
                    {
                        "id": 1151,
                        "parent_id": 1148,
                        "material_id": 9,
                        "name": "动力",
                        "thumb": "https://cdn.build-dream.cn/FhqrVxzpIcX5jTossXTT-ZGGca6C",
                        "image": "https://cdn.build-dream.cn/FhqrVxzpIcX5jTossXTT-ZGGca6C",
                        "status": 1,
                        "deleted_at": null,
                        "created_at": "2020-11-19T01:22:02.000000Z",
                        "updated_at": "2020-11-19T01:22:02.000000Z",
                        "children": []
                    }
                ]
            }
        }
    }
```
{% endtab %}
{% endtabs %}

