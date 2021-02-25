# 用户登陆接口

## 说明

* 功能说明：用户登陆接口

## 请求接口

**请求地址**

* `[host]/api/auth/login`

**请求方式**

* `POST`

**请求头Header**

* `Accept:application/json`

**请求参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| type | true | string | 登陆方式：VERIFICATION\_CODE-验证码登陆 PASSWORD-密码登录 DING\_TALK-钉钉登陆 WECHAT-微信登陆 |
| phone | false | int\(11\) | 手机号码：验证码登陆时必须穿入，密码登录时与邮箱二者选其一 |
| email | false | string | 邮箱地址：密码登录时与手机号码二者选其一 |
| password | false | string | 密码：密码登录时必须传入 |
| verification\_code | false | int | 验证码：验证码登陆时必须传入 |
| code | false | string | 临时授权码：使用微信及钉钉快捷登录时必须传入 |
| state | false | string | 防跨站攻击标识符：使用微信及钉钉快捷登录时必须传入 |
| application\_state | false | string | 验证方式：APP使用钉钉、微信快捷登陆时传入\`application\`，Web使用钉钉、微信快捷登陆时传入\`web\` |

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

