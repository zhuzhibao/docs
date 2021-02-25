# 商品列表

## 说明

* 功能说明：商品列表

## 请求接口

**请求地址**

* `[host]/api/consumer/shop/product`

**请求方式**

* `GET`

**请求头Header**

* `Authorization:Bearer {token}` token 为用户授权登陆Token
* `Accept:application/json`

**请求参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| category\_id | false | string | 分类ID |
| product\_keyword | false | string | 商品关键字 |

## 响应接口

**响应Header**

* `Content-Type:application/json`

**响应参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| code | true | integer | HTTP响应代码, 成功返回200 |
| data | false | string | 响应内容 |
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
| title | true | int | 商品名称 |
| thumb | true | int | 缩略图 |
| image | true | string | 图像 |
| carousel | true | int | 轮播图 |
| content | true | string | 商品介绍 |
| price | true | int\(1\) | 商品价格 |
| created\_at | true | date | 创建时间 |
| updated\_at | true | date | 更新时间 |

