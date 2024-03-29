---

copyright:
  years: 2017, 2019
lastupdated: "2019-09-16"

keywords: Key Protect integration, integrate service with Key Protect

subcollection: key-protect

---

{:shortdesc: .shortdesc}
{:screen: .screen}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:external: target="_blank" .external}
{:codeblock: .codeblock}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Integrating services
{: #integrate-services}

{{site.data.keyword.keymanagementservicefull}} integrates with a number of {{site.data.keyword.cloud_notm}} services to enable encryption with customer-managed keys for those services. Encryption with customer-managed encryption keys is sometimes called Bring Your Own Key (BYOK).
{: shortdesc}

You can integrate {{site.data.keyword.keymanagementserviceshort}} with the following supported services.

| Service       | Description                 | Link |
| ------------- | ------------------------------------ | ---- |
| [{{site.data.keyword.cloudant_short_notm}} for {{site.data.keyword.cloud_notm}} ({{site.data.keyword.cloud_notm}} Dedicated)](/docs/services/Cloudant?topic=cloudant-ibm-cloud-dedicated) | {{site.data.keyword.cloudant_short_notm}} is a document-oriented database as a service (DBaaS). It stores data as documents in JSON format. | [View docs](/docs/services/Cloudant/offerings?topic=cloudant-security#secure-access-control) |
| [{{site.data.keyword.databases-for-elasticsearch_full_notm}}](/docs/services/databases-for-elasticsearch?topic=databases-for-elasticsearch-about#about-databases-for-elasticsearch) | {{site.data.keyword.databases-for-elasticsearch_full_notm}} is a managed Elasticsearch service that is hosted in the {{site.data.keyword.cloud_notm}} and integrated with other {{site.data.keyword.cloud_notm}} services.| [View docs](/docs/services/databases-for-elasticsearch?topic=cloud-databases-key-protect) |
| [{{site.data.keyword.databases-for-etcd_full_notm}}](/docs/services/databases-for-etcd?topic=databases-for-etcd-about#about-databases-for-etcd) | {{site.data.keyword.databases-for-etcd_full_notm}} is a managed etcd service that is hosted in the {{site.data.keyword.cloud_notm}} and integrated with other {{site.data.keyword.cloud_notm}} services.| [View docs](/docs/services/databases-for-etcd?topic=cloud-databases-key-protect)|
| [{{site.data.keyword.databases-for-mongodb_full_notm}}](/docs/services/databases-for-mongodb?topic=databases-for-mongodb-about) | {{site.data.keyword.databases-for-mongodb_full_notm}} is a managed MongoDB service that is hosted in the {{site.data.keyword.cloud_notm}} and integrated with other {{site.data.keyword.cloud_notm}} services. | [View docs](/docs/services/databases-for-mongodb?topic=cloud-databases-key-protect)|
| [{{site.data.keyword.databases-for-postgresql_full_notm}}](/docs/services/databases-for-postgresql?topic=databases-for-postgresql-about#about) | {{site.data.keyword.databases-for-postgresql_full_notm}} is a managed PostgreSQL service that is hosted in the {{site.data.keyword.cloud_notm}} and integrated with other {{site.data.keyword.cloud_notm}} services. | [View docs](/docs/services/messages-for-postgresql?topic=cloud-databases-key-protect)|
| [{{site.data.keyword.databases-for-redis_full_notm}}](/docs/services/databases-for-redis?topic=databases-for-redis-about#about-databases-for-redis) | {{site.data.keyword.databases-for-redis_full_notm}} is a managed service that is hosted in the {{site.data.keyword.cloud_notm}} and integrated with other {{site.data.keyword.cloud_notm}} services.| [View docs](/docs/services/messages-for-redis?topic=cloud-databases-key-protect)|
| [{{site.data.keyword.messages-for-rabbitmq_full_notm}}](/docs/services/messages-for-rabbitmq?topic=messages-for-rabbitmq-about#about-messages-for-rabbitmq)  | {{site.data.keyword.messages-for-rabbitmq_full_notm}} is a managed RabbitMQ service that is hosted in the {{site.data.keyword.cloud_notm}} and integrated with other {{site.data.keyword.cloud_notm}} services. | [View docs](/docs/services/messages-for-rabbitmq?topic=cloud-databases-key-protect) |
| [{{site.data.keyword.sqlquery_short}}](/docs/services/sql-query?topic=sql-query-overview#overview) | You can use the {{site.data.keyword.sqlquery_short}} service to run SQL queries (that is, SELECT statements) to analyze, transform, or clean up rectangular data. |[View docs](/docs/services/sql-query?topic=sql-query-keyprotect) |
{: caption="Table 1. Supported data services" caption-side="top"}
{: #table-1}
{: tab-title="Data"}
{: tab-group="supported-services"}
{: class="simple-tab-table"}

| Service        | Description             | Link |
| ------------- | ---------------------------- | ---- |
| [{{site.data.keyword.block_storage_is_short}}](/docs/vpc-on-classic-block-storage?topic=vpc-on-classic-block-storage-getting-started)| You can use {{site.data.keyword.block_storage_is_short}} to provide hypervisor-mounted, high-performance data storage for virtual server instances (instances) in your VPC. | [View docs](/docs/vpc-on-classic-block-storage?topic=vpc-on-classic-block-storage-block-storage-encryption) |
| [{{site.data.keyword.cos_full_notm}}](/docs/services/cloud-object-storage?topic=cloud-object-storage-getting-started)| You can use {{site.data.keyword.cos_full_notm}} to store unstructured data in the {{site.data.keyword.cloud_notm}}. | [View docs](/docs/services/cloud-object-storage?topic=cloud-object-storage-encryption#encryption-kp)|
{: caption="Table 2. Supported storage services" caption-side="top"}
{: #table-2}
{: tab-title="Storage"}
{: tab-group="supported-services"}
{: class="simple-tab-table"}

| Service        | Description             | Link |
| ------------- | ---------------------------- | ---- |
| [{{site.data.keyword.cloud_notm}} image templates](/docs/infrastructure/image-templates?topic=image-templates-about-image-templates) | You can use {{site.data.keyword.cloud_notm}} image templates to capture an image of a virtual server to quickly replicate its configuration with minimal changes in the order process. With the End to End (E2E) Encryption feature, you can bring your own encrypted, cloud-init enabled operating system image. | [View docs](/docs/infrastructure/image-templates?topic=image-templates-using-end-to-end-e2e-encryption-to-provision-an-encrypted-instance)
| [KMIP for VMware](/docs/services/vmwaresolutions?topic=vmware-solutions-kmip-overview) | KMIP for VMware works together with VMware native vSphere encryption and vSAN encryption to provide simplified storage encryption management together with the security and flexibility of {{site.data.keyword.keymanagementserviceshort}} or Hyper Protect Crypto Services customer-managed keys. | [View docs](https://cloud.ibm.com/docs/services/vmwaresolutions/services?topic=vmware-solutions-kmip_standalone_considerations)|
| [{{site.data.keyword.vsi_is_short}}](/docs/vpc-on-classic-vsi?topic=vpc-on-classic-vsi-virtual-private-cloud) | You can use {{site.data.keyword.vsi_is_short}} to create an instance that consists of your virtual compute resources and resulting capacity within an {{site.data.keyword.vpc_short}}. | [View docs](/docs/vpc-on-classic-vsi?topic=vpc-on-classic-vsi-creating-instances-byok) |
{: caption="Table 3. Supported compute services" caption-side="top"}
{: #table-3}
{: tab-title="Compute"}
{: tab-group="supported-services"}
{: class="simple-tab-table"}

| Service       | Description                 | Link |
| ------------- | ------------------------------------ | ---- |
| [{{site.data.keyword.containerlong_notm}}](/docs/containers?topic=containers-getting-started)  | You can use the {{site.data.keyword.containerlong_notm}} service to deploy highly available apps in Docker containers that run in Kubernetes clusters.| [View docs](/docs/containers?topic=containers-encryption#keyprotect) |
{: caption="Table 4. Supported containers services" caption-side="top"}
{: #table-4}
{: tab-title="Containers"}
{: tab-group="supported-services"}
{: class="simple-tab-table"}


## Understanding your integration 
{: #understand-integration}

When you integrate a supported service with {{site.data.keyword.keymanagementserviceshort}}, you enable [envelope encryption](/docs/services/key-protect?topic=key-protect-envelope-encryption) for that service. This integration allows you to use a root key that you store in {{site.data.keyword.keymanagementserviceshort}} to wrap the data encryption keys that encrypt your data at rest. 

For example, you can create a root key, manage the key in {{site.data.keyword.keymanagementserviceshort}}, and use the root key to protect the data that is stored across different cloud services.

![The diagram shows a contextual view of your {{site.data.keyword.keymanagementserviceshort}} integration.](../images/kp-integrations.svg)

### {{site.data.keyword.keymanagementserviceshort}} API methods
{: #envelope-encryption-api-methods}

Behind the scenes, the {{site.data.keyword.keymanagementserviceshort}} API drives the envelope encryption process.  

The following table lists the API methods that add or remove envelope encryption on a resource.

| Method | Description |
| --- | --- |
| `POST /keys/{root_key_ID}?action=wrap` | [Wrap (encrypt) a data encryption key](/docs/services/key-protect?topic=key-protect-wrap-keys) |
| `POST /keys/{root_key_ID}?action=unwrap` | [Unwrap (decrypt) a data encryption key](/docs/services/key-protect?topic=key-protect-unwrap-keys) |
{: caption="Table 2. Describes the {{site.data.keyword.keymanagementserviceshort}} API methods" caption-side="top"}

To find out more about programmatically managing your keys in {{site.data.keyword.keymanagementserviceshort}}, check out the [{{site.data.keyword.keymanagementserviceshort}} API reference doc](https://{DomainName}/apidocs/key-protect){: external}.
{: tip}

## Integrating a supported service
{: #grant-access}

To add an integration, create an authorization between services by using the {{site.data.keyword.iamlong}} dashboard. Authorizations enable service to service access policies, so you can associate a resource in your cloud data service with a [root key](/docs/services/key-protect?topic=key-protect-envelope-encryption#key-types) that you manage in {{site.data.keyword.keymanagementserviceshort}}.

Be sure to provision both services in the same region before you create an authorization. To learn more about service authorizations, see [Granting access between services](/docs/iam?topic=iam-serviceauth){: external}.
{: note}

When you're ready to integrate a service, use the following steps to create an authorization:

1. From the menu bar, click **Manage** &gt; **Access (IAM)**, and select **Authorizations**. 
2. Click **Create**.
3. Select a source and target service for the authorization.
 
  For **Source service**, select the cloud data service that you want to integrate with {{site.data.keyword.keymanagementserviceshort}}. For **Target service**, select **{{site.data.keyword.keymanagementservicelong_notm}}**.

5. Enable the **Reader** role.

    With _Reader_ permissions, your source service can browse the root keys that are provisioned in the specified instance of {{site.data.keyword.keymanagementserviceshort}}.

6. Click **Authorize**.

## What's next
{: #integration-next-steps}

Add advanced encryption to your cloud resources by creating a root key in {{site.data.keyword.keymanagementserviceshort}}. Add a new resource to a supported cloud data service, and then select the root key that you want to use for advanced encryption.

- To find out more about creating root keys with the {{site.data.keyword.keymanagementserviceshort}} service, see [Creating root keys](/docs/services/key-protect?topic=key-protect-create-root-keys).
- To find out more about bringing your own root keys to the {{site.data.keyword.keymanagementserviceshort}} service, see [Importing root keys](/docs/services/key-protect?topic=key-protect-import-root-keys).


