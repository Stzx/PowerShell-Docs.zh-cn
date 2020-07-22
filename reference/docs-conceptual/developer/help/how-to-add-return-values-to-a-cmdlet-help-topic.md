---
title: 如何向 Cmdlet 帮助主题添加返回值
ms.date: 09/12/2016
ms.openlocfilehash: c164556cd06b332d04857987360c98f740a150b5
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893350"
---
# <a name="how-to-add-return-values-to-a-cmdlet-help-topic"></a><span data-ttu-id="bb852-102">如何向 Cmdlet 帮助主题添加返回值</span><span class="sxs-lookup"><span data-stu-id="bb852-102">How to Add Return Values to a Cmdlet Help Topic</span></span>

<span data-ttu-id="bb852-103">本部分介绍如何将输出部分添加到 PowerShell cmdlet 帮助主题。</span><span class="sxs-lookup"><span data-stu-id="bb852-103">This section describes how to add an OUTPUTS section to a PowerShell cmdlet Help topic.</span></span> <span data-ttu-id="bb852-104">"**输出**" 部分列出了 cmdlet 返回或沿管道向下传递的对象的 .net 类。</span><span class="sxs-lookup"><span data-stu-id="bb852-104">The **OUTPUTS** section lists the .NET classes of objects that the cmdlet returns or passes down the pipeline.</span></span>

<span data-ttu-id="bb852-105">可以添加到 "**输出**" 部分的类的数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="bb852-105">There is no limit to the number of classes that you can add to the **OUTPUTS** section.</span></span> <span data-ttu-id="bb852-106">Cmdlet 的返回类型包含在一个 `<command:returnValues>` 节点中，其中每个类都包含在一个 `<command:returnValue>` 元素中。</span><span class="sxs-lookup"><span data-stu-id="bb852-106">The return types of a cmdlet are enclosed in a `<command:returnValues>` node, with each class enclosed in a `<command:returnValue>` element.</span></span>

<span data-ttu-id="bb852-107">如果 cmdlet 未生成任何输出，请使用此部分来指示没有输出。</span><span class="sxs-lookup"><span data-stu-id="bb852-107">If a cmdlet does not generate any output, use this section to indicate that there is no output.</span></span> <span data-ttu-id="bb852-108">例如，若要替代类名称，请写入 "**无**" 并提供简短说明。</span><span class="sxs-lookup"><span data-stu-id="bb852-108">For example, in place of the class name, write **None** and provide a brief explanation.</span></span> <span data-ttu-id="bb852-109">如果 cmdlet 按条件生成输出，请使用此节点解释条件并描述条件输出。</span><span class="sxs-lookup"><span data-stu-id="bb852-109">If the cmdlet generates output conditionally, use this node to explain the conditions and describe the conditional output.</span></span>

<span data-ttu-id="bb852-110">架构包括 `<maml:description>` 每个元素中的两个元素 `<command:returnValue>` 。</span><span class="sxs-lookup"><span data-stu-id="bb852-110">The schema includes two `<maml:description>` elements in each `<command:returnValue>` element.</span></span>
<span data-ttu-id="bb852-111">但是，该 `Get-Help` cmdlet 只显示元素的内容 `<command:returnValue>/<maml:description>` 。</span><span class="sxs-lookup"><span data-stu-id="bb852-111">However, the `Get-Help` cmdlet displays only the content of the `<command:returnValue>/<maml:description>` element.</span></span>

<span data-ttu-id="bb852-112">从 PowerShell 3.0 开始， `Get-Help` cmdlet 显示元素的内容 `<maml:uri>` 。</span><span class="sxs-lookup"><span data-stu-id="bb852-112">Beginning in PowerShell 3.0, the `Get-Help` cmdlet displays the content of the `<maml:uri>` element.</span></span>
<span data-ttu-id="bb852-113">此元素使用户能够将用户定向到描述 .NET 类的主题。</span><span class="sxs-lookup"><span data-stu-id="bb852-113">This element lets you direct users to topics that describe the .NET class.</span></span>

<span data-ttu-id="bb852-114">下面的 XML 显示了 `<maml:returnValues>` 节点。</span><span class="sxs-lookup"><span data-stu-id="bb852-114">The following XML shows the `<maml:returnValues>` node.</span></span>

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

<span data-ttu-id="bb852-115">下面的 XML 演示使用 `<maml:returnValues>` 节点记录输出类型的示例。</span><span class="sxs-lookup"><span data-stu-id="bb852-115">The following XML shows an example of using the `<maml:returnValues>` node to document an output type.</span></span>

```xml
<command:returnValues>
  <command:returnValue>
    <dev:type>
      <maml:name> System.DateTime </maml:name>
      <maml:uri>  https://msdn.microsoft.com/library/system.datetime.aspx </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> Get-Date returns a DateTime object. <maml:para>
    </maml:description>
  </command: returnValue>
</command: returnValues>
```
