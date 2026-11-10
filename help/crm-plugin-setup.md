---
title: CRM连接
description: 了解如何在Salesforce或Microsoft Dynamics 365中安装Marketo Qualifier，以及如何为出站工作流和Marketo营销活动配置Salesforce操作。
feature: Agentic AI, Sales Insights, Account Journeys
role: Admin
product_v2:
  - id: d98caee2-fd67-486e-9513-36435358ebff
    internal-label: Marketo Qualifier
feature_v2:
  - id: da701e37-3227-4187-b68a-914277252a79
    internal-label: Integrations
  - id: f8f8b877-7295-5853-989f-e21f73bc94c4
    internal-label: Administration
subfeature_v2:
  - id: d2fe5f36-5653-5902-937c-9d3026104284
    internal-label: CRM integrations
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 633ca975d4fe58bdcc84caf633049ae1190b0f56
workflow-type: tm+mt
source-wordcount: '946'
ht-degree: 0%
---

# CRM连接

安装[!DNL Adobe Marketo Qualifier] CRM插件，以便代表无需离开Salesforce或Microsoft Dynamics 365，即可使用潜在客户、联系人和帐户记录页面上的[!DNL Marketo Sales Insights]和人工智能生成的见解。 该插件还提供了一个主页视图，用于[在您的CRM中优先考虑潜在客户](admin-settings.md#prioritize-leads-in-the-crm-plugin)。

在Salesforce中，代表还可以通过潜在客户和联系人列表视图以及单个记录页面，将潜在客户添加到叫客工作流或Marketo营销活动。

## 开始之前

确保安装和使用插件的用户具有所需的访问权限：

* **Salesforce管理员**：安装包和编辑页面布局的权限。
* **Microsoft Dynamics 365管理员**：在Power Apps中将解决方案导入目标环境的权限。
* **代表**：访问Marketo Qualifier和相关CRM记录。

安装插件与[将您的CRM连接到Marketo Qualifier](getting-started.md#connect-your-crm)是分开的。

## 在Salesforce中安装

安装资源包，然后将其组件添加到代表使用的记录页面。

1. 打开[Salesforce安装页面](https://experience.adobe.com/solutions/OneAdobe-sales-workflow-optimizer-sales-insight-ui/install/sales-insight?crm=salesforce)，并以管理员身份登录到Salesforce。
1. 在包安装页面上，选择&#x200B;**[!UICONTROL Install for All Users]**，然后选择&#x200B;**[!UICONTROL Install]**。

   您仍然可以通过Salesforce权限控制单个用户的访问。

1. 提示审批第三方访问时，选中审批复选框，然后选择&#x200B;**[!UICONTROL 继续]**。
1. 安装完成后，选择&#x200B;**[!UICONTROL 完成]**。

   安装需要几分钟的时间。 确认该包出现在&#x200B;**[!UICONTROL 已安装的包]**&#x200B;页面上。

1. 在Lightning App Builder中，编辑Lead、Contact和Account记录页面并添加Marketo Qualifier组件。

### 向列表视图添加操作

针对潜在客户和联系人列表视图，分别配置&#x200B;**[!UICONTROL 添加到出站工作流]**&#x200B;和&#x200B;**[!UICONTROL 添加到Marketo营销活动]**。 使用资源包中包含的按钮可避免重复出现。

1. 转到&#x200B;**[!UICONTROL 设置]** > **[!UICONTROL 对象管理器]**&#x200B;并选择&#x200B;**[!UICONTROL 潜在客户]**&#x200B;或&#x200B;**[!UICONTROL 联系人]**。
1. 打开&#x200B;**[!UICONTROL 按钮、链接和操作]**，找到列表按钮&#x200B;**[!UICONTROL AMQ Add to Outbound Workflow]**&#x200B;和&#x200B;**[!UICONTROL AMQ Add to Marketo Campaign]**。
1. 打开对象的&#x200B;**[!UICONTROL 列表视图按钮布局]**&#x200B;并选择&#x200B;**[!UICONTROL 编辑]**。

   根据您的Salesforce设置，列表视图布局可能位于&#x200B;**[!UICONTROL 搜索布局]** > **[!UICONTROL 列表视图]**&#x200B;下。

1. 将两个列表按钮移动到&#x200B;**[!UICONTROL 选定按钮]**&#x200B;并保存。
1. 对其他对象重复此操作。

代表在列表视图中选择一个或多个记录，然后选择操作。

### 添加操作以记录页面

记录页操作必须与列表视图按钮分开配置。 将这两个操作添加到每个使用中的Lead和Contact页面布局。

1. 转到&#x200B;**[!UICONTROL 设置]** > **[!UICONTROL 对象管理器]**&#x200B;并选择&#x200B;**[!UICONTROL 潜在客户]**&#x200B;或&#x200B;**[!UICONTROL 联系人]**。
1. 打开&#x200B;**[!UICONTROL 按钮、链接和操作]**，找到详细信息按钮&#x200B;**[!UICONTROL AMQ Add to Outbound Workflow]**&#x200B;和&#x200B;**[!UICONTROL AMQ Add to Marketo Campaign]**。
1. 打开&#x200B;**[!UICONTROL 页面布局]**&#x200B;并编辑分配给代表的布局。
1. 将两个详细信息按钮添加到&#x200B;**[!UICONTROL Salesforce Mobile和Lightning Experience Actions]**&#x200B;并保存。
1. 对每个适用的布局和其他对象重复执行上述操作。

这些操作将显示在记录的操作栏或其菜单中，并应用于正在查看的记录。

>[!NOTE]
>
>这些操作在桌面Salesforce Lightning Experience中起作用，而不在Salesforce移动设备应用程序中。 名为&#x200B;**[!UICONTROL Salesforce Mobile和Lightning Experience Actions]**&#x200B;的布局部分也用于桌面操作。

### 替换缺少的按钮

如果缺少打包按钮，请在对象的&#x200B;**[!UICONTROL 按钮、链接和操作]**&#x200B;下创建替换。

1. 选择&#x200B;**[!UICONTROL 新建按钮或链接]**。
1. 输入操作的标签，如`Add to Outbound Workflow`或`Add to Marketo Campaign`。
1. 为列表视图选择&#x200B;**[!UICONTROL 列表按钮]**&#x200B;或为记录页选择&#x200B;**[!UICONTROL 详细信息页按钮]**。
1. 将&#x200B;**[!UICONTROL Content Source]**&#x200B;设置为&#x200B;**[!UICONTROL Visualforce Page]**，然后选择与操作、对象和版面匹配的包的操作页面。

   Lead list 、 Lead detail 、 Contact list和Contact detail位置使用不同的页面。 确认所选页面与您配置的版面相匹配。

1. 对于列表按钮，请选择&#x200B;**[!UICONTROL 需要行选择]**。
1. 保存该按钮，并将其添加到适当的列表视图按钮布局或记录页操作中，如上所述。

### 检查Salesforce操作

保存布局后，确认这两个操作都显示在Lead和Contact列表视图和记录页面上。 用选定的记录测试每个列表操作，并从单个记录测试每个记录页操作。

如果某个操作不可用或未打开，请使用以下检查：

| 问题 | 检查内容 |
| --- | --- |
| 列表视图中缺少按钮 | 确认列表按钮位于正确对象的&#x200B;**[!UICONTROL 列表视图按钮布局]**&#x200B;上的&#x200B;**[!UICONTROL 选定按钮]**&#x200B;中，并保存布局。 |
| 记录页面中缺少按钮 | 确认详细信息按钮位于分配给用户的布局上的&#x200B;**[!UICONTROL Salesforce Mobile和Lightning Experience Actions]**&#x200B;中。 如果贵组织使用动态操作，还应检查记录页面的操作可见性。 |
| 创建按钮时，“预期页面”选项不可用 | 对于列表视图，检查显示类型是否为&#x200B;**[!UICONTROL 列表按钮]**&#x200B;或对于记录页面，检查显示类型是否为&#x200B;**[!UICONTROL 详细信息页面按钮]**。 |
| 操作未打开或显示访问错误 | 确认用户有权访问Marketo Qualifier和选定的记录。 |

## 在Microsoft Dynamics 365中安装

将插件包导入代表的工作环境中。

1. 打开[Microsoft Dynamics 365安装页面](https://experience.adobe.com/solutions/OneAdobe-sales-workflow-optimizer-sales-insight-ui/install/sales-insight?crm=dynamics)并下载包ZIP文件。
1. 以管理员身份登录到[Power Apps](https://make.powerapps.com/)并选择目标环境。
1. 打开&#x200B;**[!UICONTROL 解决方案]**&#x200B;并选择&#x200B;**[!UICONTROL 导入解决方案]**。
1. 选择&#x200B;**[!UICONTROL 浏览]**，选择下载的ZIP文件，然后选择&#x200B;**[!UICONTROL 下一步]**。
1. 查看包详细信息并选择&#x200B;**[!UICONTROL 下一步]**。
1. 保留预填充的环境变量值并选择&#x200B;**[!UICONTROL 导入]**。
1. 等待页面顶部的确认消息，告知解决方案已成功导入。

导入需要几分钟的时间。

>[!MORELIKETHIS]
>
>* [在CRM插件中优先处理潜在客户](admin-settings.md#prioritize-leads-in-the-crm-plugin)
>* [集成](integrations.md)
>* [开始使用](getting-started.md)
