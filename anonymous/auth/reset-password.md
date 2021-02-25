# 用户重置密码接口

## 说明

* 功能说明：用户重置密码接口

## 请求接口

**请求地址**

* `[host]/api/auth/reset-password`

**请求方式**

* `POST`

**请求头Header**

* `Accept:application/json`

**请求参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| phone | false | int\(11\) | 手机号码 |
| password | false | string | 密码 |
| verification\_code | false | int | 验证码 |

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
| token | true | string | 认证Token |
| role | true | string | 用户角色 |

