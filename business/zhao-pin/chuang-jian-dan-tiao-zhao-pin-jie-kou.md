# 创建单条招聘接口



## 说明

* 功能说明：创建单条招聘接口

## 请求接口

**请求地址**

* `[host]/api/`business/recruitment

**请求方式**

* `POST`

**请求头Header**

* `Authorization:Bearer {token}` token 为用户授权登陆Token
* `Accept:application/json`

**请求参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| talent\_category\_id | true | int | 分类ID |
| province\_id | true | int | 省份ID |
| city\_id | true | int | 城市ID |
| country\_id | true | int | 街道ID |
| street\_id | true | string | 街道ID |
| user\_name | true | string | 用户名称 |
| title | true | string | 招聘标题 |
| desc | true | string | 招聘内容（HTML） |
| type | true | int | 招聘类型 |
| min\_salary | true | int | 最低薪资 |
| max\_salary | true | int | 最高薪资 |
| work\_time | true | string | 工作时间 |
| status | true | int\(1\) | 状态 |
| education | true | int | 教育经历 |

## 响应接口

**响应Header**

* `Content-Type:application/json`

**响应参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| code | true | integer | HTTP响应代码, 成功返回200 |
| data | false | object | 响应内容 |
| msg | true | string | 响应描述 |

