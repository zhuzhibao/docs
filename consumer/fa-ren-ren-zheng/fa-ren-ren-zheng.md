# 法人认证



说明

* 功能说明：法人认证

## 请求接口 <a id="&#x8BF7;&#x6C42;&#x63A5;&#x53E3;"></a>

**请求地址**

* `[host]/api/consumer/`corporate/approve

**请求方式**

* `POST`

**请求头HEADER**

* `Authorization:Bearer {token}` token 为用户授权登陆Token
* `Accept:application/json`

**请求参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| user\_name | 是 | string | 申请用户名称 |
| company\_name | 是 | string | 公司名称 |
| company\_id | 是 | int | 公司ID |
| url | 是 | string | 营业执照上传地址 |
| credit\_code | 是 | string | 信用代码 |

## 响应接口 <a id="&#x54CD;&#x5E94;&#x63A5;&#x53E3;"></a>

**响应HEADER**

* `Content-Type:application/json`

**响应参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| code | true | integer | HTTP响应代码, 成功返回200 |
| data | false | string | 响应内容 |
| msg | true | string | 响应描述 |

