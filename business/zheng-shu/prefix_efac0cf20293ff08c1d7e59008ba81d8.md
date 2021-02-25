# 证书列表

## 简要描述

* 证书列表

## 请求URL

* `{{domain}}/api/business/user-licence`

## 请求方式

* GET 

## 参数

| 参数名 | 必选 | 类型 | 说明 |
| :--- | :--- | :--- | :--- |
| keyword | 否 | string | 关键字搜索 |

## 返回参数说明

| 参数名 | 类型 | 说明 |
| :--- | :--- | :--- |
| id | int | 用户id |
| name | int | 用户名 |
| nickname | int | 昵称 |
| real\_name | int | 真是姓名 |
| phone | int | 手机号码 |
| avatar | int | 头像 |
| certificate | object | 证书 |

## 返回certificate参数说明

| 参数名 | 类型 | 说明 |
| :--- | :--- | :--- |
| id | int | 用户id |
| user\_id | int | 用户id |
| license\_category\_id | int | 证书分类ID |
| license\_category\_name | int | 证书分类名称 |
| title | int | 用户自定义证书名称 |
| url | int | 证书上传地址 |
| expire\_at | int | 过期时间 |

