# 商品详情

## 说明

* 功能说明：商品列表

## 请求接口

**请求地址**

* `[host]/api/consumer/shop/product/{id}   ID为商品主键`

**请求方式**

* `GET`

**请求头Header**

* `Authorization:Bearer {token}` token 为用户授权登陆Token
* `Accept:application/json`

**请求参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| sold\_order | false | string | 销量排序 |
| price\_order | false | string | 价格排序 desc:倒序，aes:正序 |

**响应Header**

* `Content-Type:application/json`

**响应参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| code | true | integer | HTTP响应代码, 成功返回200 |
| data | false | string | 响应内容 |
| msg | true | string | 响应描述 |

**data参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| id | true | int | 自增ID |
| title | true | int | 商品名称 |
| thumb | true | int | 缩略图 |
| image | true | string | 图像 |
| carousel | true | int | 轮播图 |
| content | true | string | 商品介绍 |
| price | true | int\(1\) | 商品价格 |
| user\_has\_collect | true | bool | 用户是否收藏商品 |
| product\_attr\_value | true | array | 商品sku |
| created\_at | true | date | 创建时间 |
| updated\_at | true | date | 更新时 |

**product\_attr\_value参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| id | true | int | 自增ID |
| product\_id | true | int | 商品id |
| sku | true | int | sku |
| stock | string | int | 库存 |
| sold | true | int | 销量 |
| image | true | string | 图片 |
| price | true | int\(1\) | 价格 |
| created\_at | true | date | 创建时间 |
| updated\_at | true | date | 更新时 |

