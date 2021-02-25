# 公司列表

## 说明

* 功能说明：获取系统中所有公司列表接口

## 请求接口

#### 请求地址

* `[host]/api/administrator/company`

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
| name | false | string | 模糊搜索公司名称 |
| has\_verify | false | integer | 是否验证 |

## 请求示例

{% tabs %}
{% tab title="JavaScript" %}
```javascript
var axios = require('axios');
var data = JSON.stringify({"page":1,"pageSize":5});

var config = {
  method: 'get',
  url: 'http://local.build-dream.cn/api/administrator/company',
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
curl --location --request GET 'http://local.build-dream.cn/api/administrator/company' \
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
GET /api/administrator/company HTTP/1.1
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
| data | true | [Company](gong-si-lie-biao.md#company-can-shu)\[\] | 角色数据 |
| per\_page | true | integer | 每页数据条数 |
| total | true | integer | 总数据量 |
| last\_page | true | integer | 总页数 |

#### Company参数

| **参数名** | 是否必填 | 数据类型 | 字段说明 |
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
| address\_id | true | integer\[\] | 地址ID数组 |
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
                "id": 42,
                "service_company_id": 0,
                "name": "杭州南杭网络科技有限公司",
                "logo_material_id": 41,
                "logo": "https://cdn.build-dream.cn/FqjZXN-frMIm5R-DVIS5FOfx6xd4",
                "images": null,
                "desc": "杭州南杭网络科技有限公司",
                "license_material_id": 9,
                "license": "https://cdn.build-dream.cn/FhqrVxzpIcX5jTossXTT-ZGGca6C",
                "province_id": 11,
                "province_name": "浙江省",
                "city_id": 87,
                "city_name": "杭州市",
                "country_id": 876,
                "country_name": "江干区",
                "permission_level_id": 4,
                "permission_level_name": "钻石会员",
                "has_verify": true,
                "deleted_at": null,
                "created_at": "2020-12-07T09:43:12.000000Z",
                "updated_at": "2020-12-07T09:43:12.000000Z",
                "address_id": [
                    11,
                    87,
                    876
                ]
            },
            {
                "id": 41,
                "service_company_id": 0,
                "name": "杭州大大大大大地好建设有限公司",
                "logo_material_id": 0,
                "logo": "https://ui-avatars.com/api/杭州大大大大大地好建设有限公司",
                "images": null,
                "desc": "测试公司1",
                "license_material_id": 0,
                "license": "",
                "province_id": 11,
                "province_name": "浙江省",
                "city_id": 87,
                "city_name": "杭州市",
                "country_id": 881,
                "country_name": "余杭区",
                "permission_level_id": 1,
                "permission_level_name": "铜牌会员",
                "has_verify": true,
                "deleted_at": null,
                "created_at": "2020-11-13T06:28:22.000000Z",
                "updated_at": "2020-11-13T06:28:22.000000Z",
                "address_id": [
                    11,
                    87,
                    881
                ]
            },
            {
                "id": 40,
                "service_company_id": 0,
                "name": "杭州大大大大地好建设有限公司",
                "logo_material_id": 0,
                "logo": "https://ui-avatars.com/api/杭州大大大大地好建设有限公司",
                "images": null,
                "desc": "测试公司1",
                "license_material_id": 0,
                "license": "",
                "province_id": 11,
                "province_name": "浙江省",
                "city_id": 87,
                "city_name": "杭州市",
                "country_id": 881,
                "country_name": "余杭区",
                "permission_level_id": 1,
                "permission_level_name": "铜牌会员",
                "has_verify": true,
                "deleted_at": null,
                "created_at": "2020-11-13T05:43:12.000000Z",
                "updated_at": "2020-11-13T05:43:12.000000Z",
                "address_id": [
                    11,
                    87,
                    881
                ]
            },
            {
                "id": 39,
                "service_company_id": 0,
                "name": "杭州大大大地好建设有限公司",
                "logo_material_id": 0,
                "logo": "https://ui-avatars.com/api/杭州大大大地好建设有限公司",
                "images": null,
                "desc": "测试公司1",
                "license_material_id": 0,
                "license": "",
                "province_id": 11,
                "province_name": "浙江省",
                "city_id": 87,
                "city_name": "杭州市",
                "country_id": 881,
                "country_name": "余杭区",
                "permission_level_id": 1,
                "permission_level_name": "铜牌会员",
                "has_verify": true,
                "deleted_at": null,
                "created_at": "2020-11-13T05:41:29.000000Z",
                "updated_at": "2020-11-13T05:41:29.000000Z",
                "address_id": [
                    11,
                    87,
                    881
                ]
            },
            {
                "id": 38,
                "service_company_id": 0,
                "name": "杭州大大地好建设有限公司",
                "logo_material_id": 0,
                "logo": "https://ui-avatars.com/api/杭州大大地好建设有限公司",
                "images": null,
                "desc": "测试公司1",
                "license_material_id": 0,
                "license": "",
                "province_id": 11,
                "province_name": "浙江省",
                "city_id": 87,
                "city_name": "杭州市",
                "country_id": 881,
                "country_name": "余杭区",
                "permission_level_id": 1,
                "permission_level_name": "铜牌会员",
                "has_verify": true,
                "deleted_at": null,
                "created_at": "2020-11-13T05:35:07.000000Z",
                "updated_at": "2020-11-13T05:35:07.000000Z",
                "address_id": [
                    11,
                    87,
                    881
                ]
            }
        ],
        "first_page_url": "http://local.build-dream.cn/api/administrator/company?page=1",
        "from": 1,
        "last_page": 9,
        "last_page_url": "http://local.build-dream.cn/api/administrator/company?page=9",
        "links": [
            {
                "url": null,
                "label": "&laquo; 上一页",
                "active": false
            },
            {
                "url": "http://local.build-dream.cn/api/administrator/company?page=1",
                "label": 1,
                "active": true
            },
            {
                "url": "http://local.build-dream.cn/api/administrator/company?page=2",
                "label": 2,
                "active": false
            },
            {
                "url": "http://local.build-dream.cn/api/administrator/company?page=3",
                "label": 3,
                "active": false
            },
            {
                "url": "http://local.build-dream.cn/api/administrator/company?page=4",
                "label": 4,
                "active": false
            },
            {
                "url": "http://local.build-dream.cn/api/administrator/company?page=5",
                "label": 5,
                "active": false
            },
            {
                "url": "http://local.build-dream.cn/api/administrator/company?page=6",
                "label": 6,
                "active": false
            },
            {
                "url": "http://local.build-dream.cn/api/administrator/company?page=7",
                "label": 7,
                "active": false
            },
            {
                "url": "http://local.build-dream.cn/api/administrator/company?page=8",
                "label": 8,
                "active": false
            },
            {
                "url": "http://local.build-dream.cn/api/administrator/company?page=9",
                "label": 9,
                "active": false
            },
            {
                "url": "http://local.build-dream.cn/api/administrator/company?page=2",
                "label": "下一页 &raquo;",
                "active": false
            }
        ],
        "next_page_url": "http://local.build-dream.cn/api/administrator/company?page=2",
        "path": "http://local.build-dream.cn/api/administrator/company",
        "per_page": 5,
        "prev_page_url": null,
        "to": 5,
        "total": 42
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



