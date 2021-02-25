# 获取单条资讯详情接口

## 说明

* 功能说明：获取单条资讯详情接口

## 请求接口

**请求地址**

* `[host]/api/consumer/information/{id}` id 为资讯ID

**请求方式**

* `GET`

**请求头Header**

* `Authorization:Bearer {token}` token 为用户授权登陆Token
* `Accept:application/json`

**请求参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| 无 | 无 | 无 | 无 |

## 响应接口

**响应Header**

* `Content-Type:application/json`

**响应参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| code | true | integer | HTTP响应代码, 成功返回200 |
| data | false | object | 响应内容 |
| msg | true | string | 响应描述 |

**Data参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| id | true | int | 自增ID |
| category\_id | true | int | 分类ID |
| author | true | string | 作者 |
| title | true | string | 标题 |
| thumb | true | string | 缩略图 |
| image | true | string | 完整图 |
| context | true | string | 文章内容（HTML） |
| stars | true | int | 点赞数 |
| status | true | int\(1\) | 状态 |
| deleted\_at | true | date | 删除时间 |
| created\_at | true | date | 创建时间 |
| updated\_at | true | date | 更新时间 |

