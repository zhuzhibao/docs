# 获取单条招聘详情接口



## 说明

* 功能说明：获取单条招聘详情

## 请求接口

**请求地址**

* `[host]/api/`business/recruitment/{id} 主键ID

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

**data参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| id | true | int | 自增ID |
| talent\_category\_id | true | int | 分类ID |
| company\_id | true | int | 公司ID |
| company\_name | true | string | 公司名称 |
| user\_id | true | int | 用户ID |
| user\_name | true | string | 用户名称 |
| street\_id | true | int | 街道ID |
| title | true | string | 招聘标题 |
| desc | true | string | 招聘内容（HTML） |
| type | true | int | 招聘类型 |
| min\_salary | true | int | 最低薪资 |
| max\_salary | true | int | 最高薪资 |
| work\_time | true | string | 工作时间 |
| status | true | int\(1\) | 状态 |
| deleted\_at | true | date | 删除时间 |
| created\_at | true | date | 创建时间 |
| updated\_at | true | date | 更新时间 |

|  |
| :---: |


