---

copyright:
  years: 2020, 2022
lastupdated: "2022-10-26"

keywords: data encryption in Event Notifications, data storage for Event Notifications, bring your own keys for Event Notifications, BYOK for Event Notifications, key management for Event Notifications, key encryption for Event Notifications, personal data in Event Notifications, data deletion for Event Notifications, data in Event Notifications, data security in Event Notifications, KYOK for Event Notifications

subcollection: event-notifications

---

{{site.data.keyword.attribute-definition-list}}

# Securing your data in {{site.data.keyword.en_short}}
{: #en-mng-data}

To ensure that you can securely manage your data when you use {{site.data.keyword.en_full}}, you must know exactly what data is stored and encrypted and you must know how to delete any stored data.
{: shortdesc}

## How your data is stored and encrypted in {{site.data.keyword.en_short}}
{: #en-data-storage}

{{site.data.keyword.en_short}} stores and encrypts details that are related to your destinations like email (sender, recipients, subject), or SMS (sender, recipient, details). As a multi-tenant service, every tenant has a designated encryption key and user data in each tenant is encrypted with only that tenant's key. This tenant key is protected by using {{site.data.keyword.en_short}} managed Key Protect. {{site.data.keyword.en_short}} ensures that private information is encrypted before it is stored.

## Protecting your sensitive data in {{site.data.keyword.en_short}}
{: #en-data-encryption}

The data that you store in the {{site.data.keyword.en_short}} instance is encrypted at rest by using a randomly generated key, which is in turn protected by Key Protect, managed by {{site.data.keyword.en_short}} service.

## Deleting your data in {{site.data.keyword.en_short}}
{: #en-data-delete}

The {{site.data.keyword.en_short}} data retention policy describes how long your data is stored after you delete the service. As in {{site.data.keyword.cloud_notm}} data retention policy you can [restore](/docs/account?topic=account-resource-reclamation&interface=cli#restore-resource-cli) a resource within 7 days after you delete it.

### Commands to delete data
{: #en-data-delete-cmd}

1. Log in to your {{site.data.keyword.cloud_notm}} account by using {{site.data.keyword.cloud_notm}} CLI from terminal.
1. `ibmcloud resource reclamations` lists your deleted instance along with the reclamation ID for it.
1. Use `ibmcloud resource reclamation-delete <reclamation_id_for_instance>` to permanently delete data that is related to a deleted instance.
1. If an instance is not restored, all related data is automatically deleted after the data retention period.

### Deleting {{site.data.keyword.en_short}} instances
{: #en-delete}

If you no longer need an instance of {{site.data.keyword.en_short}}, you can delete the service instance by using {{site.data.keyword.cloud_notm}} CLI. You can also choose to delete your service instance by using the console. Any data that is stored related to that instance is also deleted.

### Restoring deleted data for {{site.data.keyword.en_short}}
{: #en-data-restore}

To restore a deleted instance or to delete the instance permanently, you can use Resource Reclamations. For more information about resource reclamation, see [Using Resource Reclamations](/docs/account?topic=account-resource-reclamation).
