# 课程详情



## 说明 <a id="&#x8BF4;&#x660E;"></a>

* 功能说明：课程详情

## 请求接口 <a id="&#x8BF7;&#x6C42;&#x63A5;&#x53E3;"></a>

**请求地址**

* `[host]`/api/consumer/course-category/{id}  id为课程ID

**请求方式**

* GET

**请求头HEADER**

* `Authorization:Bearer {token}` token 为用户授权登陆Token
* `Accept:application/json`

**请求参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| page | false | int | 页数 |
| pageSize | false | int | 页码, 默认为20条数据每页 |

## 响应接口 <a id="&#x54CD;&#x5E94;&#x63A5;&#x53E3;"></a>

**响应HEADER**

* `Content-Type:application/json`

**响应参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| code | true | integer | HTTP响应代码, 成功返回200 |
| data | false | object | 响应内容 |
| msg | true | string | 响应描述 |



**data参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| id | true | int | 自增ID |
| course\_category\_id | true | int | 课程分类ID |
| teacher\_user\_id | int | string | 讲师用户ID |
| teacher\_user\_name | true | string | 讲师 |
| teacher\_header\_image | true | string | 讲师头像地址 |
| image | true | string | 图片地址 |
| price | true | string | 价格 |
| sold | true | string | 已售 |
| total\_episode | true | string | 总章节 |
| teacher\_company | true | string | 讲师公司名称 |
| user\_has\_collect | true | bool | 是否收藏 |
| user\_has\_pay | true | bool | 是否支付 |
| episodes | true | array | 章节 |



episodes**参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| id | true | int | 自增ID |
| name | true | string | 章节名称 |
| url | true | string | 视频地址 |
| time | true | string | 时间 |

