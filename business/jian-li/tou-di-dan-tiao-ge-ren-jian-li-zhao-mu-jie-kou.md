# 投递单条个人简历招募接口



## 说明

* 功能说明：投递单条个人简历招募接口

## 请求接口

**请求地址**

* `[host]/api/`business`/resume/{id} 主键ID/`delivery

**请求方式**

* `POST`

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

