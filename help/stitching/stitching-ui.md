---
title: 拼合
description: 了解如何创建和管理拼合数据集
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
hidefromtoc: true
exl-id: 8820a093-e573-45f9-bcd2-0933e21c231b
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 1%

---

# 创建和管理拼合数据集

{{select-package}}

拼接允许管理员对Customer Journey Analytics中可用的数据集进行身份拼接。 拼合数据集可提高用户档案表示的准确性，从而最终获得更好的分析和报表。

拼接过程允许您在数据集中定义现有的&#x200B;**永久ID**。 然后，将指定重播时段（每天、每周）的永久标识符与该数据集可用的最准确的&#x200B;**临时ID**（人员或经过身份验证的标识符）拼合。 临时标识符的示例包括电子邮件、电话号码、CRM ID或图中存储的其他标识。 有关拼接的更多信息，请参阅[概述](overview.md)。

## 创建

要启动拼接，您需要创建一个或多个拼合的数据集。 要创建拼合的数据集，请执行以下操作：

1. 从顶部栏的&#x200B;**[!UICONTROL **&#x200B;数据管理&#x200B;**]**&#x200B;中选择&#x200B;**[!UICONTROL **&#x200B;拼接&#x200B;**]**。

2. 在[!UICONTROL 拼接数据集]屏幕中，选择&#x200B;**[!UICONTROL **&#x200B;创建拼接数据集&#x200B;**]**。

   系统将提示您显示一个对话框，解释您的责任。

3. 如果您接受这些责任，请选择&#x200B;**[!UICONTROL **&#x200B;继续&#x200B;**]**。

   >[!NOTE]
   >
   >    如果选择&#x200B;**[!UICONTROL **&#x200B;取消&#x200B;**]**，您将无法创建拼合的数据集。

4. 在[!UICONTROL 拼接数据集>无标题拼接数据集]屏幕中：

   1. 定义&#x200B;**[!UICONTROL **&#x200B;数据集名称&#x200B;**]**&#x200B;和（可选）**[!UICONTROL **&#x200B;描述&#x200B;**]**，

   2. 从存储事件数据集的&#x200B;**[!UICONTROL **&#x200B;沙盒&#x200B;**]**&#x200B;列表中选择沙盒。

      ![初始创建屏幕](./assets/create-initial.png)

   3. 选择&#x200B;**[!UICONTROL **&#x200B;选择源数据集&#x200B;**]**&#x200B;按钮。

      在[!UICONTROL 选择一个要拼合的数据集]弹出窗口中：

      ![选择一个数据集](./assets/select-one-dataset.png)

      - 选择一个数据集，然后选择&#x200B;**[!UICONTROL **&#x200B;选择&#x200B;**]**&#x200B;以继续。

   4. 从&#x200B;**[!UICONTROL **&#x200B;永久ID **]**&#x200B;列表中选择一个永久标识符。

   5. 从&#x200B;**[!UICONTROL **&#x200B;临时ID **]**&#x200B;列表中选择临时标识符。

      您会注意到，预览面板似乎在计算过去七天的饱和率（指定标识符在事件数内每个值出现的次数）。 完成计算后，面板会用颜色显示是否满足拼接的最小条件（绿色）或未满足（红色）。

      ![创建具有统计速率的拼接数据集](./assets/create-before-experimenting.png)

      最低条件为：

      - 持续性标识符饱和度：比率>= 95%

      - 瞬时标识符饱和度：速率>= 5%

        如果满足最小条件，则可以试验样本值。

      - 选择&#x200B;**[!UICONTROL **&#x200B;创建演示拼接ID **]**。

        在[!UICONTROL 使用示例值的试验]对话框中，将显示一个表，该表具有[!UICONTROL 时间戳]、[!UICONTROL 持久ID]、[!UICONTROL 临时ID]、[!UICONTROL 拼合ID（实时）]、[!UICONTROL 拼合ID（1天重放）]和[!UICONTROL 拼合ID（7天重放）]的示例值。

            ！[使用示例值试验](./assets/experiment-sample-values.png)
            
            1。  输入**[!UICONTROL **持久ID**]**的值。
            
            2。  选择**[!UICONTROL **刷新拼接ID**]**以查看拼合过程对数据集中的数据的影响。
            
            3。  完成样本值的实验后，选择**[!UICONTROL **Close**]**。
        

        返回[!UICONTROL 拼接的数据集> _数据集名称_]&#x200B;屏幕：

   6. 从&#x200B;**[!UICONTROL **&#x200B;重播窗口&#x200B;**]**&#x200B;列表中选择重述历史数据的频率和时段的选项。

      您可以选择默认值&#x200B;**[!UICONTROL ** Previous day， daily **]**&#x200B;或&#x200B;**[!UICONTROL ** Previous 7 days， weekly **]**。

   7. 从&#x200B;**[!UICONTROL **&#x200B;平均每日事件数&#x200B;**]**&#x200B;列表中选择一个值。

   8. 输入值（介于`0`和`12`之间），以&#x200B;**[!UICONTROL **&#x200B;回填月数&#x200B;**]**&#x200B;为单位。

   9. 选择&#x200B;**[!UICONTROL **&#x200B;保存&#x200B;**]**&#x200B;以保存拼合的数据集并启动拼合。

