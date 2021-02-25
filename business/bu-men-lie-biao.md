# 部门列表

**说明**

* 功能说明：获取部门分类列表接口

## 请求接口

#### 请求地址

* `[host]/api/business/department`

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
| data | false | [PermissionLevel](../administrator/hui-yuan-deng-ji/hui-yuan-deng-ji-lie-biao.md#permissionlevel-can-shu)\[\] | 响应内容 |
| msg | true | string | 响应描述 |

#### PermissionLevel参数

| **参数名** | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| id | true | integer | 主键ID |
| company\_id | true | string | 公司ID |
| parent\_id | true | string | 父类ID |
| name | true | string | 部门名称 |
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
            "id": 30,
            "company_id": 1,
            "parent_id": 21,
            "name": "技术部",
            "sort": 0,
            "created_at": null,
            "updated_at": null
        },
        {
            "id": 31,
            "company_id": 1,
            "parent_id": 21,
            "name": "营销部",
            "sort": 0,
            "created_at": null,
            "updated_at": null
        }
    ],
    "msg": "success"
}
```
{% endtab %}
{% endtabs %}

