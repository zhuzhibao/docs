# 更新用户信息

## 说明

* 功能说明：更新用户信息

## 请求接口

**请求地址**

* `[host]/api/consumer/user/update`

**请求方式**

* `POST`

**请求头Header**

* `Authorization:Bearer {token}` token 为用户授权登陆Token
* `Accept:application/json`

**请求参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| password | true | string | 密码 |
| phone | true | string | 手机号码 |
| nickname | true | string | 昵称 |
| avatar | true | string | 头像地址 |

## 响应接口

**响应Header**

* `Content-Type:application/json`

**响应参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| code | true | integer | HTTP响应代码, 成功返回200 |
| data | false | string | 响应内容 |
| msg | true | string | 响应描述 |

