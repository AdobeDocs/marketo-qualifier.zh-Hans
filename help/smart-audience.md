---
title: 智能受众(Beta)
description: 了解如何使用智能受众(Beta)构建帐户列表、添加CRM数据和增长信号、排定潜在客户的优先级并将它们添加到出站工作流。
feature: Agentic AI, Sales Insights, Account Journeys
role: User
badgeBeta: label="Beta 版" type="Informative"
source-git-commit: bf94a2d28913093923f446025405339e4e64919c
workflow-type: tm+mt
source-wordcount: '1125'
ht-degree: 0%
---

# 智能受众(Beta)

智能受众(Beta)可帮助您在[!DNL Adobe Marketo Qualifier]中查找下一个要工作的帐户和人员。 用纯语言描述您的受众，用CRM数据和增长信号优化帐户列表，查找相关商机，并将所选商机添加到出站工作流。

在列表视图中处理其网格、筛选器和按钮，或使用聊天来描述您想要的内容。 两者在同一列表中工作：其中一个列表中的更改显示在另一个列表中。 如果更改未立即显示，请选择&#x200B;**[!UICONTROL 刷新]**。

每个列表顶部的进度跟踪器显示三个阶段：**[!UICONTROL 构建智能受众列表]**、**[!UICONTROL 排定潜在客户优先级]**&#x200B;和&#x200B;**[!UICONTROL 添加到出站工作流]**。

## 开始之前

