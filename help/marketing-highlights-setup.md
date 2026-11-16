---
title: 设置营销亮点
description: 了解如何通过Smart Campaign流程步骤将潜在客户从Marketo Engage发送到Marketo Qualifier，并获取营销亮点建议以供审查。
feature: Agentic AI, Sales Insights, Account Journeys
role: Admin
product_v2:
  - id: d98caee2-fd67-486e-9513-36435358ebff
    internal-label: Marketo Qualifier
feature_v2:
  - id: da701e37-3227-4187-b68a-914277252a79
    internal-label: Integrations
subfeature_v2:
  - id: 7b0925d9-0dc0-5c75-a54d-2bcc31c6ebe4
    internal-label: Marketing highlights
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
    internal-label: Data integration
source-git-commit: adcfe279f38ca319589612820351c48af750bad9
workflow-type: tm+mt
source-wordcount: '1011'
ht-degree: 1%
---

# 设置营销亮点

通过将&#x200B;**[!UICONTROL 发送到Marketo Qualifier]**&#x200B;流程步骤添加到Smart Campaign，将潜在客户从[!DNL Adobe Marketo Engage]发送到[!DNL Adobe Marketo Qualifier]。 代表可以在&#x200B;**[!UICONTROL 潜在客户]** > **[!UICONTROL 营销亮点]**&#x200B;上查看发送他们的潜在客户和活动。

流程步骤适用于两种类型的Smart Campaign：

* **触发营销活动**&#x200B;发送参与情况，例如电子邮件打开和点击、链接点击、表单填写和网页访问。
* **批次营销活动**&#x200B;每次运行营销活动时发送符合条件的潜在客户。

当商机与出站工作流的定位条件匹配时，Marketo Qualifier建议在连接的CRM中将商机推荐给其所有者。 在注册和外联之前，拥有该产品的代表负责审阅和批准商机。 潜在客户不会自动注册。

营销亮点适用于所有生产地区：北美、EMEA和澳大利亚。

## 开始之前 {#before-you-begin}

在添加流程步骤之前，请确认以下先决条件：

