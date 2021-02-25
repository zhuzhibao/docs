# 商品取消收藏



## 说明

* 功能说明：商品取消收藏

## 请求接口

**请求地址**

* `[host]/api/`business`/shop/product/{id}/collect   ID为商品主键`

**请求方式**

* `DELETE`

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

