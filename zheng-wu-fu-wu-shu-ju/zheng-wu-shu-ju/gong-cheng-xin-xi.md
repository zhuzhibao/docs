# 工程信息

{% api-method method="get" host="https://test-server.build-dream.cn" path="/api/project/information" %}
{% api-method-summary %}
Get Cakes
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to get free cakes.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="keyword" type="string" %}
The API will do its best to find a cake matching the provided recipe.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```php
{    "name": "Cake's name{
    "code": 200,
    "data": {
        "items": {
            "current_page": 1,
            "data": [
                {
                    "mID": 1,
                    "工程造价（万元）": "2000",
                    "工程项目名称": "永康市桃花源农业观光旅游度假区D-01地块建设项目",
                    "建设单位名称": "永康市桃花源农业开发有限公司",
                    "建设单位统一社会信用代码": "91330784597215142M",
                    "开工日期": "2019-10-19",
                    "所属区县": "330784",
                    "所属市": "330700",
                    "施工总承包单位名称": "浙江紫微建筑工程有限公司",
                    "施工总承包单位统一社会信用代码": "913307842550741838",
                    "施工许可证号": "330784201910180101",
                    "项目地址": "永康市桃花源农业观光旅游度假区D-01地块",
                    "项目经理": "吕宏巍",
                    "项目基本信息主键ID": "93767686-afe7-4c27-b9f7-70f31e73d081",
                    "发证时间": "2019/10/18"
                }
            ],
            "first_page_url": "http://api.test-server.build-dream.cn/api/project/information?page=1",
            "from": 1,
            "next_page_url": null,
            "path": "http://api.test-server.build-dream.cn/api/project/information",
            "per_page": 20,
            "prev_page_url": null,
            "to": 1
        },
        "has_more": false
    },
    "msg": "success"
},    "recipe": "Cake's recipe name",    "cake": "Binary cake"}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Could not find a cake matching this query.
{% endapi-method-response-example-description %}

```
{    "message": "Ain't no cake like that."}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



