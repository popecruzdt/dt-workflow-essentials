## Query External Data

#### `http_easytravel_search`
Name:
```text
http_easytravel_search
```
Description:
```text
Query external easytravel API for journey data
```

This will be the task/action that queries external data from an api endpoint that contains our metric data point.

Locate the `js_set_parameters` task.

Click the `+` button to add a new action to the Workflow.

Choose action: choose `HTTP Request` action type.

Set the task name and description respectively.

Configure the HTTP Request action `Input`:

Method:
```
GET
```

URL:
```
{{ result("js_set_parameters")['EASYTRAVEL_URL'] }}
```

Headers:
```
accept  application/json
```

Error Handling:
```
Fail on certain HTTP response codes [Enabled]
```

HTTP error codes:
```
400-599
```

Click on the task's `Conditions` tab.  Set the `Run this task if`: `js_set_parameters` is `success`

Additionally, we only want this task to run if the `EASYTRAVEL_URL` parameter is defined in the previous task.  We can access the result using a Jinja expression:
```js
1. {{ result("task_name") }}
2. {{ result("task_name")['result_attribute_name'] }}
3. {{ result("task_name")['result_attribute_name'] condition expression }}
```

[Expression Reference Documentation](https://docs.dynatrace.com/docs/platform-modules/automations/workflows/reference)

Set the `And custom condition was met`:
```
{{ result("js_set_parameters")['EASYTRAVEL_URL'] is defined }}
```

![../../../assets/images/03-http-easytravel-search-input.png](../../../assets/images/03-http-easytravel-search-input.png)

Run the workflow and validate the results

![../../../assets/images/03-http-easytravel-search-results.png](../../../assets/images/03-http-easytravel-search-results.png)