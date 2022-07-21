---

copyright:
  years: 2021, 2022
lastupdated: "2022-07-21"

keywords: event-notification, event notification, high availability, ha, monitoring, metrics, monitor apps

subcollection: event-notifications

---

{{site.data.keyword.attribute-definition-list}}

# Monitor {{site.data.keyword.en_short}} service metrics with {{site.data.keyword.mon_full_notm}}
{: #en-monitoring}

Use {{site.data.keyword.mon_full_notm}} to gain operational visibility into the performance and health of your applications, services, and platforms. It offers administrators, DevOps teams, and developers full stack telemetry with advanced features to monitor and troubleshoot, define alerts, and design custom dashboards.
{: shortdesc}

## Set up your {{site.data.keyword.mon_full_notm}} service instance
{: #en-setup-monitor}

To get started, you need to [provision {{site.data.keyword.cloud_notm}} Monitoring](https://cloud.ibm.com/catalog/services/ibm-cloud-monitoring?callback=/observe/monitoring/create) instance on your {{site.data.keyword.IBM}} account. See [Provisioning an instance](https://cloud.ibm.com/docs/monitoring?topic=monitoring-provision) for more details.


Currently, {{site.data.keyword.mon_full_notm}} integration is available for {{site.data.keyword.en_short}} service deployments in the following regions:

| Deployment region | Monitoring region |
|-------------|-------------|
| Dallas| Dallas|
| London| London|
| Sydney| Sydney|
| Frankfurt| Frankfurt|
{: caption="Table 1. Deployment regions" caption-side="bottom"}

Before you can start with {{site.data.keyword.en_short}} monitoring metrics, you must first opt in and [enable platform metrics](https://cloud.ibm.com/docs/monitoring?topic=monitoring-platform_metrics_enabling)
{: note}

You can configure only one instance of the {{site.data.keyword.mon_full_notm}} service per region to collect platform metrics.

- To configure the {{site.data.keyword.mon_full_notm}} instance, you must turn on the platform metrics configuration setting.
- If a monitoring instance in a region is already enabled to collect platform metrics, metrics from enabled-monitoring services are collected automatically and available for monitoring through this instance. For more information about enabled-monitoring services, see {{site.data.keyword.cloud}} services.

To monitor platform metrics, check that the {{site.data.keyword.mon_full_notm}} instance is provisioned in the same region where the {{site.data.keyword.cloud_notm}} instance is provisioned.
{: note}

## Access your {{site.data.keyword.mon_full_notm}} metrics
{: #en-access-monitor}

1. Launch the [{{site.data.keyword.mon_full_notm}} web UI](https://cloud.ibm.com/docs/monitoring?topic=monitoring-launch) from the `Observability` page.

1. Click `DASHBOARDS`.

1. In the `Default Dashboards` section, expand `IBM`.

1. Choose the `{{site.data.keyword.en_short}}` dashboard from the list.

Access your deployment's monitoring dashboard from {{site.data.keyword.mon_full_notm}}, it's in the sidebar, under `IBM`.
Next, change the scope or make a copy of the default dashboard to monitor an {{site.data.keyword.en_short}} service instance.

## Metrics available by Service Plan
{: #en-metrics-by-plan}

| Metric Name |
| ------------|
| [ibm_eventnotifications_total_ingested_notifications](#ibm_eventnotifications_total_ingested_notifications)|
| [ibm_eventnotifications_total](#ibm_eventnotifications_total)|
| [ibm_eventnotifications_failed](#ibm_eventnotifications_failed)|
| [ibm_eventnotifications_devices](#ibm_eventnotifications_devices)|
{: caption="Table 2. Metrics available by service plan" caption-side="bottom"}

### ibm_eventnotifications_total_ingested_notifications
{: #ibm_eventnotifications_total_ingested_notifications}

Total number of notifications that are ingested. Ingested notifications are events from a source that has at least one condition that is defined on them for filtering.

| Metadata   | Description |
|-------------|-------------|
| `Metric Name` | `ibm_eventnotifications_total_ingested_notifications` |
| `Metric Type` | `gauge`|
| `Value Type` | `none`|
| `Segment By` | `ibm_scope`, `ibm_ctype`, `ibm_location`,  `ibm_service_name`, `ibm_service_instance`, `ibm_eventnotifications_source`  |
{: caption="Table 3. Ingestion metadata" caption-side="bottom"}

### ibm_eventnotifications_total
{: #ibm_eventnotifications_total}

Total number of notifications for a particular type including successful and failed notifications

| Metadata   | Description |
|-------------|-------------|
| `Metric Name` | `ibm_eventnotifications_total` |
| `Metric Type` | `gauge`|
| `Value Type` | `none`|
| `Segment By` | `ibm_scope`, `ibm_ctype`, `ibm_location`,  `ibm_service_name`, `ibm_service_instance`, `ibm_eventnotifications_source`, `ibm_eventnotifications_destination`, `ibm_eventnotifications_source`, `ibm_eventnotifications_type`|
{: caption="Table 4. Notifications metadata" caption-side="bottom"}

### ibm_eventnotifications_failed
{: #ibm_eventnotifications_failed}

Total number of failed notifications of a particular type.

| Metadata   | Description |
|-------------|-------------|
| `Metric Name` | `ibm_eventnotifications_failed` |
| `Metric Type` | `gauge`|
| `Value Type` | `none`|
| `Segment By` | `ibm_scope`, `ibm_ctype`, `ibm_location`,  `ibm_service_name`, `ibm_service_instance`, `ibm_eventnotifications_destination`, `ibm_eventnotifications_source`, `ibm_eventnotifications_type`,  |
{: caption="Table 5. Failed notifications metadata" caption-side="bottom"}

### ibm_eventnotifications_devices
{: #ibm_eventnotifications_devices}

Total number of push notification devices registered.

| Metadata   | Description |
|-------------|-------------|
| `Metric Name` | `ibm_eventnotifications_devices` |
| `Metric Type` | `gauge`|
| `Value Type` | `none`|
| `Segment By` | `ibm_scope`, `ibm_ctype`, `ibm_location`,  `ibm_service_name`, `ibm_service_instance`, `ibm_eventnotifications_destination`,  `ibm_eventnotifications_device_type`,  |
{: caption="Table 6. Total devices registered" caption-side="bottom"}

## Attributes for segmentation
{: #attributes-en}

### Global Attributes
{: #global-attributes-en}

The following attributes are available for segmenting all of the metrics previously listed.

| Attribute | Attribute Name | Attribute Description |
|-----------|----------------|-----------------------|
| `Cloud Type` | `ibm_ctype` | The cloud type is a value of `public`, `dedicated`, or `local`. |
| `Location` | `ibm_location` | The location of the monitored resource, which can be a region, data center, or global. |
| `Scope` | `ibm_scope` | The scope is the account, organization, or space GUID associated with this metric. |
| `Service instance` | `ibm_service_instance` | The service instance segment identifies the instance that the metric is associated with. |
{: caption="Table 7. Segmentation attributes" caption-side="bottom"}

### More attributes
{: #additional-attributes-en}

The following attributes are available for segmenting one or more attributes as described in the previous tables. See the individual metrics for segmentation options.

| Attribute | Attribute Name | Attribute Description |
|-----------|----------------|-----------------------|
| `Name of the destination` | `ibm_eventnotifications_destination` | A destination name with its associated id. |
| `Name of the source` | `ibm_eventnotifications_source` | A source name with its associated id. |
| `Type of event notification` | `ibm_eventnotifications_type` | The type of supported destination types. (email, sms or webhook) |
| `Type of push notification device` | `ibm_eventnotifications_device_type` | The type of supported push notification device.(push_android, push_ios) |
{: caption="Table 8. More attributes" caption-side="bottom"}
