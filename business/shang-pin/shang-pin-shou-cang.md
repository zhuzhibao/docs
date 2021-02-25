# 商品收藏



## 说明

* 功能说明：商品收藏

## 请求接口

**请求地址**

* `[host]/api/`business`/shop/product/{id}/collect   ID为商品主键`

**请求方式**

* `POST`

**请求头Header**

* `Authorization:Bearer {token}` token 为用户授权登陆Token
* `Accept:application/json`

## 响应接口

**响应Header**

* `Content-Type:application/json`

**响应参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| code | true | integer | HTTP响应代码, 成功返回200 |
| data | false | string | 响应内容 |
| msg | true | string | 响应描述 |

