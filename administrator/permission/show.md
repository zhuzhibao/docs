# 权限详情

## 说明

* 功能说明：获取系统中指定权限详情接口

## 请求接口

#### 请求地址

* `[host]/api/administrator/permission/{id}`
* `id` 为 Permission ID

#### **请**求方式

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
  url: 'http://local.build-dream.cn/api/administrator/permission/1693',
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
curl --location --request GET 'http://local.build-dream.cn/api/administrator/permission/1693' \
--header 'Authorization: Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE' \
--header 'Accept: application/json' \
--header 'Cookie: PHPSESSID=171eee4ecf83ae527a5416c47ec3bf7f' \
--data-raw ''
```
{% endtab %}

{% tab title="HTTP" %}
```http
GET /api/administrator/permission/1693 HTTP/1.1
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
| data | false | [Permission](show.md#permission-can-shu) | 响应内容 |
| msg | true | string | 响应描述 |

#### Permission参数 <a id="permission-can-shu"></a>

| **参数名** | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| id | true | integer | 主键ID |
| parent\_id | true | integer | 父权限主键ID, 为0时无父权限 |
| name | true | string | 权限标示 |
| key | true | integer | 键，同主键ID |
| value | true | string | 值，同权限标示 |
| title | true | string | 权限展示标题 |
| children | false | [Permission](show.md#permission-can-shu)\[\] | 子权限，数据结构父权限 |

## 响应示例

{% tabs %}
{% tab title="正确响应" %}
```javascript
{
    "code": 200,
    "data": {
        "id": 1693,
        "parent_id": 0,
        "name": "resume",
        "key": 1693,
        "value": "resume",
        "title": "简历管理",
        "children": [
            {
                "id": 1694,
                "parent_id": 1693,
                "name": "resume.viewAny",
                "key": 1694,
                "value": "resume.viewAny",
                "title": "查询"
            },
            {
                "id": 1695,
                "parent_id": 1693,
                "name": "resume.view",
                "key": 1695,
                "value": "resume.view",
                "title": "详细"
            },
            {
                "id": 1696,
                "parent_id": 1693,
                "name": "resume.create",
                "key": 1696,
                "value": "resume.create",
                "title": "新增"
            },
            {
                "id": 1697,
                "parent_id": 1693,
                "name": "resume.update",
                "key": 1697,
                "value": "resume.update",
                "title": "修改"
            },
            {
                "id": 1698,
                "parent_id": 1693,
                "name": "resume.delete",
                "key": 1698,
                "value": "resume.delete",
                "title": "删除"
            },
            {
                "id": 1699,
                "parent_id": 1693,
                "name": "resume.restore",
                "key": 1699,
                "value": "resume.restore",
                "title": "恢复"
            },
            {
                "id": 1700,
                "parent_id": 1693,
                "name": "resume.forceDelete",
                "key": 1700,
                "value": "resume.forceDelete",
                "title": "强制删除"
            },
            {
                "id": 1701,
                "parent_id": 1693,
                "name": "resume.delivery",
                "key": 1701,
                "value": "resume.delivery",
                "title": "投递"
            }
        ]
    },
    "msg": "success"
}
```
{% endtab %}
{% endtabs %}

