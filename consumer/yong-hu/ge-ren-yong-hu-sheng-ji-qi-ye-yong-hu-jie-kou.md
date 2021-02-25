# 个人用户升级企业用户接口

## 说明

* 功能说明：个人用户升级企业用户接口

## 请求接口

**请求地址**

* `[host]/api/consumer/user/upgrade-business`

**请求方式**

* `POST`

**请求头Header**

* `Authorization:Bearer {token}` token 为用户授权登陆Token
* `Accept:application/json`

**请求参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| company\_name | true | string | 公司名称 |
| company\_logo | true | string | 公司Logo图片地址 |
| company\_desc | true | string | 公司描述 |
| company\_license | true | string | 公司营业执照图片地址 |

## 响应接口

**响应Header**

* `Content-Type:application/json`

**响应参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| code | true | integer | HTTP响应代码, 成功返回200 |
| data | false | string | 响应内容 |
| msg | true | string | 响应描述 |

