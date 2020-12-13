---
ms.date: 09/13/2016
ms.topic: reference
title: AccessDBProviderSample01
description: AccessDBProviderSample01
ms.openlocfilehash: 8bdfa3ad492935a22ce06846294c02961cab2c65
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653757"
---
# <a name="accessdbprovidersample01"></a><span data-ttu-id="a6e30-103">AccessDBProviderSample01</span><span class="sxs-lookup"><span data-stu-id="a6e30-103">AccessDBProviderSample01</span></span>

<span data-ttu-id="a6e30-104">此示例演示如何声明一个直接从 [Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) 类派生的提供程序类。</span><span class="sxs-lookup"><span data-stu-id="a6e30-104">This sample shows how to declare a provider class that derives directly from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) class.</span></span> <span data-ttu-id="a6e30-105">仅出于完整性考虑而在此处包含此项。</span><span class="sxs-lookup"><span data-stu-id="a6e30-105">It is included here only for completeness.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="a6e30-106">演示</span><span class="sxs-lookup"><span data-stu-id="a6e30-106">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6e30-107">提供程序类最有可能派生自以下类之一，并可能实现其他提供程序接口：</span><span class="sxs-lookup"><span data-stu-id="a6e30-107">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> - <span data-ttu-id="a6e30-108">" [Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) " 类。</span><span class="sxs-lookup"><span data-stu-id="a6e30-108">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="a6e30-109">请参阅 [AccessDBProviderSample03](./accessdbprovidersample03.md)。</span><span class="sxs-lookup"><span data-stu-id="a6e30-109">See [AccessDBProviderSample03](./accessdbprovidersample03.md).</span></span>
> - <span data-ttu-id="a6e30-110">" [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) " 类。</span><span class="sxs-lookup"><span data-stu-id="a6e30-110">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="a6e30-111">请参阅 [AccessDBProviderSample04](./accessdbprovidersample04.md)。</span><span class="sxs-lookup"><span data-stu-id="a6e30-111">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> - <span data-ttu-id="a6e30-112">" [Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) " 类。</span><span class="sxs-lookup"><span data-stu-id="a6e30-112">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span> <span data-ttu-id="a6e30-113">请参阅 [AccessDBProviderSample05](./accessdbprovidersample05.md)。</span><span class="sxs-lookup"><span data-stu-id="a6e30-113">See [AccessDBProviderSample05](./accessdbprovidersample05.md).</span></span>
>
> <span data-ttu-id="a6e30-114">有关根据提供程序功能选择要从哪个提供程序类派生的详细信息，请参阅 [设计你的 Windows PowerShell 提供程序](./provider-types.md)。</span><span class="sxs-lookup"><span data-stu-id="a6e30-114">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="a6e30-115">此示例对下列内容进行了说明：</span><span class="sxs-lookup"><span data-stu-id="a6e30-115">This sample demonstrates the following:</span></span>

- <span data-ttu-id="a6e30-116">声明 `CmdletProvider` 特性。</span><span class="sxs-lookup"><span data-stu-id="a6e30-116">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="a6e30-117">定义直接从 [Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) 类中派生的提供程序类。</span><span class="sxs-lookup"><span data-stu-id="a6e30-117">Defining a provider class that derives directly from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) class.</span></span>

## <a name="example"></a><span data-ttu-id="a6e30-118">示例</span><span class="sxs-lookup"><span data-stu-id="a6e30-118">Example</span></span>

<span data-ttu-id="a6e30-119">此示例演示如何定义提供程序类以及如何声明 `CmdletProvider` 特性。</span><span class="sxs-lookup"><span data-stu-id="a6e30-119">This sample shows how to define a provider class and how to declare the `CmdletProvider` attribute.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample01/AccessDBProviderSample01.cs" range="11-30":::

## <a name="see-also"></a><span data-ttu-id="a6e30-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a6e30-120">See Also</span></span>

[<span data-ttu-id="a6e30-121">"Itemcmdletprovider"。</span><span class="sxs-lookup"><span data-stu-id="a6e30-121">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="a6e30-122">"Containercmdletprovider"。</span><span class="sxs-lookup"><span data-stu-id="a6e30-122">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="a6e30-123">"Navigationcmdletprovider"。</span><span class="sxs-lookup"><span data-stu-id="a6e30-123">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="a6e30-124">设计 Windows PowerShell 提供程序</span><span class="sxs-lookup"><span data-stu-id="a6e30-124">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)
