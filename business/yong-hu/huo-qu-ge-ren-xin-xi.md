# 获取个人信息



## 说明 <a id="&#x8BF4;&#x660E;"></a>

* 功能说明：获取个人信息接口

## 请求接口 <a id="&#x8BF7;&#x6C42;&#x63A5;&#x53E3;"></a>

**请求地址**

* `[host]/api/consumer/user/info`

**请求方式**

* `GET`

**请求头HEADER**

* `Authorization:Bearer {token}` token 为用户授权登陆Token
* `Accept:application/json`

## 响应接口 <a id="&#x54CD;&#x5E94;&#x63A5;&#x53E3;"></a>

**响应HEADER**

* `Content-Type:application/json`

**响应参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| code | true | integer | HTTP响应代码, 成功返回200 |
| data | false | object | 响应内容 |
| msg | true | string | 响应描述 |

**DATA参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| items | true | array | 子数据列表数组 |
| has\_more | true | bool | 是否还有下一页 |

**ITEMS参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| id | true | int | 自增ID |
| name | true | int | 姓名 |
| nickname | true | int | 用户昵称 |
| email | true | string | 邮箱 |
| phone | true | int | 手机号码 |
| avatar | true | string | 头像 |
| status | true | int\(1\) | 状态 |
| menu | true | array\) | 权限菜单 |
| menu.icon | true | string\) | 菜单icon |
| menu.url | true | string\) | 菜单跳转地址 |
| created\_at | true | date | 创建时间 |
| updated\_at | true | date | 更新时间 |

