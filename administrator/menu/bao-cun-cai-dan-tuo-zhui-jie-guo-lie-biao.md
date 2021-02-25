# 保存菜单拖追结果列表

## 说明

* 功能说明：保存菜单拖拽结果列表接口

## 请求接口

#### 请求地址

* `[host]/api/administrator/menu/drop`

#### 请求方式

* `PUT`

#### 请求头Header

* `Authorization:Bearer {token}` token 为用户授权登陆Token
* `Accept:application/json`

#### 请求参数

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| menu\_list | true | [Menu](bao-cun-cai-dan-tuo-zhui-jie-guo-lie-biao.md#menu-can-shu)\[\] | 拖拽后菜单数组 |

#### Menu参数

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| id | true | integer | 主键ID |
| parent\_id | true | integer | 父菜单主键ID, 为0时无父菜单 |
| menu\_type\_id | false | integer | 菜单分类外键ID |
| need\_permissions | false | string\[\] | 菜单所需权限 |
| need\_role\_types | false | string\[\] | 菜单所需角色 |
| name | false | string | 菜单标示 |
| title | false | string | 菜单展示标题 |
| icon | false | string | 图标 |
| path | false | string | 路径 |
| redirect | false | string | 重定向路径 |
| component | false | string | 前端组件名称 |
| keepAlive | false | boolean | 是否常驻 |
| props | false | boolean | 是否使用 Vue Props 传递 Route 参数 |
| hidden | false | boolean | 是否隐藏菜单 |
| hideChildrenInMenu | false | boolean | 是否隐藏子菜单 |
| children | false | [Menu](bao-cun-cai-dan-tuo-zhui-jie-guo-lie-biao.md#menu-can-shu)\[\] | 子菜单数组 |

## 

## 请求示例

{% tabs %}
{% tab title="JavaScript" %}
```javascript
var axios = require('axios');
var data = JSON.stringify({"menu_list":[{"id":145,"parent_id":0,"menu_type_id":3,"need_permissions":[],"need_role_types":["Business"],"name":"Dashboard","title":"仪表盘 | menu.dashboard","icon":"dashboard","path":"/dashboard","redirect":"/dashboard/workspace","component":"RouteView","keepAlive":false,"props":false,"hidden":false,"hideChildrenInMenu":false,"sort":5,"deleted_at":null,"created_at":"2021-01-04T05:54:39.000000Z","updated_at":"2021-01-06T01:19:24.000000Z","children":[{"id":148,"parent_id":145,"menu_type_id":3,"need_permissions":[],"need_role_types":["Business"],"name":"DashboardWorkplace","title":"工作台 | menu.dashboard.workplace","icon":"","path":"/dashboard/workplace","redirect":"","component":"Workplace","keepAlive":true,"props":true,"hidden":false,"hideChildrenInMenu":false,"sort":0,"deleted_at":null,"created_at":"2021-01-04T06:21:55.000000Z","updated_at":"2021-01-06T01:19:24.000000Z","key":148,"value":148}],"key":145,"value":145},{"id":164,"parent_id":0,"menu_type_id":3,"need_permissions":[],"need_role_types":["Business"],"name":"Company","title":"企业管理 | menu.company","icon":"apartment","path":"/company","redirect":"/company/detail","component":"RouteView","keepAlive":false,"props":false,"hidden":false,"hideChildrenInMenu":false,"sort":4,"deleted_at":null,"created_at":"2021-01-06T01:19:18.000000Z","updated_at":"2021-01-06T02:00:47.000000Z","children":[{"id":165,"parent_id":164,"menu_type_id":3,"need_permissions":[],"need_role_types":["Business"],"name":"CompanyDetail","title":"企业详情 | menu.company.detail","icon":"","path":"/company/:id?/detail","redirect":"","component":"company/CompanyDetail","keepAlive":true,"props":true,"hidden":false,"hideChildrenInMenu":false,"sort":0,"deleted_at":null,"created_at":"2021-01-06T02:00:38.000000Z","updated_at":"2021-01-06T02:00:38.000000Z","key":165,"value":165}],"key":164,"value":164},{"id":149,"parent_id":0,"menu_type_id":3,"need_permissions":[],"need_role_types":["Business"],"name":"Talent","title":"人才系统 | menu.talent","icon":"appstore","path":"/talent","redirect":"/talent/resume/index","component":"RouteView","keepAlive":true,"props":true,"hidden":false,"hideChildrenInMenu":false,"sort":3,"deleted_at":null,"created_at":"2021-01-04T06:24:07.000000Z","updated_at":"2021-01-06T01:19:24.000000Z","children":[{"id":150,"parent_id":149,"menu_type_id":3,"need_permissions":[],"need_role_types":["Business"],"name":"TalentResumeIndex","title":"简历列表 | menu.talent.resume.index","icon":"","path":"/talent/resume/index","redirect":"/talent/resume/list","component":"resume/ResumeIndex","keepAlive":false,"props":false,"hidden":false,"hideChildrenInMenu":true,"sort":1,"deleted_at":null,"created_at":"2021-01-04T06:25:07.000000Z","updated_at":"2021-01-06T01:19:24.000000Z","children":[{"id":151,"parent_id":150,"menu_type_id":3,"need_permissions":[],"need_role_types":["Business"],"name":"TalentResumeList","title":"简历列表 | menu.talent.resume.list","icon":"","path":"/talent/resume/list","redirect":"","component":"resume/ResumeList","keepAlive":true,"props":true,"hidden":false,"hideChildrenInMenu":false,"sort":1,"deleted_at":null,"created_at":"2021-01-04T06:25:52.000000Z","updated_at":"2021-01-06T01:19:24.000000Z","key":151,"value":151},{"id":152,"parent_id":150,"menu_type_id":3,"need_permissions":[],"need_role_types":["Business"],"name":"TalentResumeDetail","title":"简历详情 | menu.talent.resume.detail","icon":"","path":"/talent/resume/:id","redirect":"","component":"resume/ResumeDetail","keepAlive":true,"props":true,"hidden":true,"hideChildrenInMenu":true,"sort":0,"deleted_at":null,"created_at":"2021-01-04T06:26:43.000000Z","updated_at":"2021-01-06T01:19:24.000000Z","key":152,"value":152}],"key":150,"value":150},{"id":153,"parent_id":149,"menu_type_id":3,"need_permissions":[],"need_role_types":["Business"],"name":"TalentRecruitmentIndex","title":"招聘列表 | menu.talent.recruitment.index","icon":"","path":"/talent/recruitment/index","redirect":"/talent/recruitment/list","component":"recruitment/RecruitmentIndex","keepAlive":false,"props":false,"hidden":false,"hideChildrenInMenu":true,"sort":0,"deleted_at":null,"created_at":"2021-01-04T06:28:18.000000Z","updated_at":"2021-01-06T01:19:24.000000Z","children":[{"id":154,"parent_id":153,"menu_type_id":3,"need_permissions":[],"need_role_types":["Business"],"name":"TalentRecruitmentList","title":"招聘列表 | menu.talent.recruitment.list","icon":"","path":"/talent/recruitment/list","redirect":"","component":"recruitment/RecruitmentList","keepAlive":true,"props":true,"hidden":false,"hideChildrenInMenu":false,"sort":1,"deleted_at":null,"created_at":"2021-01-04T06:29:04.000000Z","updated_at":"2021-01-06T01:19:24.000000Z","key":154,"value":154},{"id":155,"parent_id":153,"menu_type_id":3,"need_permissions":[],"need_role_types":["Business"],"name":"TalentRecruitmentDetail","title":"招聘详情 | menu.talent.recruitment.detail","icon":"","path":"/talent/recruitment/:id","redirect":"","component":"recruitment/RecruitmentDetail","keepAlive":true,"props":true,"hidden":true,"hideChildrenInMenu":true,"sort":0,"deleted_at":null,"created_at":"2021-01-04T06:29:54.000000Z","updated_at":"2021-01-06T01:19:24.000000Z","key":155,"value":155}],"key":153,"value":153}],"key":149,"value":149},{"id":156,"parent_id":0,"menu_type_id":3,"need_permissions":[],"need_role_types":["Business"],"name":"Product","title":"建材市场 | menu.product","icon":"shopping-cart","path":"/product","redirect":"/prodcut/list","component":"RouteView","keepAlive":true,"props":true,"hidden":false,"hideChildrenInMenu":false,"sort":2,"deleted_at":null,"created_at":"2021-01-04T06:32:28.000000Z","updated_at":"2021-01-06T01:19:24.000000Z","children":[{"id":157,"parent_id":156,"menu_type_id":3,"need_permissions":[],"need_role_types":["Business"],"name":"ProductList","title":"商品列表 | menu.product.list","icon":"","path":"/product/list","redirect":"","component":"product/ProductList","keepAlive":true,"props":true,"hidden":false,"hideChildrenInMenu":false,"sort":0,"deleted_at":null,"created_at":"2021-01-04T06:33:22.000000Z","updated_at":"2021-01-06T01:19:24.000000Z","key":157,"value":157}],"key":156,"value":156},{"id":158,"parent_id":0,"menu_type_id":3,"need_permissions":[],"need_role_types":["Business"],"name":"Information","title":"资讯系统 | menu.information","icon":"message","path":"/information","redirect":"/information/list","component":"RouteView","keepAlive":true,"props":true,"hidden":false,"hideChildrenInMenu":false,"sort":1,"deleted_at":null,"created_at":"2021-01-04T06:41:52.000000Z","updated_at":"2021-01-06T01:19:24.000000Z","children":[{"id":159,"parent_id":158,"menu_type_id":3,"need_permissions":[],"need_role_types":["Business"],"name":"InformationList","title":"资讯列表 | menu.information.list","icon":"","path":"/information/list","redirect":"","component":"information/InformationList","keepAlive":true,"props":true,"hidden":false,"hideChildrenInMenu":false,"sort":0,"deleted_at":null,"created_at":"2021-01-04T06:43:55.000000Z","updated_at":"2021-01-06T01:19:24.000000Z","key":159,"value":159}],"key":158,"value":158},{"id":160,"parent_id":0,"menu_type_id":3,"need_permissions":[],"need_role_types":["Business"],"name":"Course","title":"课程管理 | menu.course","icon":"folder","path":"/course","redirect":"/course/index","component":"RouteView","keepAlive":true,"props":true,"hidden":false,"hideChildrenInMenu":false,"sort":0,"deleted_at":null,"created_at":"2021-01-04T06:47:09.000000Z","updated_at":"2021-01-06T01:19:24.000000Z","children":[{"id":161,"parent_id":160,"menu_type_id":3,"need_permissions":[],"need_role_types":["Business"],"name":"CourseIndex","title":"课程列表 | menu.course.index","icon":"","path":"/course/index","redirect":"/course/list","component":"course/CourseIndex","keepAlive":false,"props":false,"hidden":false,"hideChildrenInMenu":true,"sort":0,"deleted_at":null,"created_at":"2021-01-04T06:48:02.000000Z","updated_at":"2021-01-06T01:19:24.000000Z","children":[{"id":162,"parent_id":161,"menu_type_id":3,"need_permissions":[],"need_role_types":["Business"],"name":"CourseList","title":"课程列表 | menu.course.list","icon":"","path":"/course/list","redirect":"","component":"course/CourseList","keepAlive":true,"props":true,"hidden":false,"hideChildrenInMenu":false,"sort":1,"deleted_at":null,"created_at":"2021-01-04T06:48:42.000000Z","updated_at":"2021-01-06T01:19:24.000000Z","key":162,"value":162},{"id":163,"parent_id":161,"menu_type_id":3,"need_permissions":[],"need_role_types":["Business"],"name":"CourseEpisode","title":"课程剧集 | menu.course.episode","icon":"","path":"/course/:id/episode","redirect":"","component":"course/CourseEpisodeList","keepAlive":true,"props":true,"hidden":false,"hideChildrenInMenu":false,"sort":0,"deleted_at":null,"created_at":"2021-01-04T06:49:14.000000Z","updated_at":"2021-01-06T01:19:24.000000Z","key":163,"value":163}],"key":161,"value":161}],"key":160,"value":160}]});

var config = {
  method: 'put',
  url: 'http://local.build-dream.cn/api/administrator/menu/drop',
  headers: { 
    'Authorization': 'Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE', 
    'Accept': 'application/json', 
    'Content-Type': 'application/json', 
    'Cookie': 'PHPSESSID=171eee4ecf83ae527a5416c47ec3bf7f'
  },
  data : data
};

axios(config)
.then(function (response) {
  console.log(JSON.stringify(response.data));
})
.catch(function (error) {
  console.log(error);
});

```
{% endtab %}

{% tab title="cURL" %}
```bash
curl --location --request PUT 'http://local.build-dream.cn/api/administrator/menu/drop' \
--header 'Authorization: Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \
--header 'Cookie: PHPSESSID=171eee4ecf83ae527a5416c47ec3bf7f' \
--data-raw '{
    "menu_list": [
        {
            "id": 145,
            "parent_id": 0,
            "menu_type_id": 3,
            "need_permissions": [],
            "need_role_types": [
                "Business"
            ],
            "name": "Dashboard",
            "title": "仪表盘 | menu.dashboard",
            "icon": "dashboard",
            "path": "/dashboard",
            "redirect": "/dashboard/workspace",
            "component": "RouteView",
            "keepAlive": false,
            "props": false,
            "hidden": false,
            "hideChildrenInMenu": false,
            "sort": 5,
            "deleted_at": null,
            "created_at": "2021-01-04T05:54:39.000000Z",
            "updated_at": "2021-01-06T01:19:24.000000Z",
            "children": [
                {
                    "id": 148,
                    "parent_id": 145,
                    "menu_type_id": 3,
                    "need_permissions": [],
                    "need_role_types": [
                        "Business"
                    ],
                    "name": "DashboardWorkplace",
                    "title": "工作台 | menu.dashboard.workplace",
                    "icon": "",
                    "path": "/dashboard/workplace",
                    "redirect": "",
                    "component": "Workplace",
                    "keepAlive": true,
                    "props": true,
                    "hidden": false,
                    "hideChildrenInMenu": false,
                    "sort": 0,
                    "deleted_at": null,
                    "created_at": "2021-01-04T06:21:55.000000Z",
                    "updated_at": "2021-01-06T01:19:24.000000Z",
                    "key": 148,
                    "value": 148
                }
            ],
            "key": 145,
            "value": 145
        },
        {
            "id": 164,
            "parent_id": 0,
            "menu_type_id": 3,
            "need_permissions": [],
            "need_role_types": [
                "Business"
            ],
            "name": "Company",
            "title": "企业管理 | menu.company",
            "icon": "apartment",
            "path": "/company",
            "redirect": "/company/detail",
            "component": "RouteView",
            "keepAlive": false,
            "props": false,
            "hidden": false,
            "hideChildrenInMenu": false,
            "sort": 4,
            "deleted_at": null,
            "created_at": "2021-01-06T01:19:18.000000Z",
            "updated_at": "2021-01-06T02:00:47.000000Z",
            "children": [
                {
                    "id": 165,
                    "parent_id": 164,
                    "menu_type_id": 3,
                    "need_permissions": [],
                    "need_role_types": [
                        "Business"
                    ],
                    "name": "CompanyDetail",
                    "title": "企业详情 | menu.company.detail",
                    "icon": "",
                    "path": "/company/:id?/detail",
                    "redirect": "",
                    "component": "company/CompanyDetail",
                    "keepAlive": true,
                    "props": true,
                    "hidden": false,
                    "hideChildrenInMenu": false,
                    "sort": 0,
                    "deleted_at": null,
                    "created_at": "2021-01-06T02:00:38.000000Z",
                    "updated_at": "2021-01-06T02:00:38.000000Z",
                    "key": 165,
                    "value": 165
                }
            ],
            "key": 164,
            "value": 164
        },
        {
            "id": 149,
            "parent_id": 0,
            "menu_type_id": 3,
            "need_permissions": [],
            "need_role_types": [
                "Business"
            ],
            "name": "Talent",
            "title": "人才系统 | menu.talent",
            "icon": "appstore",
            "path": "/talent",
            "redirect": "/talent/resume/index",
            "component": "RouteView",
            "keepAlive": true,
            "props": true,
            "hidden": false,
            "hideChildrenInMenu": false,
            "sort": 3,
            "deleted_at": null,
            "created_at": "2021-01-04T06:24:07.000000Z",
            "updated_at": "2021-01-06T01:19:24.000000Z",
            "children": [
                {
                    "id": 150,
                    "parent_id": 149,
                    "menu_type_id": 3,
                    "need_permissions": [],
                    "need_role_types": [
                        "Business"
                    ],
                    "name": "TalentResumeIndex",
                    "title": "简历列表 | menu.talent.resume.index",
                    "icon": "",
                    "path": "/talent/resume/index",
                    "redirect": "/talent/resume/list",
                    "component": "resume/ResumeIndex",
                    "keepAlive": false,
                    "props": false,
                    "hidden": false,
                    "hideChildrenInMenu": true,
                    "sort": 1,
                    "deleted_at": null,
                    "created_at": "2021-01-04T06:25:07.000000Z",
                    "updated_at": "2021-01-06T01:19:24.000000Z",
                    "children": [
                        {
                            "id": 151,
                            "parent_id": 150,
                            "menu_type_id": 3,
                            "need_permissions": [],
                            "need_role_types": [
                                "Business"
                            ],
                            "name": "TalentResumeList",
                            "title": "简历列表 | menu.talent.resume.list",
                            "icon": "",
                            "path": "/talent/resume/list",
                            "redirect": "",
                            "component": "resume/ResumeList",
                            "keepAlive": true,
                            "props": true,
                            "hidden": false,
                            "hideChildrenInMenu": false,
                            "sort": 1,
                            "deleted_at": null,
                            "created_at": "2021-01-04T06:25:52.000000Z",
                            "updated_at": "2021-01-06T01:19:24.000000Z",
                            "key": 151,
                            "value": 151
                        },
                        {
                            "id": 152,
                            "parent_id": 150,
                            "menu_type_id": 3,
                            "need_permissions": [],
                            "need_role_types": [
                                "Business"
                            ],
                            "name": "TalentResumeDetail",
                            "title": "简历详情 | menu.talent.resume.detail",
                            "icon": "",
                            "path": "/talent/resume/:id",
                            "redirect": "",
                            "component": "resume/ResumeDetail",
                            "keepAlive": true,
                            "props": true,
                            "hidden": true,
                            "hideChildrenInMenu": true,
                            "sort": 0,
                            "deleted_at": null,
                            "created_at": "2021-01-04T06:26:43.000000Z",
                            "updated_at": "2021-01-06T01:19:24.000000Z",
                            "key": 152,
                            "value": 152
                        }
                    ],
                    "key": 150,
                    "value": 150
                },
                {
                    "id": 153,
                    "parent_id": 149,
                    "menu_type_id": 3,
                    "need_permissions": [],
                    "need_role_types": [
                        "Business"
                    ],
                    "name": "TalentRecruitmentIndex",
                    "title": "招聘列表 | menu.talent.recruitment.index",
                    "icon": "",
                    "path": "/talent/recruitment/index",
                    "redirect": "/talent/recruitment/list",
                    "component": "recruitment/RecruitmentIndex",
                    "keepAlive": false,
                    "props": false,
                    "hidden": false,
                    "hideChildrenInMenu": true,
                    "sort": 0,
                    "deleted_at": null,
                    "created_at": "2021-01-04T06:28:18.000000Z",
                    "updated_at": "2021-01-06T01:19:24.000000Z",
                    "children": [
                        {
                            "id": 154,
                            "parent_id": 153,
                            "menu_type_id": 3,
                            "need_permissions": [],
                            "need_role_types": [
                                "Business"
                            ],
                            "name": "TalentRecruitmentList",
                            "title": "招聘列表 | menu.talent.recruitment.list",
                            "icon": "",
                            "path": "/talent/recruitment/list",
                            "redirect": "",
                            "component": "recruitment/RecruitmentList",
                            "keepAlive": true,
                            "props": true,
                            "hidden": false,
                            "hideChildrenInMenu": false,
                            "sort": 1,
                            "deleted_at": null,
                            "created_at": "2021-01-04T06:29:04.000000Z",
                            "updated_at": "2021-01-06T01:19:24.000000Z",
                            "key": 154,
                            "value": 154
                        },
                        {
                            "id": 155,
                            "parent_id": 153,
                            "menu_type_id": 3,
                            "need_permissions": [],
                            "need_role_types": [
                                "Business"
                            ],
                            "name": "TalentRecruitmentDetail",
                            "title": "招聘详情 | menu.talent.recruitment.detail",
                            "icon": "",
                            "path": "/talent/recruitment/:id",
                            "redirect": "",
                            "component": "recruitment/RecruitmentDetail",
                            "keepAlive": true,
                            "props": true,
                            "hidden": true,
                            "hideChildrenInMenu": true,
                            "sort": 0,
                            "deleted_at": null,
                            "created_at": "2021-01-04T06:29:54.000000Z",
                            "updated_at": "2021-01-06T01:19:24.000000Z",
                            "key": 155,
                            "value": 155
                        }
                    ],
                    "key": 153,
                    "value": 153
                }
            ],
            "key": 149,
            "value": 149
        },
        {
            "id": 156,
            "parent_id": 0,
            "menu_type_id": 3,
            "need_permissions": [],
            "need_role_types": [
                "Business"
            ],
            "name": "Product",
            "title": "建材市场 | menu.product",
            "icon": "shopping-cart",
            "path": "/product",
            "redirect": "/prodcut/list",
            "component": "RouteView",
            "keepAlive": true,
            "props": true,
            "hidden": false,
            "hideChildrenInMenu": false,
            "sort": 2,
            "deleted_at": null,
            "created_at": "2021-01-04T06:32:28.000000Z",
            "updated_at": "2021-01-06T01:19:24.000000Z",
            "children": [
                {
                    "id": 157,
                    "parent_id": 156,
                    "menu_type_id": 3,
                    "need_permissions": [],
                    "need_role_types": [
                        "Business"
                    ],
                    "name": "ProductList",
                    "title": "商品列表 | menu.product.list",
                    "icon": "",
                    "path": "/product/list",
                    "redirect": "",
                    "component": "product/ProductList",
                    "keepAlive": true,
                    "props": true,
                    "hidden": false,
                    "hideChildrenInMenu": false,
                    "sort": 0,
                    "deleted_at": null,
                    "created_at": "2021-01-04T06:33:22.000000Z",
                    "updated_at": "2021-01-06T01:19:24.000000Z",
                    "key": 157,
                    "value": 157
                }
            ],
            "key": 156,
            "value": 156
        },
        {
            "id": 158,
            "parent_id": 0,
            "menu_type_id": 3,
            "need_permissions": [],
            "need_role_types": [
                "Business"
            ],
            "name": "Information",
            "title": "资讯系统 | menu.information",
            "icon": "message",
            "path": "/information",
            "redirect": "/information/list",
            "component": "RouteView",
            "keepAlive": true,
            "props": true,
            "hidden": false,
            "hideChildrenInMenu": false,
            "sort": 1,
            "deleted_at": null,
            "created_at": "2021-01-04T06:41:52.000000Z",
            "updated_at": "2021-01-06T01:19:24.000000Z",
            "children": [
                {
                    "id": 159,
                    "parent_id": 158,
                    "menu_type_id": 3,
                    "need_permissions": [],
                    "need_role_types": [
                        "Business"
                    ],
                    "name": "InformationList",
                    "title": "资讯列表 | menu.information.list",
                    "icon": "",
                    "path": "/information/list",
                    "redirect": "",
                    "component": "information/InformationList",
                    "keepAlive": true,
                    "props": true,
                    "hidden": false,
                    "hideChildrenInMenu": false,
                    "sort": 0,
                    "deleted_at": null,
                    "created_at": "2021-01-04T06:43:55.000000Z",
                    "updated_at": "2021-01-06T01:19:24.000000Z",
                    "key": 159,
                    "value": 159
                }
            ],
            "key": 158,
            "value": 158
        },
        {
            "id": 160,
            "parent_id": 0,
            "menu_type_id": 3,
            "need_permissions": [],
            "need_role_types": [
                "Business"
            ],
            "name": "Course",
            "title": "课程管理 | menu.course",
            "icon": "folder",
            "path": "/course",
            "redirect": "/course/index",
            "component": "RouteView",
            "keepAlive": true,
            "props": true,
            "hidden": false,
            "hideChildrenInMenu": false,
            "sort": 0,
            "deleted_at": null,
            "created_at": "2021-01-04T06:47:09.000000Z",
            "updated_at": "2021-01-06T01:19:24.000000Z",
            "children": [
                {
                    "id": 161,
                    "parent_id": 160,
                    "menu_type_id": 3,
                    "need_permissions": [],
                    "need_role_types": [
                        "Business"
                    ],
                    "name": "CourseIndex",
                    "title": "课程列表 | menu.course.index",
                    "icon": "",
                    "path": "/course/index",
                    "redirect": "/course/list",
                    "component": "course/CourseIndex",
                    "keepAlive": false,
                    "props": false,
                    "hidden": false,
                    "hideChildrenInMenu": true,
                    "sort": 0,
                    "deleted_at": null,
                    "created_at": "2021-01-04T06:48:02.000000Z",
                    "updated_at": "2021-01-06T01:19:24.000000Z",
                    "children": [
                        {
                            "id": 162,
                            "parent_id": 161,
                            "menu_type_id": 3,
                            "need_permissions": [],
                            "need_role_types": [
                                "Business"
                            ],
                            "name": "CourseList",
                            "title": "课程列表 | menu.course.list",
                            "icon": "",
                            "path": "/course/list",
                            "redirect": "",
                            "component": "course/CourseList",
                            "keepAlive": true,
                            "props": true,
                            "hidden": false,
                            "hideChildrenInMenu": false,
                            "sort": 1,
                            "deleted_at": null,
                            "created_at": "2021-01-04T06:48:42.000000Z",
                            "updated_at": "2021-01-06T01:19:24.000000Z",
                            "key": 162,
                            "value": 162
                        },
                        {
                            "id": 163,
                            "parent_id": 161,
                            "menu_type_id": 3,
                            "need_permissions": [],
                            "need_role_types": [
                                "Business"
                            ],
                            "name": "CourseEpisode",
                            "title": "课程剧集 | menu.course.episode",
                            "icon": "",
                            "path": "/course/:id/episode",
                            "redirect": "",
                            "component": "course/CourseEpisodeList",
                            "keepAlive": true,
                            "props": true,
                            "hidden": false,
                            "hideChildrenInMenu": false,
                            "sort": 0,
                            "deleted_at": null,
                            "created_at": "2021-01-04T06:49:14.000000Z",
                            "updated_at": "2021-01-06T01:19:24.000000Z",
                            "key": 163,
                            "value": 163
                        }
                    ],
                    "key": 161,
                    "value": 161
                }
            ],
            "key": 160,
            "value": 160
        }
    ]
}'
```
{% endtab %}

{% tab title="HTTP" %}
```http
PUT /api/administrator/menu/drop HTTP/1.1
Host: local.build-dream.cn
Authorization: Bearer 323|jTbUFek9YNrITuP1fo6zHUifO3bAb14J8LgjOShE
Accept: application/json
Content-Type: application/json
Cookie: PHPSESSID=171eee4ecf83ae527a5416c47ec3bf7f
Content-Length: 19410

{
    "menu_list": [
        {
            "id": 145,
            "parent_id": 0,
            "menu_type_id": 3,
            "need_permissions": [],
            "need_role_types": [
                "Business"
            ],
            "name": "Dashboard",
            "title": "仪表盘 | menu.dashboard",
            "icon": "dashboard",
            "path": "/dashboard",
            "redirect": "/dashboard/workspace",
            "component": "RouteView",
            "keepAlive": false,
            "props": false,
            "hidden": false,
            "hideChildrenInMenu": false,
            "sort": 5,
            "deleted_at": null,
            "created_at": "2021-01-04T05:54:39.000000Z",
            "updated_at": "2021-01-06T01:19:24.000000Z",
            "children": [
                {
                    "id": 148,
                    "parent_id": 145,
                    "menu_type_id": 3,
                    "need_permissions": [],
                    "need_role_types": [
                        "Business"
                    ],
                    "name": "DashboardWorkplace",
                    "title": "工作台 | menu.dashboard.workplace",
                    "icon": "",
                    "path": "/dashboard/workplace",
                    "redirect": "",
                    "component": "Workplace",
                    "keepAlive": true,
                    "props": true,
                    "hidden": false,
                    "hideChildrenInMenu": false,
                    "sort": 0,
                    "deleted_at": null,
                    "created_at": "2021-01-04T06:21:55.000000Z",
                    "updated_at": "2021-01-06T01:19:24.000000Z",
                    "key": 148,
                    "value": 148
                }
            ],
            "key": 145,
            "value": 145
        },
        {
            "id": 164,
            "parent_id": 0,
            "menu_type_id": 3,
            "need_permissions": [],
            "need_role_types": [
                "Business"
            ],
            "name": "Company",
            "title": "企业管理 | menu.company",
            "icon": "apartment",
            "path": "/company",
            "redirect": "/company/detail",
            "component": "RouteView",
            "keepAlive": false,
            "props": false,
            "hidden": false,
            "hideChildrenInMenu": false,
            "sort": 4,
            "deleted_at": null,
            "created_at": "2021-01-06T01:19:18.000000Z",
            "updated_at": "2021-01-06T02:00:47.000000Z",
            "children": [
                {
                    "id": 165,
                    "parent_id": 164,
                    "menu_type_id": 3,
                    "need_permissions": [],
                    "need_role_types": [
                        "Business"
                    ],
                    "name": "CompanyDetail",
                    "title": "企业详情 | menu.company.detail",
                    "icon": "",
                    "path": "/company/:id?/detail",
                    "redirect": "",
                    "component": "company/CompanyDetail",
                    "keepAlive": true,
                    "props": true,
                    "hidden": false,
                    "hideChildrenInMenu": false,
                    "sort": 0,
                    "deleted_at": null,
                    "created_at": "2021-01-06T02:00:38.000000Z",
                    "updated_at": "2021-01-06T02:00:38.000000Z",
                    "key": 165,
                    "value": 165
                }
            ],
            "key": 164,
            "value": 164
        },
        {
            "id": 149,
            "parent_id": 0,
            "menu_type_id": 3,
            "need_permissions": [],
            "need_role_types": [
                "Business"
            ],
            "name": "Talent",
            "title": "人才系统 | menu.talent",
            "icon": "appstore",
            "path": "/talent",
            "redirect": "/talent/resume/index",
            "component": "RouteView",
            "keepAlive": true,
            "props": true,
            "hidden": false,
            "hideChildrenInMenu": false,
            "sort": 3,
            "deleted_at": null,
            "created_at": "2021-01-04T06:24:07.000000Z",
            "updated_at": "2021-01-06T01:19:24.000000Z",
            "children": [
                {
                    "id": 150,
                    "parent_id": 149,
                    "menu_type_id": 3,
                    "need_permissions": [],
                    "need_role_types": [
                        "Business"
                    ],
                    "name": "TalentResumeIndex",
                    "title": "简历列表 | menu.talent.resume.index",
                    "icon": "",
                    "path": "/talent/resume/index",
                    "redirect": "/talent/resume/list",
                    "component": "resume/ResumeIndex",
                    "keepAlive": false,
                    "props": false,
                    "hidden": false,
                    "hideChildrenInMenu": true,
                    "sort": 1,
                    "deleted_at": null,
                    "created_at": "2021-01-04T06:25:07.000000Z",
                    "updated_at": "2021-01-06T01:19:24.000000Z",
                    "children": [
                        {
                            "id": 151,
                            "parent_id": 150,
                            "menu_type_id": 3,
                            "need_permissions": [],
                            "need_role_types": [
                                "Business"
                            ],
                            "name": "TalentResumeList",
                            "title": "简历列表 | menu.talent.resume.list",
                            "icon": "",
                            "path": "/talent/resume/list",
                            "redirect": "",
                            "component": "resume/ResumeList",
                            "keepAlive": true,
                            "props": true,
                            "hidden": false,
                            "hideChildrenInMenu": false,
                            "sort": 1,
                            "deleted_at": null,
                            "created_at": "2021-01-04T06:25:52.000000Z",
                            "updated_at": "2021-01-06T01:19:24.000000Z",
                            "key": 151,
                            "value": 151
                        },
                        {
                            "id": 152,
                            "parent_id": 150,
                            "menu_type_id": 3,
                            "need_permissions": [],
                            "need_role_types": [
                                "Business"
                            ],
                            "name": "TalentResumeDetail",
                            "title": "简历详情 | menu.talent.resume.detail",
                            "icon": "",
                            "path": "/talent/resume/:id",
                            "redirect": "",
                            "component": "resume/ResumeDetail",
                            "keepAlive": true,
                            "props": true,
                            "hidden": true,
                            "hideChildrenInMenu": true,
                            "sort": 0,
                            "deleted_at": null,
                            "created_at": "2021-01-04T06:26:43.000000Z",
                            "updated_at": "2021-01-06T01:19:24.000000Z",
                            "key": 152,
                            "value": 152
                        }
                    ],
                    "key": 150,
                    "value": 150
                },
                {
                    "id": 153,
                    "parent_id": 149,
                    "menu_type_id": 3,
                    "need_permissions": [],
                    "need_role_types": [
                        "Business"
                    ],
                    "name": "TalentRecruitmentIndex",
                    "title": "招聘列表 | menu.talent.recruitment.index",
                    "icon": "",
                    "path": "/talent/recruitment/index",
                    "redirect": "/talent/recruitment/list",
                    "component": "recruitment/RecruitmentIndex",
                    "keepAlive": false,
                    "props": false,
                    "hidden": false,
                    "hideChildrenInMenu": true,
                    "sort": 0,
                    "deleted_at": null,
                    "created_at": "2021-01-04T06:28:18.000000Z",
                    "updated_at": "2021-01-06T01:19:24.000000Z",
                    "children": [
                        {
                            "id": 154,
                            "parent_id": 153,
                            "menu_type_id": 3,
                            "need_permissions": [],
                            "need_role_types": [
                                "Business"
                            ],
                            "name": "TalentRecruitmentList",
                            "title": "招聘列表 | menu.talent.recruitment.list",
                            "icon": "",
                            "path": "/talent/recruitment/list",
                            "redirect": "",
                            "component": "recruitment/RecruitmentList",
                            "keepAlive": true,
                            "props": true,
                            "hidden": false,
                            "hideChildrenInMenu": false,
                            "sort": 1,
                            "deleted_at": null,
                            "created_at": "2021-01-04T06:29:04.000000Z",
                            "updated_at": "2021-01-06T01:19:24.000000Z",
                            "key": 154,
                            "value": 154
                        },
                        {
                            "id": 155,
                            "parent_id": 153,
                            "menu_type_id": 3,
                            "need_permissions": [],
                            "need_role_types": [
                                "Business"
                            ],
                            "name": "TalentRecruitmentDetail",
                            "title": "招聘详情 | menu.talent.recruitment.detail",
                            "icon": "",
                            "path": "/talent/recruitment/:id",
                            "redirect": "",
                            "component": "recruitment/RecruitmentDetail",
                            "keepAlive": true,
                            "props": true,
                            "hidden": true,
                            "hideChildrenInMenu": true,
                            "sort": 0,
                            "deleted_at": null,
                            "created_at": "2021-01-04T06:29:54.000000Z",
                            "updated_at": "2021-01-06T01:19:24.000000Z",
                            "key": 155,
                            "value": 155
                        }
                    ],
                    "key": 153,
                    "value": 153
                }
            ],
            "key": 149,
            "value": 149
        },
        {
            "id": 156,
            "parent_id": 0,
            "menu_type_id": 3,
            "need_permissions": [],
            "need_role_types": [
                "Business"
            ],
            "name": "Product",
            "title": "建材市场 | menu.product",
            "icon": "shopping-cart",
            "path": "/product",
            "redirect": "/prodcut/list",
            "component": "RouteView",
            "keepAlive": true,
            "props": true,
            "hidden": false,
            "hideChildrenInMenu": false,
            "sort": 2,
            "deleted_at": null,
            "created_at": "2021-01-04T06:32:28.000000Z",
            "updated_at": "2021-01-06T01:19:24.000000Z",
            "children": [
                {
                    "id": 157,
                    "parent_id": 156,
                    "menu_type_id": 3,
                    "need_permissions": [],
                    "need_role_types": [
                        "Business"
                    ],
                    "name": "ProductList",
                    "title": "商品列表 | menu.product.list",
                    "icon": "",
                    "path": "/product/list",
                    "redirect": "",
                    "component": "product/ProductList",
                    "keepAlive": true,
                    "props": true,
                    "hidden": false,
                    "hideChildrenInMenu": false,
                    "sort": 0,
                    "deleted_at": null,
                    "created_at": "2021-01-04T06:33:22.000000Z",
                    "updated_at": "2021-01-06T01:19:24.000000Z",
                    "key": 157,
                    "value": 157
                }
            ],
            "key": 156,
            "value": 156
        },
        {
            "id": 158,
            "parent_id": 0,
            "menu_type_id": 3,
            "need_permissions": [],
            "need_role_types": [
                "Business"
            ],
            "name": "Information",
            "title": "资讯系统 | menu.information",
            "icon": "message",
            "path": "/information",
            "redirect": "/information/list",
            "component": "RouteView",
            "keepAlive": true,
            "props": true,
            "hidden": false,
            "hideChildrenInMenu": false,
            "sort": 1,
            "deleted_at": null,
            "created_at": "2021-01-04T06:41:52.000000Z",
            "updated_at": "2021-01-06T01:19:24.000000Z",
            "children": [
                {
                    "id": 159,
                    "parent_id": 158,
                    "menu_type_id": 3,
                    "need_permissions": [],
                    "need_role_types": [
                        "Business"
                    ],
                    "name": "InformationList",
                    "title": "资讯列表 | menu.information.list",
                    "icon": "",
                    "path": "/information/list",
                    "redirect": "",
                    "component": "information/InformationList",
                    "keepAlive": true,
                    "props": true,
                    "hidden": false,
                    "hideChildrenInMenu": false,
                    "sort": 0,
                    "deleted_at": null,
                    "created_at": "2021-01-04T06:43:55.000000Z",
                    "updated_at": "2021-01-06T01:19:24.000000Z",
                    "key": 159,
                    "value": 159
                }
            ],
            "key": 158,
            "value": 158
        },
        {
            "id": 160,
            "parent_id": 0,
            "menu_type_id": 3,
            "need_permissions": [],
            "need_role_types": [
                "Business"
            ],
            "name": "Course",
            "title": "课程管理 | menu.course",
            "icon": "folder",
            "path": "/course",
            "redirect": "/course/index",
            "component": "RouteView",
            "keepAlive": true,
            "props": true,
            "hidden": false,
            "hideChildrenInMenu": false,
            "sort": 0,
            "deleted_at": null,
            "created_at": "2021-01-04T06:47:09.000000Z",
            "updated_at": "2021-01-06T01:19:24.000000Z",
            "children": [
                {
                    "id": 161,
                    "parent_id": 160,
                    "menu_type_id": 3,
                    "need_permissions": [],
                    "need_role_types": [
                        "Business"
                    ],
                    "name": "CourseIndex",
                    "title": "课程列表 | menu.course.index",
                    "icon": "",
                    "path": "/course/index",
                    "redirect": "/course/list",
                    "component": "course/CourseIndex",
                    "keepAlive": false,
                    "props": false,
                    "hidden": false,
                    "hideChildrenInMenu": true,
                    "sort": 0,
                    "deleted_at": null,
                    "created_at": "2021-01-04T06:48:02.000000Z",
                    "updated_at": "2021-01-06T01:19:24.000000Z",
                    "children": [
                        {
                            "id": 162,
                            "parent_id": 161,
                            "menu_type_id": 3,
                            "need_permissions": [],
                            "need_role_types": [
                                "Business"
                            ],
                            "name": "CourseList",
                            "title": "课程列表 | menu.course.list",
                            "icon": "",
                            "path": "/course/list",
                            "redirect": "",
                            "component": "course/CourseList",
                            "keepAlive": true,
                            "props": true,
                            "hidden": false,
                            "hideChildrenInMenu": false,
                            "sort": 1,
                            "deleted_at": null,
                            "created_at": "2021-01-04T06:48:42.000000Z",
                            "updated_at": "2021-01-06T01:19:24.000000Z",
                            "key": 162,
                            "value": 162
                        },
                        {
                            "id": 163,
                            "parent_id": 161,
                            "menu_type_id": 3,
                            "need_permissions": [],
                            "need_role_types": [
                                "Business"
                            ],
                            "name": "CourseEpisode",
                            "title": "课程剧集 | menu.course.episode",
                            "icon": "",
                            "path": "/course/:id/episode",
                            "redirect": "",
                            "component": "course/CourseEpisodeList",
                            "keepAlive": true,
                            "props": true,
                            "hidden": false,
                            "hideChildrenInMenu": false,
                            "sort": 0,
                            "deleted_at": null,
                            "created_at": "2021-01-04T06:49:14.000000Z",
                            "updated_at": "2021-01-06T01:19:24.000000Z",
                            "key": 163,
                            "value": 163
                        }
                    ],
                    "key": 161,
                    "value": 161
                }
            ],
            "key": 160,
            "value": 160
        }
    ]
}
```
{% endtab %}
{% endtabs %}

## 响应接口

#### 响应Header

* `Content-Type:application/json`

#### 响应参数

| 参数名 | 是否必填 | 数据类型 | 字段说明 |
| :---: | :---: | :---: | :---: |
| code | true | integer | HTTP响应代码, 成功返回200 |
| data | false | string | 响应内容 |
| msg | true | string | 响应描述 |

## 响应示例

{% tabs %}
{% tab title="正确响应" %}
```javascript
{
    "code": 200,
    "data": "拖拽结果已保存",
    "msg": "success"
}
```
{% endtab %}

{% tab title="表单验证错误响应" %}
```javascript
{
    "code": 403,
    "data": {
        "menu_list": [
            "menu list 不能为空"
        ]
    },
    "msg": "请求数据验证失败!"
}
```
{% endtab %}

{% tab title="认证错误响应" %}
```javascript
{
    "code": 401,
    "msg": "请求未认证"
}
```
{% endtab %}
{% endtabs %}



