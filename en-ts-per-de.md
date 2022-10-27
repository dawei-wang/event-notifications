---

copyright:
  years: 2019, 2022
lastupdated: "2022-10-26"

keywords: question about event notifications, permission, integrating, authorization, authorize

subcollection: event-notifications

content-type: troubleshoot

---

{{site.data.keyword.attribute-definition-list}}

# Why am I denied permission to integrate an {{site.data.keyword.en_short}} instance?
{: #troubleshoot-integrate}
{: troubleshoot}
{: support}

You are denied permission while integrating an {{site.data.keyword.en_short}} service instance with an IBM Cloud Service.
{: shortdesc}

You get a 'Permission denied' message, while integrating {{site.data.keyword.en_short}} service instance with IBM Cloud service.
{: tsSymptoms}

{{site.data.keyword.en_short}} integration APIs use Service to Service [authorization](/docs/get-coding?topic=get-coding-grant-access){: external}.
{: tsCauses}

Grant authorization between the IBM Cloud Service (for example: Security and Compliance Center) and {{site.data.keyword.en_short}} service instance.
{: tsResolve}

Manage --> Access (IAM) --> Authorization --> Create

![Create authorization](images/en-ts-authorize.png "Authorize event notifications in SCC"){: caption="Figure 1. Grant authorization" caption-side="bottom"}