## 查看状态

您可以在[!UICONTROL 拼接的数据集]列表中查看拼接状态。

- 从顶部栏的&#x200B;**[!UICONTROL **&#x200B;数据管理&#x200B;**]**&#x200B;中选择&#x200B;**[!UICONTROL **&#x200B;拼接&#x200B;**]**。

  您看到拼接数据集的列表，每个数据集都使用[!UICONTROL 沙盒]、[!UICONTROL Source数据集]、[!UICONTROL 状态]、[!UICONTROL 回填状态]、[!UICONTROL 所有者]以及创建日期[!UICONTROL 来标识]。

  ![拼接数据集的概述](./assets/overview-stitched-datasetts.png)

  [!UICONTROL 状态]的可能值包括：

  | 值 | 说明 |
  |-----|-----|
  | **[!UICONTROL **&#x200B;已排队&#x200B;**]** | 已收到请求，很快就会处理该请求。 |
  | **[!UICONTROL **&#x200B;正在创建&#x200B;**]** | 正在创建资源和新拼合的数据集。 |
  | **[!UICONTROL **&#x200B;拼接正在进行中&#x200B;**]** | 资源和拼合的数据集已存在，并且正在进行拼合 |
  | **[!UICONTROL **&#x200B;错误&#x200B;**]** | 拼合时出现问题。 可能某个架构在源数据集与拼合的数据集之间发生更改，每日流量过大，或者…… （_**此处需要更多信息……**_） |

  >[!INFO]
  >
  >    每当状态更改时，都会发送通知，消息为&#x200B;**[!UICONTROL **&#x200B;数据集&#x200B;_的Stitched数据集_&#x200B;名称已更改为状态&#x200B;_的&#x200B;_**]**名称。


  [!UICONTROL 回填状态]可以具有以下值：0%、25%、50%、75%或100%。

  您可以选择信息图标以显示一个弹出窗口，其中包含有关所选拼接数据集的更多详细信息。


## 删除

>[!NOTE]
>
>您只能删除状态为[!UICONTROL 正在拼合]、[!UICONTROL 错误]或[!UICONTROL 已排队]的数据集。


要删除单个拼接的数据集，请执行以下操作：

- 为拼接的数据集选择&#x200B;**[!UICONTROL **...**]**，然后从菜单中选择&#x200B;**[!UICONTROL **&#x200B;删除&#x200B;**]**。

  ![删除拼合的数据集](./assets/delete-stitched-dataset.png)

要删除多个拼接数据，请执行以下操作：

- 使用每个列出数据集开头的复选框，选择多个拼合的数据集。

- 从其中一个选定的拼接数据集中选择&#x200B;**[!UICONTROL **...**]**，然后从菜单中选择&#x200B;**[!UICONTROL **&#x200B;删除&#x200B;**]**。
