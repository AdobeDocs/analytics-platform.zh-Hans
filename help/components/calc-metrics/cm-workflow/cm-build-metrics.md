---
description: 计算量度生成器提供了一个画布，用于拖放Dimension、量度、过滤器和函数，以根据容器层次结构逻辑、规则和运算符创建自定义量度。 通过此集成式开发工具，您可以生成并保存简单的计算量度或复杂的高级计算量度。
title: 生成量度
source-git-commit: e50636784e406da84c986645ac380d68d9622bc6
workflow-type: tm+mt
source-wordcount: '901'
ht-degree: 86%

---

# 生成量度

计算量度生成器提供了一个画布，用于拖放Dimension、量度、过滤器和函数，以根据容器层次结构逻辑、规则和运算符创建自定义量度。 通过此集成式开发工具，您可以生成并保存简单的计算量度或复杂的高级计算量度。

可通过以下几种方式访问计算量度生成器：

* 在 Analysis Workspace 中，打开一个项目然后单击 **[!UICONTROL + 新建]** > **[!UICONTROL 创建量度]**。
* 在 [!DNL Analytics] 中，转到&#x200B;**[!UICONTROL 组件]** > **[!UICONTROL 计算量度]**。

* 单击&#x200B;**[!UICONTROL 计算量度管理器]**&#x200B;顶部的 [+ 添加](/help/components/calc-metrics/cm-workflow/cm-manager.md)，或者

* 转到 **[!UICONTROL Analytics]** > **[!UICONTROL 报表]**，打开任意报表并单击“量度”图标 ![](assets/metrics_icon.png) 以调出“量度”边栏，然后单击&#x200B;**[!UICONTROL 添加]**。

![](assets/cm_builder_ui.png)

## UI 组件 {#section_9382AEEBA4244DD6A9F6C1DD3F6D076B}

