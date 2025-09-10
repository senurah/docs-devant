# Usage Insights Overview

Devant provides comprehensive insights into APIs created within Devant. Usage insights provide a range of metrics, including API traffic, error rates, and latency, allowing you to monitor and optimize API performance effectively.

With Devant usage insights, you can:

- **Analyze API traffic**: Monitor the volume of requests and responses to understand usage patterns.
- **Track errors**: Identify and analyze errors to improve API reliability.
- **Monitor latency**: Measure and optimize the response times of your APIs.
- **Generate reports**: Generate detailed reports to keep stakeholders informed and support data-driven decision-making.
- **Configure alerts**: Set up alerts for specific events or thresholds to proactively manage API performance.
- **Obtain granular insights**: Obtain detailed information on a per-application, per-API, and per-user basis for more targeted analysis.
- **Drill down into data**: Dive deeper into data to perform root cause analysis.


By leveraging these insights, businesses can make informed decisions to enhance their API strategies and drive their digital transformation initiatives forward.

## View insights

To view usage insights, go to the [Devant Console](https://console.devant.dev/) and click **Insights**, and then click **Usage** in the left navigation menu.

If you are viewing insights on the Devant platform at the organization level, note the following:

- **Permission-based access**: Signed-in users can only view insights for integrations or projects that they have permission to access.
- **Data exclusion**: Insights exclude data from integrations you cannot access and the data related to deleted integrations.
- **Comprehensive view permission**: To view insights for all integrations, including deleted ones, across the organization regardless of project visibility, you must have the `View Organization Insights` permission under `OBSERVABILITY-MANAGEMENT` with the mapping level defined at the `Organization` level.
- **Admin role**: Users with the admin role have the `View Organization Insights` permission by default and can view organization-wide insights.
- **Configuring permissions**: For detailed steps on configuring permissions, see [Control Access in the Devant Console](../../administer/control-access-in-the-devant-console/).

By ensuring proper permissions are set, organizations can manage access to insights effectively while maintaining data security and relevance.

## Analyze statistics

Once you access the **Usage Insights** page, you can access the following subpages.

### Overview

The **Overview** page gives you a quick overview of the system status.

![Overview](../assets/img/monitoring-and-insights/usage-insights/overview.png)

The information displayed is as follows:

- **Total Traffic**

    ![Total traffic](../assets/img/monitoring-and-insights/usage-insights/overview-page-total-traffic.png){.cInlineImage-small}

    This widget displays the total traffic of the selected environment received during a given time interval. Both successful requests and failed requests are displayed. To investigate further, you can click the arrow icon on the bottom right corner of the widget to open the [**Traffic**](#traffic) page.

- **Error Request Count**

    ![Error request count](../assets/img/monitoring-and-insights/usage-insights/overview-page-error-request-count.png){.cInlineImage-small}

    This widget displays the total number of requests that have resulted in errors in your selected environment during the selected time range. You can investigate errors by clicking the arrow on the bottom right of the widget and opening the [**Errors**](#errors) page.

- **Average Error Rate**

    ![Average error rate](../assets/img/monitoring-and-insights/usage-insights/overview-page-error-rate.png){.cInlineImage-small}

    This widget displays the average error rate (i.e., error count/total request count) of the selected environment for a given time interval. You can use this widget as an indicator to understand the health of the system. If the error rate is high, you can investigate further by clicking the arrow on the bottom right of the widget and opening the [**Errors**](#errors) page.

- **95th Percentile Latency**

    ![95th percentile latency](../assets/img/monitoring-and-insights/usage-insights/overview-page-latency.png){.cInlineImage-small}

    This widget displays the 95th percentile of all API latencies in your selected environment for the given time interval. You can use this widget to determine whether the complete system operates under given SLAs. This metric provides the first indication of slow APIs. To investigate further, you can click the arrow on the bottom right of the widget to open the [**Latency**](#latency) page where you can further analyze the latency.

- **API Request Summary**

    ![API request summary](../assets/img/monitoring-and-insights/usage-insights/overview-page-timeline.png){.cInlineImage-full}

    This chart displays the total successful requests, the total requests that have resulted in errors, and the latency in a timeline. The y-axis on the left displays the request count and the error count. The x-axis shows time, and the y-axis on the right shows the latency in milliseconds. The granularity of the data points is decided based on the time range you have selected. The tooltip provides the exact value of all three metrics.

### Traffic

The **Traffic** page shows information related to the traffic that goes through your API management deployments. This includes API usage, application usage, resource usage, etc. You can use this page to investigate the usage of APIs and applications, traffic patterns, etc.

![Traffic](../assets/img/monitoring-and-insights/usage-insights/traffic-page-full.png)

You can filter the information displayed in the widgets as follows:

| **Filtering Option** | **Description** |
|--------------------|-------------------------------------------------------------------------------------------------|
| **By API**         | In the **API** field, you can select one or more APIs for which you want to view analytics. **All** is selected by default. Once you select an API, you can further filter by a specific application that uses the selected API via the **Application** field described below. |
| **By Application** | In the **Application** field, you can select the applications for which you want to view analytics. **All** is selected by default. The available applications are all the applications that have subscribed to one or more of the APIs you selected in the **API** field.|

You can view the following information for the APIs you have selected using the above filtering criteria:

- **API Usage Over Time**

     This timeline shows the count of API hits for the selected APIs. If multiple APIs are selected, the timeline shows each API in a separate line with a legend separating each line. You can also zoom in on a selected time range by selecting that area in the chart. To restore to the original view use the **Zoom-out** button on the top right-hand corner of the plot.

    ![API usage over time](../assets/img/monitoring-and-insights/usage-insights/api-usage-timeline.png){.cInlineImage-full}

- **API Usage By Application**

     This widget shows the per-application breakdown of requests for the APIs you selected. You can use the pie chart view or the line chart view. You can switch between the two views using the small icon at the upper-right corner of the widget.

    ![API usage by application](../assets/img/monitoring-and-insights/usage-insights/usage-by-application.png){.cInlineImage-half}

- **API Usage By Target**

     This widget shows the per-backend breakdown of requests for the APIs you selected. This information is useful when multiple APIs share the same backend that has traffic restrictions. You can use these stats to scale your backends proactively.

     ![API usage by target](../assets/img/monitoring-and-insights/usage-insights/usage-by-target.png){.cInlineImage-half}

- **API Resource Usage**

     This table shows a resource-level breakdown of API traffic. Each row represents an API resource and it shows the API name, resource path, API method, and the hit count for that combination.

     ![API resource usage](../assets/img/monitoring-and-insights/usage-insights/resource-usage.png)

### Errors

The **Errors** page shows information related to erroneous API calls received by your system. It allows you to analyze errors by both error categories and HTTP status codes.

- **Error Category View**: An error category represents a type of faulty scenario identified at the API gateway level. In these cases, the API request may not reach the API target, and the user will receive an error message and an HTTP error code. Errors are grouped into categories and subcategories based on their nature (such as authentication, connectivity, throttling, or other issues). The chart displays these categories and their subcategory errors, helping you quickly identify and analyze the types of errors occurring in your APIs.

- **Status Code View**: Status code-based insights provide information based on the HTTP status codes received by the client, regardless of whether the error was generated by the API gateway or the backend target. This is different from the error category chart, which groups errors by the type of faulty scenario identified at the gateway level. For example, an authentication error category may result in different status codes like 401 or 403, depending on the specific issue. These errors may not reach the target and are sent to the client by the gateway. Conversely, a request might pass through the gateway but be rejected by the target (e.g., a 403 due to a payload validation issue at the backend). In the status code chart, both errors would appear as 403 and 401, while in the category chart, they would be grouped under authentication errors. Thus, the status code view shows the distribution of error codes received by the client, independent of the error category, while the category view groups errors by their underlying cause.

Use this page as the starting point for debugging any API errors.

![Error statistics](../assets/img/monitoring-and-insights/usage-insights/error-page-full.png){.cInlineImage-full}

You can filter the information displayed in the widgets as follows:

| **Filtering Option** | **Description** |
|--------------------|-------------------------------------------------------------------------------------------------|
| **By API** | In the **API** field, select the APIs for which you want to view analytics. By default, all APIs are selected. You can select one or multiple APIs from this selector and view the aggregated result. |
| **By Category** | The **Category** field is displayed when you click **Category** in the upper right corner of the page. In this field, you can select one or all of the following error categories:<br/>**Authentication**: Any kind of authentication error falls into this category including expired/missing/invalid credentials.<br/>**Target Connectivity**: Any kind of backend error falls into this category including connection time-outs/other backend errors (for example, 4xx and 5xx status codes).<br/>**Throttling**: Any request that fails due to rate-limiting falls into this category including application throttling/subscription throttling.<br/>**Other**: All other errors fall into this category including mediation errors/resource not found errors. |
| **By Status Code** | The **Status Code** field is displayed when you click **Status Code** in the upper right corner of the page. In this field, you can select all or any available HTTP status code categories (4xx, 5xx, etc.). These status codes represent the response status of the API Gateway. |

#### Viewing errors by category

The following widgets are available for monitoring errors when you have selected **Category** in the upper-right corner of the page.

- This graph shows the error by category over time for the selected period. Apply the required filters as explained above to select the APIs and the error categories to which this content applies. When you select multiple APIs, the error count is grouped by category.

    ![Errors by category graph](../assets/img/monitoring-and-insights/usage-insights/error-category-graph.png){.cInlineImage-full}

- This table provides further information about the errors such as application details and the error reason. For some authentication errors, the application name is not available. You can use this table to get more concrete information about the errors related to your APIs and then start the problem identification.

    ![Errors by category table](../assets/img/monitoring-and-insights/usage-insights/error-category-table.png){.cInlineImage-full}

#### Viewing errors by status code

The following widgets are available for monitoring errors when you select **Status Code** in the upper-right corner of the page.

- **Errors by Status Code**

    This graph shows the distribution of HTTP status codes received for errors over time for the selected period. Apply the required filters as explained above to select the APIs and status code groups to which this content applies. When you select multiple APIs, the error count is grouped by the status code.

    ![Errors by status code](../assets/img/monitoring-and-insights/usage-insights/error-by-status-code.png){.cInlineImage-full}

- **Target Errors by Status Code**

    This graph shows the distribution of target errors that have occurred during the selected time interval by HTTP status code. Apply the required filters as explained in the table above to view the APIs and status code groups to which this content applies. If you select multiple APIs, the widget groups the target error count by the status code.

    ![Target errors by status code](../assets/img/monitoring-and-insights/usage-insights/target-error-by-status-code.png){.cInlineImage-full}


- **Errors**

    The Errors heat map shows the HTTP response codes of errors sent to the client by the API Gateway. Each row displays the number of times the system returned each status code for the selected APIs. The cell color is red for higher numbers and white for lower numbers. If required, you can further filter the results by the error code groups you identified with the **Errors by Status Code** graph.

    ![Errors](../assets/img/monitoring-and-insights/usage-insights/error-heatmap.png){.cInlineImage-full}

- **Target Errors**

    The Target errors heat map shows the HTTP response codes of errors that the API Gateway received from the backend. Each row displays the number of times the system returned each status code for the selected APIs. The cell color is red for higher numbers and white for lower numbers. If required, you can further filter the results by the error code groups you identified with the **Target Errors by Status Code** graph.

    ![Target errors](../assets/img/monitoring-and-insights/usage-insights/target-error-heatmap.png){.cInlineImage-full}

### Latency

The **Latency** page shows information related to the latency of API calls within the API management deployment. You can view a summary of the slowest APIs and then drill down into the API view for further analysis. Use this page as a starting point to debug API slowness.

![Latency](../assets/img/monitoring-and-insights/usage-insights/latency-page-full.png){.cInlineImage-full}

The information displayed is as follows:

- **Top 10 Slowest APIs**

    This widget allows you to identify the slowest APIs of the API management system at a glance. Since these are the APIs that contribute to the higher 95th percentile of the system, improving these APIs lowers the 95th percentile of latency in the API Management deployments.

    ![Slowest APIs](../assets/img/monitoring-and-insights/usage-insights/slowest-apis.png){.cInlineImage-full}

- **Latencies By Category**

    This widget allows you to further drill down details in the above chart. Use the API selector in this widget to select the slow API you identified in the earlier step and then analyze further. Use the charts available in the widget to view the 95th percentile and the median latency over the selected period of the following:

      - Backend
      - Request mediation
      - Response mediation

    ![Latencies by category](../assets/img/monitoring-and-insights/usage-insights/latency-by-category.png){.cInlineImage-full}

  You can use these charts to further drill down and analyze whether the latency occurs in the backend, request mediation, or response mediation. Also, because you can see both the median and 95th percentile, you can easily identify whether the slowness is occurring in each request or whether it is intermittent.

### Cache

The **Cache** page shows statistics that indicate the efficiency with which response caching is carried out for the requests sent to your APIs.

![Cache statistics](../assets/img/monitoring-and-insights/usage-insights/cache-page-full.png){.cInlineImage-full}

The page displays the following statistics:

- **Cache Hit Percentage**

    This graph shows the percentage of requests the system has handled via the response cache over time and the total hits over time. This information allows you to assess how efficiently the backend handles API requests. For example, if the cache hit rate is low, it may indicate that the backend generates the same response each time a specific request is sent instead of returning the response via the cache. In such a scenario, there is scope to improve performance via response caching.

    ![Cache hit percentage](../assets/img/monitoring-and-insights/usage-insights/cache-statistics.png){.cInlineImage-full}

- **Latency**

    This section shows the total latency reported during the same time interval applied to the **Cache Hit Percentage** graph above.

    ![Cache hits and misses](../assets/img/monitoring-and-insights/usage-insights/cache-latency.png){.cInlineImage-full}

### Devices

The **Devices** page displays information about operating systems and HTTP agents that end users use to invoke the APIs. You can use this page to get an idea of the distribution of your user base and improve your APIs to match the audience.

![Device statistics](../assets/img/monitoring-and-insights/usage-insights/devices-page-full.png){.cInlineImage-full}

To filter the information displayed on this page by API, select the required API(s) in the **API** field. **All** is selected by default.

The information displayed is as follows:

- **Top Platforms**

    This chart shows the breakdown of the API clients by the operating system. The pie chart only shows platforms with a significant amount of requests. Other platforms are grouped under the **Other** category.

    ![Top platforms](../assets/img/monitoring-and-insights/usage-insights/top-platforms.png){.cInlineImage-half}

- **Top User Agents**

    This chart shows the breakdown of the API clients by user-agent. The pie chart only shows user agents with a significant amount of requests. Other platforms are grouped under the **Other** category.

    ![Top user agents](../assets/img/monitoring-and-insights/usage-insights/top-user-agents.png){.cInlineImage-half}

### Alerts

The **Alerts** page shows information related to business alerts issued by Devant for your currently selected environment and organization. You can use this page as a health monitoring dashboard and make it visible to your project team. On this page, you can drill down on each alert and discover possible anomalies in your published APIs. See the topics given below to get details of the available widgets and understand how to use them effectively.

![Alerts statistics](../assets/img/monitoring-and-insights/usage-insights/alerts-page-full.png){.cInlineImage-full}

**Prerequisites**

To use this page, be sure to configure alerts and have API invocations that trigger alerts. 

!!! Note
    Alerts are retained only for one week.

- **Alert Summary**

    This table lists each alert generated during the selected time interval. The message of the alert can be viewed by expanding the arrow icon on the details column. The drop-downs can be used to filter alerts based on the alert type and API.

    ![Alert summary](../assets/img/monitoring-and-insights/usage-insights/alert-summary.png){.cInlineImage-full}

- **Top APIs by Alert Count**

    This shows a pie chart and a table to visualize the alert distribution during the selected time interval.

    ![Top APIs by alert count](../assets/img/monitoring-and-insights/usage-insights/top-apis-by-alert-count.png){.cInlineImage-full}

### Reports

The **Reports** page allows you to download monthly usage reports for your system. There are preconfigured reports with system-wide statistics, and a custom report generator to generate reports based on a subset of APIs/applications.

![Report page](../assets/img/monitoring-and-insights/usage-insights/report-page-full.png){.cInlineImage-full}

#### Download custom reports

This widget allows you to generate a custom report for the statistics that have been generated up to now and download it.

![Custom report download](../assets/img/monitoring-and-insights/usage-insights/custom-report.png){.cInlineImage-full}

To generate a custom report, follow the steps below:

1. In the **API** field, select one or more APIs for which you want to generate the report. If required, you can select all the APIs by selecting **All**.

2. If you need to further filter the content printed in the report, select one or more applications in the **Consumer** field. By default, all the applications that have subscribed to one or more of the selected APIs are selected.

    !!! Tip
        If you want to filter the report content by the API consumer instead of the application, click the toggle switch to the right of the **Consumer** field, and then select the required consumer. Only consumers who have subscribed to one or more of the selected APIs are displayed in the list. You can either select one or all of them.

3. Select the required year and the month in the **Year** and **Month** fields to specify the time interval for which you want to generate the report.

4. Click **Download** and select the required format.

The report is downloaded in the specified format.

The contents of the report are as follows.

| **Item** | **Description** |
|-------------------------|--------------------------------------------------------------------------------------------|
| **Generated Time**            | The date and the time the report was generated.                                            |
| **Organization**              | The organization to which the report applies. Each report always applies to a specific organization.                   |
| **Environment**               | The environment to which the report applies. Each report always applies to a specific environment.                            |
| **Reporting period**          | The time interval for which the report is generated.                                            |
| **Total request count**       | The total request count received by all selected APIs during the report time interval.                                        |
| **Total successful requests** | The total count of successful requests received by all selected APIs during the report time interval.                      |
| **Total failed requests**     | The total count of failed requests received by all selected APIs during the report time interval.                            |

The table in the report contains the following columns.

| **Item**        | **Description**                                                                           |
|-----------------|-------------------------------------------------------------------------------------------|
| **#**           | The sequential number of the row.                                                         |
| **API**         | The name of the API.                                                                      |
| **Application** | The name of the application. The name of the subscriber is also provided within brackets. |
| **Total**       | The total count of requests received by the API during the report time interval.          |
| **Successes**   | The count of successful requests received by the API during the report time interval.     |
| **Failures**    | The count of failed requests received by the API during the report time interval.         |

#### Download pregenerated reports

The widgets shown below allow you to download monthly reports for the last three months.

![Pre-generated reports](../assets/img/monitoring-and-insights/usage-insights/configured-report.png){.cInlineImage-half}

To download a pregenerated report, click **Download** for the relevant month and then click on the required format.