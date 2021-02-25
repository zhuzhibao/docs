# 简历详情



## 说明

* 功能说明：查询单个简历接口

## 请求接口

**请求地址**

* `[host]/api/`business`/resume/{id} 主键ID`

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
| id | true | int | 主键 |
| user\_id | true | int | userID |
| real\_name | true | string | 真实姓名 |
| birthday | true | string | 生日 |
| eduction | true | string | 学历 |
| desc | true | string | 自我描述 |
| status | true | int | 状态： 1-正常 0-关闭 |
| job-hope | true | int | 求职期望 |
| graduated\_at | true | date | 毕业时间 |
| created\_at | true | string | 创建时间 |
| updated\_at | true | string | 更新时间 |



**参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| talent\_category\_id | true | int | 人才分类 |
| talent\_category\_name | true | string | 人才分类名称 |
| city\_name | true | string | 求职城市 |
| type | true | int | 0:实习，1：兼职，2：全职，3：校招 |
| min\_salary | true | string | 最低工资 |
| max\_salary | true | string  | 最高工资 |

