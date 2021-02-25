# 资讯列表



## 说明

* 功能说明：获取资讯分类列表接口

## 请求接口

**请求地址**

* `[host]/api/`business`/information-category`

**请求方式**

* `GET`

**请求头Header**

* `Authorization:Bearer {token}` token 为用户授权登陆Token
* `Accept:application/json`

**请求参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| page | false | int | 页数 |
| pageSize | false | int | 页码, 默认为20条数据每页 |

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
| items | true | array | 子数据列表数组 |
| has\_more | true | bool | 是否还有下一页 |

**Items参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| id | true | int | 自增ID |
| parent\_id | true | int | 父ID |
| name | true | string | 分类名称 |
| thumb | true | string | 缩略图 |
| image | true | string | 完整图 |
| status | true | int\(1\) | 状态 |
| deleted\_at | true | date | 删除时间 |
| created\_at | true | date | 创建时间 |
| updated\_at | true | date | 更新时 |

