---
ms.date: 09/13/2016
ms.topic: reference
title: AccessDbProviderSample04 代码示例
description: AccessDbProviderSample04 代码示例
ms.openlocfilehash: bb70ce9f1b1c94349c354a8771fedf7fcb1bb320
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647570"
---
# <a name="accessdbprovidersample04-code-sample"></a><span data-ttu-id="86ecf-103">AccessDbProviderSample04 代码示例</span><span class="sxs-lookup"><span data-stu-id="86ecf-103">AccessDbProviderSample04 Code Sample</span></span>

<span data-ttu-id="86ecf-104">下面的代码演示了在 [创建 Windows Powershell 容器提供程序](./creating-a-windows-powershell-container-provider.md)中所述的 windows powershell 提供程序的实现。</span><span class="sxs-lookup"><span data-stu-id="86ecf-104">The following code shows the implementation of the Windows PowerShell provider described in [Creating a Windows PowerShell Container Provider](./creating-a-windows-powershell-container-provider.md).</span></span>
<span data-ttu-id="86ecf-105">此提供程序适用于多层数据存储区。</span><span class="sxs-lookup"><span data-stu-id="86ecf-105">This provider works on multi-layer data stores.</span></span> <span data-ttu-id="86ecf-106">对于这种类型的数据存储，存储区的顶层包含根项，而每个后续级别称为子项的节点。</span><span class="sxs-lookup"><span data-stu-id="86ecf-106">For this type of data store, the top level of the store contains the root items and each subsequent level is referred to as a node of child items.</span></span> <span data-ttu-id="86ecf-107">通过允许用户在这些子节点上工作，用户可以通过数据存储区进行分层交互。</span><span class="sxs-lookup"><span data-stu-id="86ecf-107">By allowing the user to work on these child nodes, a user can interact hierarchically through the data store.</span></span>

## <a name="code-sample"></a><span data-ttu-id="86ecf-108">代码示例</span><span class="sxs-lookup"><span data-stu-id="86ecf-108">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs" range="11-1635":::

## <a name="see-also"></a><span data-ttu-id="86ecf-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86ecf-109">See Also</span></span>

[<span data-ttu-id="86ecf-110">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="86ecf-110">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
