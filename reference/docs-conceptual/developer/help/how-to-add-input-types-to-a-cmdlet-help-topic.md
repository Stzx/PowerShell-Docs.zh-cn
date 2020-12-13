---
ms.date: 09/12/2016
ms.topic: reference
title: 如何向 Cmdlet 帮助主题添加输入类型
description: 如何向 Cmdlet 帮助主题添加输入类型
ms.openlocfilehash: f2ad87c54230bcdd7e0ea708e9a1869daef7495f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "94391096"
---
# <a name="how-to-add-input-types-to-a-cmdlet-help-topic"></a><span data-ttu-id="42bec-103">如何向 Cmdlet 帮助主题添加输入类型</span><span class="sxs-lookup"><span data-stu-id="42bec-103">How to Add Input Types to a Cmdlet Help Topic</span></span>

<span data-ttu-id="42bec-104">本部分介绍如何将 **输入** 部分添加到 PowerShell cmdlet 帮助主题。</span><span class="sxs-lookup"><span data-stu-id="42bec-104">This section describes how to add an **INPUTS** section to a PowerShell cmdlet Help topic.</span></span> <span data-ttu-id="42bec-105">" **输入** " 部分列出了 cmdlet 作为管道的输入接受的对象的 .net 类，可以通过值或按属性名称。</span><span class="sxs-lookup"><span data-stu-id="42bec-105">The **INPUTS** section lists the .NET classes of objects that the cmdlet accepts as input from the pipeline, either by value or by property name.</span></span>

<span data-ttu-id="42bec-106">可以添加到 **输入** 部分的类的数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="42bec-106">There is no limit to the number of classes that you can add to an **INPUTS** section.</span></span> <span data-ttu-id="42bec-107">输入类型括在 `<command:inputTypes>` 节点中，每个类都包含在元素中 `<command:inputType>` 。</span><span class="sxs-lookup"><span data-stu-id="42bec-107">The input types are enclosed in a `<command:inputTypes>` node, with each class enclosed in a `<command:inputType>` element.</span></span>

<span data-ttu-id="42bec-108">架构包括 `<maml:description>` 每个元素中的两个元素 `<command:inputType>` 。</span><span class="sxs-lookup"><span data-stu-id="42bec-108">The schema includes two `<maml:description>` elements in each `<command:inputType>` element.</span></span>
<span data-ttu-id="42bec-109">但是，该 `Get-Help` cmdlet 只显示元素的内容 `<command:inputType>/<maml:description>` 。</span><span class="sxs-lookup"><span data-stu-id="42bec-109">However, the `Get-Help` cmdlet displays only the content of the `<command:inputType>/<maml:description>` element.</span></span>

<span data-ttu-id="42bec-110">从 PowerShell 3.0 开始， `Get-Help` cmdlet 显示元素的内容 `<maml:uri>` 。</span><span class="sxs-lookup"><span data-stu-id="42bec-110">Beginning in PowerShell 3.0, the `Get-Help` cmdlet displays the content of the `<maml:uri>` element.</span></span>
<span data-ttu-id="42bec-111">此元素使用户能够将用户定向到描述 .NET 类的主题。</span><span class="sxs-lookup"><span data-stu-id="42bec-111">This element lets you direct users to topics that describe the .NET class.</span></span>

<span data-ttu-id="42bec-112">下面的 XML 显示了 `<maml:inputTypes>` 节点。</span><span class="sxs-lookup"><span data-stu-id="42bec-112">The following XML shows the `<maml:inputTypes>` node.</span></span>

```xml
<command:inputTypes>
  <command:inputType>
    <dev:type>
      <maml:name> Class name </maml:name>
      <maml:uri>  URI of a topic that describes the class </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> Brief description </maml:para>
    </maml:description>
  </command:inputType>
</command:inputTypes>
```

<span data-ttu-id="42bec-113">下面的 XML 演示使用 `<maml:inputTypes>` 节点记录输入类型的示例。</span><span class="sxs-lookup"><span data-stu-id="42bec-113">The following XML shows an example of using the `<maml:inputTypes>` node to document an input type.</span></span>

```xml
<command:inputTypes>
  <command:inputType>
    <dev:type>
      <maml:name>System.DateTime</maml:name>
      <maml:uri>https://docs.microsoft.com/dotnet/api/system.datetime</maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> You can pipe a date to the Set-Date cmdlet. <maml:para>
    <maml:description>
  </command:inputType>
</command:inputTypes>
```