<table id="table_60A82936321047D1A335331BF83B0972"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> 字段 </th> 
   <th colname="col3" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> 标题 </span> </td> 
   <td colname="col3"> <p>必须为量度命名。如果没有命名，则无法保存量度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> 描述 </span> </td> 
   <td colname="col3"> <p>为量度提供用户友好的描述，以显示该量度的用途，并将其与类似的量度区分开。 </p> <p>该描述还会显示在报表内。最好不要在描述中放入公式，而是描述此量度应当用于哪些方面，不应当用于哪些方面。（公式会在您创建量度时生成，它位于“概要”标题的下面。因此，无需将公式添加到描述中。） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> 格式 </span> </td> 
   <td colname="col3"> <p>选项包括“小数”、“时间”、“百分比”和“货币”。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> 小数位 </span> </td> 
   <td colname="col3"> <p>显示将在报表中显示的小数位数。您可以指定的最大小数位数为 10。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> 将上升趋势显示为... </span> </td> 
   <td colname="col3"> <p>此量度极性设置显示 Analytics 应当将量度中的上升趋势视为有利（绿色）还是不利（红色）。最终，报表中的图表将在上升时显示为绿色或红色。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> 标记 </span> </td> 
   <td colname="col3"> <p>标记是一种用于组织量度的好方法。所有用户均可创建标记，并将一个或多个标记应用于量度。但是，您只能查看您所拥有的或与您共享的那些区段的标记。应创建哪种类型的标记？以下是对实用标记的一些建议： 
     <ul id="ul_9A6CE5F179424687A39F2D5C1A953258"> 
      <li id="li_A8815F2D8D284874AD701A7B103D82A3">基于<b>团队名称</b>的标记，如社交营销、移动营销。 </li> 
      <li id="li_A51A4515A541488E9D90296A955E9F4F"><b>项目</b>标记（分析标记），如登录页面分析。 </li> 
      <li id="li_B4605470A7094026AC168420B64BBCC3"><b>类别</b>标记：男士；地理位置。 </li> 
      <li id="li_B6EAB0F2A96C41209C4EC97B9E64390B"><b>工作流程标记：待批准；策划（为特定的业务部门）</b> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> 概要 </span> </td> 
   <td colname="col3"> <p>无论您何时对量度定义进行更改，<span class="uicontrol">概要</span>公式都会随之发生更新。当您将光标悬停在量度上方并单击 <img placement="inline"  src="assets/i_icon.png" id="image_BDA0EAF89C19440CB02AE248BA3F968E" /> 图标时，此公式还会显示在左侧的量度边栏中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> 定义 </span> </td> 
   <td colname="col3"> <p>在此处，您可以拖入量度/计算量度、区段和/或函数，以生成计算量度。 </p> <p> 
     <ul id="ul_B13401A266354DC594C6176025DB61CB"> 
      <li id="li_01776C32C7C5440AA1F847096CBED92B">如果拖入计算量度，它将自动展开其量度定义。 </li> 
      <li id="li_A483D352522E4572AB43042473053359">您可以通过容器嵌套定义。但是，与区段容器不同的是，这些容器的作用类似于数学表达式，它们决定着运算的顺序。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> 运算符 </span> </td> 
   <td colname="col3"> <p>默认运算符是除以 (<img placement="inline"  src="assets/divided_icon.png" id="image_320D7363DE024BDEB21E44606C8B367F" width="25px" />)，还有 +、- 和 x 运算符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> 预览 </span> </td> 
   <td colname="col3"> <p>提供对可能存在的任何错误的快速阅览。预览涵盖过去 90 天的范围。这种方式可用于初步评估您是否为量度选择了正确的组件。出现意外结果表示您需要重新检查量度定义。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> 添加 </span> </td> 
   <td colname="col3"> <p>对于所有类型的计算量度，您可以向定义中添加容器和静态数字。对于高级计算量度，您还可以添加区段和函数。 </p> <p> 
     <ul id="ul_607C1B303F334062BC620317667DE490"> 
      <li id="li_53462789B8AF4F1AA9B45565D37CF22B">容器的作用类似于数学表达式，它们决定着运算的顺序。因此，容器中的任何内容都将在下次运算前得到处理。 </li> 
      <li id="li_401A9E0D8B3B468990289DBF66A06F63">将区段拖到容器上，会将该容器中的所有内容分段。（仅限高级计算量度） </li> 
      <li id="li_F191B200D7A944F9ADC0573A9A82A6DA">您可以在一个容器中堆叠多个区段。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> 齿轮图标（<span class="uicontrol">量度类型</span>、<span class="uicontrol">归因</span>） </td> 
   <td colname="col3"> <p>选择量度旁边的齿轮图标允许您指定<a href="/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md"  >量度类型和归因模型</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> + 新建 </span> </td> 
   <td colname="col3"> <p>允许您创建新组件，例如新过滤器(可将您转到 <a href="/help/components/filters/create-filters.md"  > 过滤器生成器 </a>.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>搜索组件 </p> </td> 
   <td colname="col3"> <p>通过此搜索栏，您可以搜索维度、量度、区段（仅限高级计算量度）和函数（仅限高级计算量度）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>维度列表 </p> </td> 
   <td colname="col3"> <p>要在区段生成器中构建简单区段（例如“页面 = 主页”），您无需离开计算量度生成器，而是可以在“页面”中拖动并从计算量度生成器中直接选择“主页”。 </p> <p>这可以极大地简化用于创建分段计算量度的工作流程。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>量度列表 </p> </td> 
   <td colname="col3"> <p>量度有以下 3 种类别： </p> 
    <ul id="ul_7BF50F4964EF45858FBA1634FBFA45CF"> 
     <li id="li_90F2312927A6499CA1CE04F8FFC912CF">标准量度 ( <img placement="inline"  src="assets/met_icon.png" id="image_65A80F54D73443E78542FE0B31CC3F20" />) </li> 
     <li id="li_A3F59083E79B4AC780D6F8CEDFFD20C9">计算量度 ( <img placement="inline"  src="assets/calc_met_icon.png" id="image_C5674AB9B9EB4DA9A56782D15822C319" />) </li> 
     <li id="li_8735E76637ED4C3F983731A66E04C93E">量度模板 (<img placement="inline"  src="assets/cm_template_icon.png" width="25px" id="image_D236601511CC4DD3828F223431E27E88" />) - 位于列表底部。 </li> 
    </ul> <p>当您将光标悬停在量度上方时，可以在其右侧看到“信息”图标：<img placement="inline"  src="assets/info.png" width="150px" id="image_5A65E772A68A4B94ACAD6552CCF21F5F" />。单击此图标会显示以下信息： </p> 
    <ul id="ul_DF35DDB9FBFA40C8A93FA0F2286A0BBE"> 
     <li id="li_4215AA9BF93F4C8B941002A7A4D2F50B">有关如何计算量度的公式。 </li> 
     <li id="li_6A8E39EB6DCE4377B0B594B6D4FC0294">量度的预览趋势。 </li> 
     <li id="li_44C1595E4BE64ED69D1DB3BB6655ED55">位于右上角的编辑（铅笔）图标可使您转到计算量度生成器，以便在其中编辑此计算量度。 </li> 
    </ul> <p><img placement="break" align="center"  src="assets/info2.png" width="200px" id="image_7D5B2F026A034118BE4DA81B9215A883" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>过滤器列表 </p> </td> 
   <td colname="col3"> <p>（仅限高级计算量度）作为管理员，此列表会显示在您的登录公司中创建的所有过滤器。 如果您不是管理员用户，此列表会显示您拥有的过滤器以及与您共享的过滤器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>函数列表 </p> </td> 
   <td colname="col3"> <p>（仅限高级计算量度）函数将分为两个列表：<a href="/help/components/calc-metrics/cm-functions.md"  >基本</a>（最常用）和<a href="/help/components/calc-metrics/cm-adv-functions.md"  >高级</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>数据视图选择器 </p> </td> 
   <td colname="col3"> <p>允许您切换到其他数据视图。 </p> </td> 
  </tr> 
 </tbody> 
</table>
