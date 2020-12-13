---
ms.date: 09/12/2016
ms.topic: reference
title: 如何向 Cmdlet 帮助主题添加返回值
description: 如何向 Cmdlet 帮助主题添加返回值
ms.openlocfilehash: 8c556821a257451a320916231cb20fc82e75ebb4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "94389736"
---
# <a name="how-to-add-return-values-to-a-cmdlet-help-topic"></a><span data-ttu-id="10dcc-103">如何向 Cmdlet 帮助主题添加返回值</span><span class="sxs-lookup"><span data-stu-id="10dcc-103">How to Add Return Values to a Cmdlet Help Topic</span></span>

<span data-ttu-id="10dcc-104">本部分介绍如何将输出部分添加到 PowerShell cmdlet 帮助主题。</span><span class="sxs-lookup"><span data-stu-id="10dcc-104">This section describes how to add an OUTPUTS section to a PowerShell cmdlet Help topic.</span></span> <span data-ttu-id="10dcc-105">" **输出** " 部分列出了 cmdlet 返回或沿管道向下传递的对象的 .net 类。</span><span class="sxs-lookup"><span data-stu-id="10dcc-105">The **OUTPUTS** section lists the .NET classes of objects that the cmdlet returns or passes down the pipeline.</span></span>

<span data-ttu-id="10dcc-106">可以添加到 " **输出** " 部分的类的数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="10dcc-106">There is no limit to the number of classes that you can add to the **OUTPUTS** section.</span></span> <span data-ttu-id="10dcc-107">Cmdlet 的返回类型包含在一个 `<command:returnValues>` 节点中，其中每个类都包含在一个 `<command:returnValue>` 元素中。</span><span class="sxs-lookup"><span data-stu-id="10dcc-107">The return types of a cmdlet are enclosed in a `<command:returnValues>` node, with each class enclosed in a `<command:returnValue>` element.</span></span>

<span data-ttu-id="10dcc-108">如果 cmdlet 未生成任何输出，请使用此部分来指示没有输出。</span><span class="sxs-lookup"><span data-stu-id="10dcc-108">If a cmdlet does not generate any output, use this section to indicate that there is no output.</span></span> <span data-ttu-id="10dcc-109">例如，若要替代类名称，请写入 " **无** " 并提供简短说明。</span><span class="sxs-lookup"><span data-stu-id="10dcc-109">For example, in place of the class name, write **None** and provide a brief explanation.</span></span> <span data-ttu-id="10dcc-110">如果 cmdlet 按条件生成输出，请使用此节点解释条件并描述条件输出。</span><span class="sxs-lookup"><span data-stu-id="10dcc-110">If the cmdlet generates output conditionally, use this node to explain the conditions and describe the conditional output.</span></span>

<span data-ttu-id="10dcc-111">架构包括 `<maml:description>` 每个元素中的两个元素 `<command:returnValue>` 。</span><span class="sxs-lookup"><span data-stu-id="10dcc-111">The schema includes two `<maml:description>` elements in each `<command:returnValue>` element.</span></span>
<span data-ttu-id="10dcc-112">但是，该 `Get-Help` cmdlet 只显示元素的内容 `<command:returnValue>/<maml:description>` 。</span><span class="sxs-lookup"><span data-stu-id="10dcc-112">However, the `Get-Help` cmdlet displays only the content of the `<command:returnValue>/<maml:description>` element.</span></span>

<span data-ttu-id="10dcc-113">从 PowerShell 3.0 开始， `Get-Help` cmdlet 显示元素的内容 `<maml:uri>` 。</span><span class="sxs-lookup"><span data-stu-id="10dcc-113">Beginning in PowerShell 3.0, the `Get-Help` cmdlet displays the content of the `<maml:uri>` element.</span></span>
<span data-ttu-id="10dcc-114">此元素使用户能够将用户定向到描述 .NET 类的主题。</span><span class="sxs-lookup"><span data-stu-id="10dcc-114">This element lets you direct users to topics that describe the .NET class.</span></span>

<span data-ttu-id="10dcc-115">下面的 XML 显示了 `<maml:returnValues>` 节点。</span><span class="sxs-lookup"><span data-stu-id="10dcc-115">The following XML shows the `<maml:returnValues>` node.</span></span>

```xml
<command:returnValues>
  <command:returnValue>
    <dev:type>
      <maml:name> Class Name </maml:name>
      <maml:uri>  URI of a topic that describes the class </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
       <maml:para> Brief description <maml:para>

</maml:description>
  </command: returnValue>
</command: returnValues>
```

<span data-ttu-id="10dcc-116">下面的 XML 演示使用 `<maml:returnValues>` 节点记录输出类型的示例。</span><span class="sxs-lookup"><span data-stu-id="10dcc-116">The following XML shows an example of using the `<maml:returnValues>` node to document an output type.</span></span>

```xml
<command:returnValues>
  <command:returnValue>
    <dev:type>
      <maml:name> System.DateTime </maml:name>
      <maml:uri>  https://docs.microsoft.com/dotnet/api/system.datetime </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> Get-Date returns a DateTime object. <maml:para>
    </maml:description>
  </command: returnValue>
</command: returnValues>
```
