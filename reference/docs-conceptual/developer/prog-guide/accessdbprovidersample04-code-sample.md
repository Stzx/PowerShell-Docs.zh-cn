---
title: AccessDbProviderSample04 代码示例 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 05509c5b36475bcd3f91c9ab7413974994d668d6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787268"
---
# <a name="accessdbprovidersample04-code-sample"></a><span data-ttu-id="4031f-102">AccessDbProviderSample04 代码示例</span><span class="sxs-lookup"><span data-stu-id="4031f-102">AccessDbProviderSample04 Code Sample</span></span>

<span data-ttu-id="4031f-103">下面的代码演示了在[创建 Windows Powershell 容器提供程序](./creating-a-windows-powershell-container-provider.md)中所述的 windows powershell 提供程序的实现。</span><span class="sxs-lookup"><span data-stu-id="4031f-103">The following code shows the implementation of the Windows PowerShell provider described in [Creating a Windows PowerShell Container Provider](./creating-a-windows-powershell-container-provider.md).</span></span>
<span data-ttu-id="4031f-104">此提供程序适用于多层数据存储区。</span><span class="sxs-lookup"><span data-stu-id="4031f-104">This provider works on multi-layer data stores.</span></span> <span data-ttu-id="4031f-105">对于这种类型的数据存储，存储区的顶层包含根项，而每个后续级别称为子项的节点。</span><span class="sxs-lookup"><span data-stu-id="4031f-105">For this type of data store, the top level of the store contains the root items and each subsequent level is referred to as a node of child items.</span></span> <span data-ttu-id="4031f-106">通过允许用户在这些子节点上工作，用户可以通过数据存储区进行分层交互。</span><span class="sxs-lookup"><span data-stu-id="4031f-106">By allowing the user to work on these child nodes, a user can interact hierarchically through the data store.</span></span>

## <a name="code-sample"></a><span data-ttu-id="4031f-107">代码示例</span><span class="sxs-lookup"><span data-stu-id="4031f-107">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs" range="11-1635":::

## <a name="see-also"></a><span data-ttu-id="4031f-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4031f-108">See Also</span></span>

[<span data-ttu-id="4031f-109">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="4031f-109">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
