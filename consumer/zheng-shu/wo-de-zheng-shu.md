# 我的证书



## 说明 <a id="&#x8BF4;&#x660E;"></a>

* 功能说明：获取资讯列表接口

## 请求接口 <a id="&#x8BF7;&#x6C42;&#x63A5;&#x53E3;"></a>

**请求地址**

* `[host]/api/consumer/`certificate

**请求方式**

* `GET`

**请求头HEADER**

* `Authorization:Bearer {token}` token 为用户授权登陆Token
* `Accept:application/json`

**请求参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| page | false | int | 页数 |
| pageSize | false | int | 页码, 默认为20条数据每页 |
| query | false | object | 查询数据 |

**QUERY参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |


## 响应接口 <a id="&#x54CD;&#x5E94;&#x63A5;&#x53E3;"></a>

**响应HEADER**

* `Content-Type:application/json`

**响应参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| code | true | integer | HTTP响应代码, 成功返回200 |
| data | false | object | 响应内容 |
| msg | true | string | 响应描述 |

**DATA参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| items | true | array | 子数据列表数组 |
| has\_more | true | bool | 是否还有下一页 |

#### **ITEMS参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| id | true | int | 自增ID |
| user\_id | true | int | 用户ID |
| license\_category\_id | true | int | 证书分类ID |
| license\_category\_name | string | string | 证书分类名称 |
| title | true | string | 证书标题 |
| url | true | string | 证书上传地址 |
| expire\_at | true | string | 到期时间 |
| has\_verify | truei | int | 是否验证 |
| category | true | array | 证书详情 |
| deleted\_at | true | date | 删除时间 |
| created\_at | true | date | 创建时间 |
| updated\_at | true | date | 更新时间 |



#### category**参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| id | true | int | 自增ID |
| name | true | string | 证书分类名称 |
| image | int | string | 证书图片 |

