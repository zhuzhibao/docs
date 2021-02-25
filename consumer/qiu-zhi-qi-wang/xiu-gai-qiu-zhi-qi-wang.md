# 修改求职期望



## 说明 <a id="&#x8BF4;&#x660E;"></a>

* 功能说明：修改求职期望

## 请求接口 <a id="&#x8BF7;&#x6C42;&#x63A5;&#x53E3;"></a>

**请求地址**

* `[host]/api/consumer/job-hope/{id} 修改记录ID`

**请求方式**

* `PUT`

**请求头HEADER**

* `Authorization:Bearer {token}` token 为用户授权登陆Token
* `Accept:application/json`

**请求参数**

| talent\_category\_id | 是 | int | 人才分类ID |
| :--- | :--- | :--- | :--- |
| talent\_category\_name | 否 | string | 人才分类名称 |
| city\_id | 否 | int | 城市ID |
| min\_salary | 否 | int | 最小工资 |
| max\_salary | 否 | int | 最大工资 |
| type | 否 | int | 类型 |

## 响应接口 <a id="&#x54CD;&#x5E94;&#x63A5;&#x53E3;"></a>

**响应HEADER**

* `Content-Type:application/json`

**响应参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :--- | :--- | :--- | :--- |
| code | true | integer | HTTP响应代码, 成功返回200 |
| data | false | string | 响应内容 |
| msg | true | string | 响应描述 |

