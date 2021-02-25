# 联系我们记录



说明

* 功能说明：联系我们

## 请求接口 <a id="&#x8BF7;&#x6C42;&#x63A5;&#x53E3;"></a>

**请求地址**

* `[host]/api/consumer/`consumer/contact/us

**请求方式**

* `GET`

**请求头HEADER**

* `Authorization:Bearer {token}` token 为用户授权登陆Token
* `Accept:application/json`

\*\*\*\*

## 响应接口 <a id="&#x54CD;&#x5E94;&#x63A5;&#x53E3;"></a>

**响应HEADER**

* `Content-Type:application/json`

**响应参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| code | true | integer | HTTP响应代码, 成功返回200 |
| data | false | string | 响应内容 |
| msg | true | string | 响应描述 |



**data参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| id | true | integer | id  |
| user\_id | true | string | 用户ID |
| user\_name | true | string | 用户名称 |
| phone | true | string | 手机号码 |
| company\_name | true | string | 公司名 |
| remark | true | string | 备注 |

