# 获奖企业信息

{% api-method method="get" host="https://test-server.build-dream.cn" path="/api/award/company" %}
{% api-method-summary %}
Get Cakes
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to get free cakes.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="keyword" type="string" required=false %}
 搜索关键字
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

{% tabs %}
{% tab title="PHP" %}
```php
{
    "code": 200,
    "data": {
        "items": {
            "current_page": 1,
            "data": [
                {
                    "mID": 1,
                    "统一社会信用代码": "9133068114627096XL",
                    "荣誉名称和内容": "-1",
                    "获得荣誉时间": "2018-03-08",
                    "状态": "有效",
                    "编号": "15244"
                },
                {
                    "mID": 2,
                    "统一社会信用代码": "91330201144107528M",
                    "荣誉名称和内容": "-1",
                    "获得荣誉时间": "2018-07-25",
                    "状态": "有效",
                    "编号": "15553"
                },
                {
                    "mID": 3,
                    "统一社会信用代码": "91330602146062685F",
                    "荣誉名称和内容": "-1",
                    "获得荣誉时间": "2018-03-08",
                    "状态": "有效",
                    "编号": "15248"
                },
                {
                    "mID": 4,
                    "统一社会信用代码": "91330225691361058X",
                    "荣誉名称和内容": "-1",
                    "获得荣誉时间": "2018-03-08",
                    "状态": "有效",
                    "编号": "14988"
                },
                {
                    "mID": 5,
                    "统一社会信用代码": "91330300720006013W",
                    "荣誉名称和内容": "-1",
                    "获得荣誉时间": "2018-07-25",
                    "状态": "有效",
                    "编号": "15603"
                },
                {
                    "mID": 6,
                    "统一社会信用代码": "91330783147520019P",
                    "荣誉名称和内容": "-1",
                    "获得荣誉时间": "2018-07-25",
                    "状态": "有效",
                    "编号": "15527"
                },
                {
                    "mID": 7,
                    "统一社会信用代码": "9133000072008517XG",
                    "荣誉名称和内容": "-1",
                    "获得荣誉时间": "2018-08-10",
                    "状态": "有效",
                    "编号": "15738"
                },
                {
                    "mID": 8,
                    "统一社会信用代码": "91331124148638326R",
                    "荣誉名称和内容": "-1",
                    "获得荣誉时间": "2018-03-08",
                    "状态": "有效",
                    "编号": "15401"
                },
                {
                    "mID": 9,
                    "统一社会信用代码": "91330203144089833Y",
                    "荣誉名称和内容": "-1",
                    "获得荣誉时间": "2018-03-08",
                    "状态": "有效",
                    "编号": "14987"
                },
                {
                    "mID": 10,
                    "统一社会信用代码": "913302051445477776",
                    "荣誉名称和内容": "-1",
                    "获得荣誉时间": "2018-07-25",
                    "状态": "有效",
                    "编号": "15565"
                },
                {
                    "mID": 11,
                    "统一社会信用代码": "91330109143459556P",
                    "荣誉名称和内容": "2016年度浙江省标化工地",
                    "获得荣誉时间": "2016-12-30",
                    "状态": "有效",
                    "编号": "13348"
                },
                {
                    "mID": 12,
                    "统一社会信用代码": "91330106143251894C",
                    "荣誉名称和内容": "-1",
                    "获得荣誉时间": "2018-07-25",
                    "状态": "有效",
                    "编号": "15484"
                },
                {
                    "mID": 13,
                    "统一社会信用代码": "91330482727629598Y",
                    "荣誉名称和内容": "2016年度浙江省标化工地",
                    "获得荣誉时间": "2016-12-30",
                    "状态": "有效",
                    "编号": "13637"
                },
                {
                    "mID": 14,
                    "统一社会信用代码": "913307017511924292",
                    "荣誉名称和内容": "2016年度浙江省标化工地",
                    "获得荣誉时间": "2016-12-30",
                    "状态": "有效",
                    "编号": "14352"
                },
                {
                    "mID": 15,
                    "统一社会信用代码": "91330106256271891J",
                    "荣誉名称和内容": "-1",
                    "获得荣誉时间": "2018-07-25",
                    "状态": "有效",
                    "编号": "15478"
                },
                {
                    "mID": 16,
                    "统一社会信用代码": "91330800586292759X",
                    "荣誉名称和内容": "2016年度浙江省标化工地",
                    "获得荣誉时间": "2016-12-30",
                    "状态": "有效",
                    "编号": "13572"
                },
                {
                    "mID": 17,
                    "统一社会信用代码": "9133010414308239XR",
                    "荣誉名称和内容": "2016年度浙江省标化工地",
                    "获得荣誉时间": "2016-12-30",
                    "状态": "有效",
                    "编号": "13991"
                },
                {
                    "mID": 18,
                    "统一社会信用代码": "91330481795566496D",
                    "荣誉名称和内容": "-1",
                    "获得荣誉时间": "2018-03-08",
                    "状态": "有效",
                    "编号": "15161"
                },
                {
                    "mID": 19,
                    "统一社会信用代码": "913300001429123557",
                    "荣誉名称和内容": "-1",
                    "获得荣誉时间": "2018-07-25",
                    "状态": "有效",
                    "编号": "15508"
                },
                {
                    "mID": 20,
                    "统一社会信用代码": "913311007772225263",
                    "荣誉名称和内容": "-1",
                    "获得荣誉时间": "2018-08-10",
                    "状态": "有效",
                    "编号": "15749"
                }
            ],
            "first_page_url": "http://localhost/api/award/company?page=1",
            "from": 1,
            "next_page_url": "http://localhost/api/award/company?page=2",
            "path": "http://localhost/api/award/company",
            "per_page": 20,
            "prev_page_url": null,
            "to": 20
        },
        "has_more": true
    },
    "msg": "success"
}
```
{% endtab %}
{% endtabs %}
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



