---
title: '[!DNL Adobe Marketo Qualifier] 发行说明'
description: 了解[!DNL Adobe Marketo Qualifier]中的新增功能。
feature: Agentic AI, Sales Insights, Account Journeys
role: User
product_v2:
  - id: d98caee2-fd67-486e-9513-36435358ebff
    internal-label: Marketo Qualifier
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 633ca975d4fe58bdcc84caf633049ae1190b0f56
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 10%
---
# [!DNL Adobe Marketo Qualifier] 发行说明

## 即将发布的版本

* 用纯语言描述您要联系的人员，并将其转化为CRM潜在客户和联系人过滤器，在“出站工作流”定位中使用每个“潜在客户”和“联系人”过滤器，并在保存之前预览匹配的潜在客户。 [了解详情](outbound-workflows.md#step-2-configure-targeting-filters)。
* 在文本字段（如职务和电子邮件）中同时按多个值过滤潜在客户，每个过滤器最多可包含五个值。 [了解详情](prospects.md#filter-and-find-prospects)。
* 直接从出站工作流审核、编辑和发送对潜在客户回复的AI草稿回复，或拒绝不适合的草稿。 [了解详情](outbound-workflows.md#review-and-send-ai-draft-replies)。
* 在Salesforce或Microsoft Dynamics 365中安装[!DNL Adobe Marketo Qualifier]，并从Salesforce列表视图和记录页面将潜在客户添加到出站工作流或Marketo营销活动。 [了解详情](crm-plugin-setup.md)。
* 智能受众(Beta)可快速入门：引导式演练、创建受众时的快速添加选项，以及记录计数的更清晰的列表、保留在视图中的帐户列和颜色编码分数。 [了解详情](smart-audience.md)。
* 利用Smart audience (Beta)查找并优先处理合适的客户和潜在客户。 以纯语言描述您需要的帐户，添加CRM数据和增长信号，审查已评分的潜在客户，并将它们添加到出站工作流。 [了解详情](smart-audience.md)。
* 按帐户字段、“联系人”和“机会”字段筛选联系人，以查找合适的联系人并更准确地定位出站工作流。 [了解详情](prospects.md#filter-and-find-prospects)。
* 联系人会显示其关联的帐户和所有者姓名，而潜在客户的页面现在会显示90天的营销活动，最多为30天。 [了解详情](prospects.md#review-prospect-details)。

## 10-08-2026

此版本包括：

* 重用出站工作流，或更改正在运行的工作流的接触点，复制它并编辑副本。 复制最初为无潜在客户的专用草稿，而原始工作流未更改。 [了解详情](outbound-workflows.md#duplicate-an-outbound-workflow)。
* 以紧凑布局配置出站工作流，并在目标、定位、接触点和设置之间导航。 [了解详情](outbound-workflows.md#create-an-outbound-workflow)。
* 自动识别电子邮件回复中的清除选择退出请求。 潜在客户将标记为已选择退出，并且不会发送进一步的接触点。 [了解详情](outbound-workflows.md#opt-out-requests-in-replies)。
* 准备会议时，只需一份简短的介绍，其中结合了Web研究和特定于产品的客户案例研究，并提供了按相关性和来源划分的讨论要点。 [了解详情](prospects.md#generate-meeting-prep)。
* 生成的电子邮件将根据质量准则进行检查，并在需要时进行重写，然后再进行审核。 在发送每封电子邮件之前，您仍会审核、编辑和批准该电子邮件。 [了解详情](outbound-workflows.md#review-and-refine-generated-emails)。

## 09-22-2026

此版本包括：

* 在嵌入的CRM插件中查看[!DNL Marketo Sales Insights]和代理数据，并将潜在客户添加到[!DNL Marketo Qualifier]。 [了解详情](admin-settings.md#crm-mcp-and-the-embedded-plugin)。
* 使用“最佳匹配”、“我的观察列表”、“Web活动”、“电子邮件往来”和“网络研讨会”活动来排定CRM商机的优先级。 [了解详情](admin-settings.md#prioritize-leads-in-the-crm-plugin)。
* 当潜在客户的实时[!DNL Marketo]活动与工作流条件匹配时，自动在出站工作流中注册潜在客户。 [了解详情](home.md#automatically-enroll-prospects-from-marketing-highlights)。
* 审查潜在客户上下文并导出潜在客户列表，并在[!DNL Marketo Optimizer]个Prime和Ultimate实例上查看AI人员摘要。 [了解详情](prospects.md#review-prospect-context-and-export-the-list)。
* 在出站工作流中，审阅并批准任务队列中生成的目标客户电子邮件，并通过代理建议进行回复。 [了解详情](tasks.md)。

## 09-08-2026

此版本包括：

* 在“用户档案”设置中设置一次您自己的电子邮件起草样式，并且每个生成的电子邮件都遵循该样式。 [了解详情](profile-settings.md#email-drafting-context)。
* 在新的“会议研究”选项卡中，从潜在客户页面生成基于目标的会议准备或自定义会议准备。 [了解详情](prospects.md#generate-meeting-prep)。
* 管理员可以将“出站工作流”分配给队友，并将工作流设置重置为默认值。 [了解详情](outbound-workflows.md#create-an-outbound-workflow)。
* 从CSV导入潜在客户时映射自定义字段，并在生成的电子邮件中使用这些值。 [了解详情](prospects.md#build-your-prospect-list)。
* 生成的电子邮件会使用您导入的任何其他潜在客户数据，并且可以使用潜在客户的语言以本机方式编写。 [了解详情](outbound-workflows.md#step-5-add-prospects-and-start-email-generation)。
* 默认情况下，“出站性能”显示打开率和点击率，并且在组织级别切换原始计数和潜在客户总数。 [了解详情](performance.md)。
* 当目标客户在出站工作流中移动时，CRM同步规则会自动更新CRM状态。 [了解详情](admin-settings.md#configure-crm-sync-rules)。
* 在您的[!DNL Marketo Qualifier]、CRM、[!DNL Marketo]和[!DNL Marketo Optimizer]数据中提出AI Chat问题。 [了解详情](ai-assistant.md#ask-ai-chat-across-your-connected-data)。

## 08-17-2026

[!DNL Marketo Qualifier]现已作为独立应用程序提供。 它支持[!DNL Marketo Engage]和[!DNL Marketo Optimizer]。

此版本包括：

* 通过AI生成的活动摘要和基于信号的评分，确定潜在客户和客户的优先级。 [了解有关潜在客户或[帐户的更多信息](prospects.md#review-prospect-details)](accounts.md#account-insights)。
* 目标驱动的出站工作流，具有AI建议的节奏和草拟的电子邮件。 [了解详情](outbound-workflows.md)。
* 电话、LinkedIn InMails和电子邮件审阅的统一任务队列。 [了解详情](tasks.md)。
* 通过日历集成自动预订会议。 [了解详情](outbound-workflows.md#meeting-booking)。
* 一个知识中心，可在您自己的行动手册材料中将AI外联置于基础之上。 [了解详情](admin-settings.md#knowledge-center)。
* AI Chat可根据CRM、参与和知识中心数据回答自然语言问题。 [了解详情](ai-assistant.md)。
* 电子邮件和会议预订性能报表。 [了解详情](performance.md)。
* 用于在CRM或Outlook中访问的浏览器和电子邮件插件。 [了解详情](admin-settings.md#crm-mcp-and-the-embedded-plugin)。
* 支持Salesforce和Microsoft Dynamics 365集成。 [了解详情](integrations.md)。