* Marketo管理员已在&#x200B;**[!UICONTROL 管理员]**&#x200B;中为您的Marketo Engage实例启用&#x200B;**[!UICONTROL 发送到Marketo Qualifier]**。
* Marketo Qualifier已[连接到Salesforce或Microsoft Dynamics 365](getting-started.md#connect-your-crm)，因此每个潜在客户都可以与其CRM所有者匹配。

>[!IMPORTANT]
>
>**[!UICONTROL 发送到Marketo Qualifier]**&#x200B;流程步骤不需要webhook、端点URL或API凭据。 您不需要访问Adobe Developer Console即可使用它。 如果流程步骤不可用，请与Marketo管理员联系。

## 通过Smart Campaign发送潜在客户 {#send-leads-with-a-smart-campaign}

使用现有的Smart Campaign，或为要发送的潜在客户和活动创建一个。

1. 在Marketo Engage中，打开Smart Campaign，或选择&#x200B;**[!UICONTROL 营销活动]** > **[!UICONTROL 新建]** > **[!UICONTROL Smart Campaign]**&#x200B;以创建一个。
1. 在&#x200B;**[!UICONTROL 智能列表]**&#x200B;选项卡上，定义哪些潜在客户符合条件。

   * 对于触发器促销活动，为要发送的活动添加触发器，如&#x200B;**[!UICONTROL 访问网页]**、**[!UICONTROL 点击网页上的链接]**&#x200B;或电子邮件中的&#x200B;**[!UICONTROL 点击链接]**。
   * 对于批量营销活动，请为要发送的潜在客户添加过滤器。

1. 在&#x200B;**[!UICONTROL 流]**&#x200B;选项卡上，添加&#x200B;**[!UICONTROL 发送到Marketo Qualifier]**&#x200B;流步骤。
1. 激活触发器营销活动，或运行或计划批处理营销活动。
1. 在Marketo Qualifier中，打开&#x200B;**[!UICONTROL 潜在客户]** > **[!UICONTROL 营销亮点]**&#x200B;以查看潜在客户及其活动。

   该活动显示商机如何到达，例如&#x200B;**[!UICONTROL 从批次营销活动]**&#x200B;添加。

只向其CRM所有者建议符合出站工作流定位标准的潜在客户。 若要查看建议，请打开&#x200B;**[!UICONTROL 任务]** > **[!UICONTROL 代理建议]**。 查看[从营销亮点获取建议](outbound-workflows.md#automatically-enroll-prospects-from-marketing-highlights)和[代理建议](tasks.md#agent-suggestions)。

## 现有webhook设置 {#existing-webhook-setups}

以下说明描述了较早的webhook设置。 在&#x200B;**[!UICONTROL 发送到Marketo Qualifier]**&#x200B;流程步骤中不需要这些端口。 如果贵组织已使用webhook，请在更改该设置之前与Marketo管理员和Adobe联系人联系。

+++Webhook设置说明

这些说明需要访问Adobe Developer Console和Marketo Engage中的&#x200B;**[!UICONTROL 管理员]**。

### A部分：创建API凭据 {#part-a-create-api-credentials}

这些凭据允许[!DNL Marketo]安全地向Marketo Qualifier进行身份验证。

要创建凭据，请执行以下操作：

1. 转到[Adobe Developer Console](https://developer.adobe.com/console/)并使用您的Adobe ID登录。
1. 选择&#x200B;**[!UICONTROL 创建新项目]**，或打开现有项目。
1. 若要重命名项目，请选择&#x200B;**[!UICONTROL 编辑项目]**，输入可识别的名称，如`Marketo Qualifier Marketing Highlights`，然后选择&#x200B;**[!UICONTROL 保存]**。
1. 选择&#x200B;**[!UICONTROL 添加API]**，选择&#x200B;**[!UICONTROL Experience Platform API]**，然后选择&#x200B;**[!UICONTROL 下一步]**。
1. 选择&#x200B;**[!UICONTROL OAuth服务器到服务器]**&#x200B;作为身份验证类型，然后选择&#x200B;**[!UICONTROL 下一步]**。

   **[!UICONTROL OAuth服务器到服务器]**&#x200B;允许[!DNL Marketo]直接从服务器调用Marketo Qualifier API，无需人员登录。

1. 输入不超过45个字符的凭据名称，如`Marketo Qualifier Marketing Highlights Creds`。
1. 要关联产品配置文件，请选择它，然后选择&#x200B;**[!UICONTROL 保存配置的API]**。
1. 在&#x200B;**[!UICONTROL 连接的凭据]**&#x200B;下，打开&#x200B;**[!UICONTROL OAuth服务器到服务器]**&#x200B;凭据。 选择&#x200B;**[!UICONTROL 检索客户端密钥]**，然后复制&#x200B;**[!UICONTROL 客户端ID]**&#x200B;和&#x200B;**[!UICONTROL 客户端密钥]**。 在[部分C](#part-c-configure-the-marketo-webhook)中使用这些值。

>[!WARNING]
>
>将客户端密钥设为私有。 请将其视为密码，不要通过电子邮件发送。 使用您组织批准的安全渠道与配置webhook的人员共享该渠道。

### B部分：收集您的端点和标识符 {#part-b-gather-your-endpoint-and-identifiers}

[部分C](#part-c-configure-the-marketo-webhook)需要三个值：

* **端点URL** — 您所在地区的Marketo Qualifier webhook地址。
* **imsOrg ID** — 贵组织在Adobe Identity Management System (IMS)中的标识符，格式为`{ORG_ID}@AdobeOrg`。
* **沙盒名称** — 您的AEP沙盒的名称与在Marketo Qualifier URL中显示的名称（`sname`值）完全相同，而不是在UI中显示的显示名称。 使用小写URL值，例如`prod`，而不是`Prod`。

| 区域 | Webhook端点URL |
| --- | --- |
| 北美洲 | `https://5r6xakp9k3.execute-api.us-east-1.amazonaws.com/prod/external/marketo/signals` |
| EMEA | `https://pc72i8q1k3.execute-api.eu-west-1.amazonaws.com/prod/external/marketo/signals` |
| APAC /澳大利亚 | `https://5cxxxyqlai.execute-api.ap-southeast-2.amazonaws.com/prod/external/marketo/signals` |

{style="table-layout:auto"}

如果您不确定自己的地区、imsOrg ID或沙盒名称，您的Adobe联系人可以确认它们。

### C部分：配置Marketo webhook {#part-c-configure-the-marketo-webhook}

要创建webhook，请执行以下操作：

1. 在[!DNL Marketo]中，选择&#x200B;**[!UICONTROL 管理员]** > **[!UICONTROL Webhooks]**。
1. 选择&#x200B;**[!UICONTROL 新建Webhook]**。
1. 将&#x200B;**[!UICONTROL URL]**&#x200B;设置为[B](#part-b-gather-your-endpoint-and-identifiers)部分中的您区域的终结点URL。
1. 将&#x200B;**[!UICONTROL 请求类型]**&#x200B;设置为`POST`。
1. 将&#x200B;**[!UICONTROL 请求令牌编码]**&#x200B;设置为`JSON`。 必须提供此设置。
1. 将下面的有效负载模板粘贴到&#x200B;**[!UICONTROL 模板]**&#x200B;中。 使用[!DNL Marketo]的&#x200B;**[!UICONTROL 插入令牌]**&#x200B;匹配实例中的字段名称。

   >[!NOTE]
   >
   >使用JSON编码时，请勿将字符串令牌包裹在引号中。 [!DNL Marketo]自动添加它们。

   ```json
   {
     "leadId": {{lead.Id:default=0}},
     "email": {{lead.Email Address:default=}},
     "fullName": {{lead.Full Name:default=}},
     "company": {{company.Company Name:default=}},
     "title": {{lead.Job Title:default=}},
     "department": {{lead.Department:default=}},
     "country": {{lead.Country:default=}},
     "score": {{lead.Lead Score:default=0}},
     "rating": {{lead.Lead Rating:default=}},
     "leadStatus": {{lead.Lead Status:default=}},
     "leadSource": {{lead.Lead Source:default=}},
     "isCustomer": {{lead.Is Customer:default=false}},
     "industry": {{company.Industry:default=}},
     "annualRevenue": {{company.Annual Revenue:default=0}},
     "numEmployees": {{company.Num Employees:default=0}},
     "campaignId": {{campaign.id:default=0}},
     "campaignName": {{campaign.name:default=}},
     "programName": {{program.name:default=}},
     "occurredAt": {{system.dateTime:default=}},
     "munchkinId": {{system.munchkinId:default=}},
     "triggerName": {{trigger.Trigger Name:default=}},
     "crmId": {{lead.SFDC ID:default=}},
     "crmType": {{lead.SFDC Type:default=}},
     "crmOwnerEmail": {{lead.Lead Owner Email Address:default=}},
     "crmOwnerFirstName": {{lead.Lead Owner First Name:default=}},
     "crmOwnerLastName": {{lead.Lead Owner Last Name:default=}},
     "attributes": {
       "asset": {{trigger.Name:default=}},
       "link": {{trigger.Link:default=}},
       "subject": {{trigger.Subject:default=}},
       "webPage": {{trigger.Web Page:default=}},
       "category": {{trigger.Category:default=}},
       "details": {{trigger.Details:default=}},
       "sentBy": {{trigger.Sent By:default=}},
       "receivedBy": {{trigger.Received By:default=}},
       "referrer": {{trigger.Referrer:default=}},
       "searchEngine": {{trigger.Search Engine:default=}},
       "searchQuery": {{trigger.Search Query:default=}},
       "imDescription": {{lead.Last Interesting Moment Desc:default=}},
       "imType": {{lead.Last Interesting Moment Type:default=}},
       "imDate": {{lead.Last Interesting Moment Date:default=}},
       "imSource": {{lead.Last Interesting Moment Source:default=}},
       "chatAgentName": {{trigger.Agent Name:default=}},
       "chatAgentEmail": {{trigger.Agent Email:default=}},
       "chatConversationStatus": {{trigger.Conversation Status:default=}},
       "chatConversationSummary": {{trigger.Conversation Summary:default=}},
       "chatGoalName": {{trigger.Goal name:default=}},
       "chatMeetingStatus": {{trigger.meeting status:default=}},
       "chatScheduledFor": {{trigger.Scheduled For:default=}},
       "chatDocumentName": {{trigger.Document Name:default=}},
       "chatDocumentUrl": {{trigger.Document URL:default=}},
       "chatPageUrl": {{trigger.Page URL:default=}}
     }
   }
   ```

1. 选择&#x200B;**[!UICONTROL Webhook操作]** > **[!UICONTROL 设置自定义标头]**，然后使用[部分A](#part-a-create-api-credentials)和[部分B](#part-b-gather-your-endpoint-and-identifiers)中的值添加以下标头：

   | 标头 | 值 |
   | --- | --- |
   | `Content-Type` | `application/json` |
   | `x-client-id` | 您的客户端ID |
   | `x-client-secret` | 您的客户端密码 |
   | `x-gw-ims-org-id` | 您的imsOrg ID |
   | `x-sandbox-name` | 您的沙盒名称 |

   {style="table-layout:auto"}

1. 选择&#x200B;**[!UICONTROL 保存]**。

### D部分：将webhook添加到触发器Smart Campaign {#part-d-add-the-webhook-to-a-trigger-smart-campaign}

将&#x200B;**[!UICONTROL Call Webhook]**&#x200B;流程步骤添加到触发智能营销活动（现有或新步骤）。 智能列表会在该营销策划中触发，从而决定要将哪些活动发送到Marketo Qualifier。

要添加webhook，请执行以下操作：

1. 打开现有的触发器Smart Campaign，或创建一个新触发器（**[!UICONTROL 营销活动]** > **[!UICONTROL 新建]** > **[!UICONTROL Smart Campaign]**）。
1. 在&#x200B;**[!UICONTROL 智能列表]**&#x200B;选项卡上，为要发送的活动添加一个或多个触发器，例如&#x200B;**[!UICONTROL 单击电子邮件中的链接]**、**[!UICONTROL 填写表单]**&#x200B;或&#x200B;**[!UICONTROL 访问网页]**。
1. 在&#x200B;**[!UICONTROL 流]**&#x200B;选项卡上，添加&#x200B;**[!UICONTROL 调用Webhook]**&#x200B;步骤，并选择您在[C](#part-c-configure-the-marketo-webhook)部分中创建的webhook。
1. 激活Smart Campaign。

来自该Smart Campaign的活动现在流入Marketo Qualifier。 代表可以在&#x200B;**[!UICONTROL 潜在客户]** > **[!UICONTROL 营销亮点]**&#x200B;上查看和筛选此活动。

+++

>[!MORELIKETHIS]
>
>* [管理集成](integrations.md)
>* [潜在客户](prospects.md)
>* [开始使用](getting-started.md)
