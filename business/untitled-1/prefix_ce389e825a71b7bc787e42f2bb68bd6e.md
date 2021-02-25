# 企业资质列表接口

## 简要描述

* 企业资质列表接口

## 请求URL

* `{{domain}}/api/business/qualification-company`

## 请求方式

* GET 

## 参数

| 参数名 | 必选 | 类型 | 说明 |
| :--- | :--- | :--- | :--- |
| qualification\_id | false | string | 资质ID |
| expired\_at | false | string | 过期时间 |

## 返回参数说明

| 参数名 | 类型 | 说明 |
| :--- | :--- | :--- |
| id | int | 主键ID |
| company\_id | int | 企业ID |
| qualification\_id | int | 资质分类ID |
| url | int | 资质上传地址 |
| remark | int | 备注 |
| expired\_at | int | 到期时间 |
| qualification | object | 资质 |

## 返回qualification参数说明

| 参数名 | 类型 | 说明 |
| :--- | :--- | :--- |
| id | int | 资质ID |
| parent\_id | int | 父类ID |
| name | int | 名称 |
| cover\_image | int | 封面图片 |

## 备注

