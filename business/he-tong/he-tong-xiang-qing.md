# 合同详情



## 说明 <a id="&#x8BF4;&#x660E;"></a>

* 功能说明：合同列表

## 请求接口 <a id="&#x8BF7;&#x6C42;&#x63A5;&#x53E3;"></a>

**请求地址**

* `[host]/api/business/contract/1`

**请求方式**

* `GET`

**请求头HEADER**

* `Authorization:Bearer {token}` token 为用户授权登陆Token
* `Accept:application/json`

**请求参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| url | true | string | 文件上传地址 |
| party\_a | true | int | 甲方 |
| party\_b | true | int | 乙方 |
| expire\_at | true | int | 到期时间 |

## 响应接口 <a id="&#x54CD;&#x5E94;&#x63A5;&#x53E3;"></a>

**响应HEADER**

* `Content-Type:application/json`

**响应参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| code | true | integer | HTTP响应代码, 成功返回200 |
| data | false | object | 响应内容 |
| msg | true | string | 响应描述 |



**data参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| title | true | string | 标题 |
| party\_a | true | string | 甲方 |
| party\_b | true | string | 乙方 |
| remark | true | string | 备注 |
| url | true | string | 合同上传地址 |
| expire\_at | true | string | 到期时间 |

