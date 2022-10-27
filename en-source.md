---

copyright:
  years: 2020, 2022
lastupdated: "2022-10-26"

keywords: event-notifications, event notifications, about event notifications

subcollection: event-notifications

---

{{site.data.keyword.attribute-definition-list}}

# Event sources
{: #en-source}

An event source is a service or application on {{site.data.keyword.cloud_notm}} that emits event notifications and publishes them to a topic within the {{site.data.keyword.en_short}} service. A source is a registered entity in an {{site.data.keyword.en_short}} service instance. A source can be registered to an {{site.data.keyword.en_short}} service instance either as an `{{site.data.keyword.cloud_notm}} source` or an `API source` or an `{{site.data.keyword.cloud_notm}} platform source`.
{: shortdesc}

A source can publish to multiple topics. In other contexts sources are identified as producers or publishers.

## {{site.data.keyword.cloud_notm}} sources
{: #en-ibm-sources-list}

The list of IBM provided sources is as follows:
- [{{site.data.keyword.monitoringfull_notm}}](https://{DomainName}/docs/monitoring?topic=monitoring-notifications){: external}
- [{{site.data.keyword.secrets-manager_full_notm}}](https://{DomainName}/docs/secrets-manager?topic=secrets-manager-event-notifications&interface=ui){: external}
- [{{site.data.keyword.compliance_long}}](https://{DomainName}/docs/security-compliance?topic=security-compliance-event-notifications&interface=ui){: external}

## API sources
{: #en-api-sources}

You can send custom events from your backend application to the {{site.data.keyword.en_short}} service by using API sources. To do this, you need to add an `API source` first.

To add an {{site.data.keyword.cloud_notm}} source or an API source, complete the steps that are provided in the [Add an {{site.data.keyword.en_short}} source tutorial](/docs/event-notifications?topic=event-notifications-en-add-source)

## {{site.data.keyword.cloud_notm}} platform sources
{: #en-ibm-cloud-platform-sources}

- [{{site.data.keyword.cloud_notm}} Platform Notifications](https://{DomainName}/docs/account?topic=account-add-users-distribution-list#event-notifications-distribution-list){: external}
