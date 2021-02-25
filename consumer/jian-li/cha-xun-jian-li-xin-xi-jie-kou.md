# 查询简历信息接口

## 说明

* 功能说明：查询简历信息接口

## 请求接口

**请求地址**

* `[host]/api/consumer/resume`

**请求方式**

* `GET`

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

**Data参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| talent\_category\_id | true | int | 人才职业分类ID |
| talent\_category\_name | true | string | 人才职业分类名 |
| street\_id | true | int | 街道ID |
| street\_name | true | string | 街道名 |
| country\_id | true | int | 区县ID |
| country\_name | true | string | 区县名 |
| city\_id | true | int | 城市ID |
| city\_name | true | string | 城市名 |
| province\_id | true | int | 省份ID |
| province\_name | true | string | 省份名 |
| real\_name | true | string | 真实姓名 |
| birthday | true | string | 生日 |
| eduction | true | string | 学历 |
| min\_salary | true | int | 最低期望薪资 |
| max\_salary | true | int | 最高期望薪资 |
| desc | true | string | 自我描述 |
| status | true | int | 状态： 1-正常 0-关闭 |
| created\_at | true | string | 创建时间 |
| updated\_at | true | string | 更新时间 |

