# 我的求职期望



## 说明 <a id="&#x8BF4;&#x660E;"></a>

* 功能说明：获取我的求职接口

## 请求接口 <a id="&#x8BF7;&#x6C42;&#x63A5;&#x53E3;"></a>

**请求地址**

* `[host]/api/consumer/job-hope`

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

**ITEMS参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| id | true | int | 自增ID |
| user\_id | true | int | 用户ID |
| resume\_id | true | string | 关联简历ID |
| talent\_category\_id | true | string | 分类ID |
| talent\_category\_name | true | string | 分类名称 |
| min\_salary | true | string | 最小工资 |
| max\_salary | true | string | 最大工资 |
| city\_id | true | int | 城市ID |
| deleted\_at | true | date | 删除时间 |
| created\_at | true | date | 创建时间 |
| updated\_at | true | date | 更新时间 |

