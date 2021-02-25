# 便民服务点

{% api-method method="get" host="https://test-server.build-dream.cn" path="/api/convenient/point" %}
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

```php
{    "name": "Cake's {
    "code": 200,
    "data": {
        "items": {
            "current_page": 1,
            "data": [
                {
                    "mID": 1,
                    "序号": 10002592,
                    "服务点名称": "修自行车",
                    "经度": 120.169814,
                    "纬度": 30.245027
                },
                {
                    "mID": 2,
                    "序号": 10002722,
                    "服务点名称": "修自行车",
                    "经度": 120.204005082226,
                    "纬度": 30.2450894680609
                },
                {
                    "mID": 3,
                    "序号": 10002599,
                    "服务点名称": "修鞋",
                    "经度": 120.18247824411,
                    "纬度": 30.2523240477394
                },
                {
                    "mID": 4,
                    "序号": 10002971,
                    "服务点名称": "修自行车",
                    "经度": 119.933195,
                    "纬度": 30.045384
                },
                {
                    "mID": 5,
                    "序号": 10002798,
                    "服务点名称": "修鞋",
                    "经度": 120.146207580929,
                    "纬度": 30.270788426753
                },
                {
                    "mID": 6,
                    "序号": 10002749,
                    "服务点名称": "织补、缝补",
                    "经度": 120.194697843421,
                    "纬度": 30.2784443625496
                },
                {
                    "mID": 7,
                    "序号": 10002898,
                    "服务点名称": "修鞋",
                    "经度": 120.055071,
                    "纬度": 30.242679
                },
                {
                    "mID": 8,
                    "序号": 10002853,
                    "服务点名称": "织补、缝补",
                    "经度": 120.165344,
                    "纬度": 30.251781
                },
                {
                    "mID": 9,
                    "序号": 10002844,
                    "服务点名称": "道宝通开锁店",
                    "经度": 120.298434,
                    "纬度": 30.425718
                },
                {
                    "mID": 10,
                    "序号": 10002937,
                    "服务点名称": "修自行车",
                    "经度": 119.952714,
                    "纬度": 30.054319
                },
                {
                    "mID": 11,
                    "序号": 10002928,
                    "服务点名称": "修鞋",
                    "经度": 119.958978,
                    "纬度": 30.048631
                },
                {
                    "mID": 12,
                    "序号": 10002583,
                    "服务点名称": "缝补",
                    "经度": 120.165362,
                    "纬度": 30.251798
                },
                {
                    "mID": 13,
                    "序号": 10002897,
                    "服务点名称": "织补、缝补",
                    "经度": 120.055119,
                    "纬度": 30.242684
                },
                {
                    "mID": 14,
                    "序号": 10002975,
                    "服务点名称": "修自行车",
                    "经度": 119.955594,
                    "纬度": 30.050216
                },
                {
                    "mID": 15,
                    "序号": 10002988,
                    "服务点名称": "修自行车",
                    "经度": 119.937608,
                    "纬度": 30.053671
                },
                {
                    "mID": 16,
                    "序号": 10002945,
                    "服务点名称": "修自行车",
                    "经度": 119.956295,
                    "纬度": 30.052141
                },
                {
                    "mID": 17,
                    "序号": 10002909,
                    "服务点名称": "织补、缝补",
                    "经度": 120.196761,
                    "纬度": 30.237409
                },
                {
                    "mID": 18,
                    "序号": 10002940,
                    "服务点名称": "修自行车",
                    "经度": 119.956344,
                    "纬度": 30.05132
                },
                {
                    "mID": 19,
                    "序号": 10002648,
                    "服务点名称": "修自行车",
                    "经度": 120.168132937287,
                    "纬度": 30.277322987014
                },
                {
                    "mID": 20,
                    "序号": 10002605,
                    "服务点名称": "织补、缝补",
                    "经度": 120.18457664305,
                    "纬度": 30.2520160750481
                }
            ],
            "first_page_url": "http://localhost/api/convenient/point?page=1",
            "from": 1,
            "next_page_url": "http://localhost/api/convenient/point?page=2",
            "path": "http://localhost/api/convenient/point",
            "per_page": 20,
            "prev_page_url": null,
            "to": 20
        },
        "has_more": true
    },
    "msg": "success"
}",    "recipe": "Cake's recipe name",    "cake": "Binary cake"}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