智能受众需要连接的Salesforce或Microsoft Dynamics 365 CRM。 它会实时读取CRM数据，而不会写入CRM。 有关连接说明，请参阅[开始使用](getting-started.md#connect-your-crm)。

您最多可以创建100个列表。 每个列表最多可包含500个帐户和2,000个潜在客户。 不会添加超过这些限制的帐户或潜在客户。 缩小标准或将受众拆分为多个列表，例如按地区或区段划分。

## 描述和预览帐户

首先，描述您要访问的帐户。 预览不会保存列表。

1. 打开&#x200B;**[!UICONTROL 智能受众]**&#x200B;并选择&#x200B;**[!UICONTROL 新建智能受众]**&#x200B;或&#x200B;**[!UICONTROL 创建列表]**。
1. 在聊天中，描述您想要的帐户。 例如，输入`Find healthcare accounts with revenue over $50M`。
1. 在预览中查看匹配帐户数和示例数。

您的请求可以包括以下标准：

| 标准 | 示例 |
| --- | --- |
| Firmographics | 行业、员工人数、年收入、帐户类型和评级 |
| 位置 | 地区、国家/地区、省/市/自治区/直辖市 |
| 所有权 | 您的帐户或分配给指定所有者的帐户 |
| 管道 | 无论是否具有开放商机的帐户，均须遵守[Salesforce限制](#current-scope-and-limits) |
| 帐户详细信息 | 名称、网站或域以及帐号 |

其他示例请求包括：

* `Accounts in the US with more than 1000 employees`
* `My accounts in Germany or France`
* `Accounts with no open opportunity`

如果部分请求无法应用于您的CRM数据，则聊天会标识跳过的条件。 预览仅反映应用的条件。 在保存之前查看这些省略。

## 保存或优化预览

当预览与您的目标受众匹配时，请保存该预览。

1. 要更改预览，请发送包含所需条件的新请求。 在确认之前，不会保存任何内容。
1. 当预览就绪时，要求聊天将其另存为列表并提供列表名称。
1. 查看&#x200B;**[!UICONTROL 帐户]**&#x200B;选项卡上保存的帐户。

可以从列表页面重命名列表。 要删除列表，请打开该列表并选择&#x200B;**[!UICONTROL 删除智能受众列表]**。

>[!CAUTION]
>
>删除列表会永久从智能受众中删除其帐户、潜在客户和列。 它不会删除CRM记录。

## 丰富和甄选客户

添加信息列，以帮助决定要使用的帐户。 请求一列或每个请求一个信号。

要添加CRM信息，请输入一个请求，如`Add a column showing which accounts have an open opportunity`。 有关Salesforce限制，请参阅[当前范围和限制](#current-scope-and-limits)。

若要添加增长信号，请在列表视图中选择&#x200B;**[!UICONTROL 扩充帐户]**&#x200B;或在聊天中询问。 可用的信号包括：

| 信号 | 它显示的内容 |
| --- | --- |
| 资金 | 最近的筹资和筹资活动 |
| 招聘 | 最近职位空缺和招聘需求 |
| 扩展信号 | 新办公室、新市场和扩展公告 |
| 技术变革 | 公司技术栈栈的添加和更改 |
| 裁员 | 通过聊天请求的裁员信息 |

例如，输入`Which of these accounts have raised funding recently?`或`Which of these accounts have had layoffs?`。

在大型列表中，添加信号可能需要几分钟的时间。 按照列表中显示的进度检查每一新列，然后保留或丢弃它。

要缩小帐户范围并排定其优先顺序，请执行以下操作：

1. 在&#x200B;**[!UICONTROL 帐户]**&#x200B;选项卡上，打开&#x200B;**[!UICONTROL 筛选器]**。
1. 按帐户、域、行业、所有者、最小或最大员工、最小或最大收入或自定义列进行筛选。 自定义列是您添加的CRM和信号列。 例如，筛选聘用列设置为`Yes`的帐户。
1. （可选）选择&#x200B;**[!UICONTROL 排定帐户优先级]**&#x200B;以按分数对帐户进行排名。
1. 删除您不希望使用的任何帐户。

筛选器与列表一起保存。 系统只会为过滤的帐户查找潜在客户，因此请在优先处理潜在客户之前设置帐户过滤器。

## 查找潜在客户并确定其优先级

在已列入候选名单的帐户中查找相关人员。 在&#x200B;**[!UICONTROL 排定潜在客户优先级]**&#x200B;下，选择一个预设或描述您希望在聊天中的联系人。

| 预设 | 找到的联系人 |
| --- | --- |
| **[!UICONTROL 销售联系人]** | 销售总监和销售经理联系人 |
| **[!UICONTROL 营销联系人]** | 营销和营销经理联系人副总裁 |
| **[!UICONTROL 产品联系人]** | SVP产品经理联系人 |
| **[!UICONTROL 技术联系人]** | IT主管和工程部副总裁 |
| **[!UICONTROL 所有CRM联系人]** | 客户处每个可用联系人，最多2,000个潜在客户 |

对于聊天请求，输入`Find VP and Director level people at these accounts`、`Find C-level executives (CEO, CTO, CFO) at these accounts`或`Find managers at these accounts`。

查看&#x200B;**[!UICONTROL 潜在客户]**&#x200B;选项卡上的结果。 每个潜在客户都会显示其名称、职位、帐户、电子邮件、所有者和分数。 根据资历、电子邮件地址是否可用、最低或最高得分，或者商机是否在工作流中筛选。 **[!UICONTROL 推理]**&#x200B;列说明了每个潜在客户排名的原因。

### 分数的工作方式

分数介于0到100之间。 分数越高，表示适应度越高，参与准备程度越高。 相同的数据产生相同的分数。

得分结合使用：

* **适合**：帐户与您理想的客户配置文件（如行业和规模）的匹配程度。
* **购买和增长信号**：招聘、融资和领导力变化等信号。 最近的信号数量更多。
* **销售上下文**：上下文，例如具有扩展机会的现有客户。

在决定联系谁之前，先查看推理和可用数据。

## 将潜在客户添加到出站工作流

查看潜在客户后，将所需的潜在客户添加到现有出站工作流。

1. 在&#x200B;**[!UICONTROL 潜在客户]**&#x200B;选项卡上，筛选并选择所需的潜在客户。 例如，选择电子邮件地址最低分数为70的潜在客户。
1. 选择&#x200B;**[!UICONTROL 添加到出站工作流]**。
1. 选择工作流并进行确认。
1. 查看确认。 **[!UICONTROL Workflow]**&#x200B;列显示已添加潜在客户的&#x200B;**[!UICONTROL 已分配]**。

您还可以请求聊天按名称将潜在客户添加到工作流。 如果您不知道此名称，请咨询聊天以列出可用的工作流。 检查工作流名称和回复中的潜在客户数。

添加潜在客户不会取代电子邮件审阅和批准。 按照以下步骤操作：[审核生成的电子邮件](outbound-workflows.md#review-and-refine-generated-emails)和[在发送外展之前批准和注册潜在客户](outbound-workflows.md#approve-and-enroll-prospects)。

## 当前范围和限制

在Beta过程中，请牢记以下限制：

* 请求一列或每个请求一个信号。
* 智能受众使用标准CRM帐户字段。 不支持自定义CRM字段。
* 不支持按帐户拥有的产品进行筛选。
* 对于Salesforce，无法查找具有未完成销售机会的客户。 查找没有未结商机的帐户适用于这两个CRM。
* 对于Salesforce，有关为特定角色（如销售代表）招聘的请求不可用。

>[!MORELIKETHIS]
>
>* [帐户](accounts.md)
>* [潜在客户](prospects.md)
>* [出站工作流](outbound-workflows.md)
>* [AI聊天](ai-assistant.md)
