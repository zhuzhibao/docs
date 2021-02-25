# 更新单条招聘



## 说明

* 功能说明：更新单条招聘接口

## 请求接口

**请求地址**

* `[host]/api/`business/recruitment/{id}

**请求方式**

* `PUT`

**请求头Header**

* `Authorization:Bearer {token}` token 为用户授权登陆Token
* `Accept:application/json`

**请求参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| talent\_category\_id | false | int | 分类ID |
| street\_id | false | string | 街道ID |
| user\_name | false | string | 用户名称 |
| title | false | string | 招聘标题 |
| desc | false | string | 招聘内容（HTML） |
| type | false | int | 招聘类型 |
| min\_salary | false | int | 最低薪资 |
| max\_salary | false | int | 最高薪资 |
| work\_time | false | string | 工作时间 |
| status | false | int\(1\) | 状态 |
| education | false | int | 教育经历 |

## 响应接口

**响应Header**

* `Content-Type:application/json`

**响应参数**

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| code | true | integer | HTTP响应代码, 成功返回200 |
| data | false | object | 响应内容 |
| msg | true | string | 响应描述 |

