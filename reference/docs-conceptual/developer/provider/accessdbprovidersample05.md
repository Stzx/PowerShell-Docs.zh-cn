---
ms.date: 09/13/2016
ms.topic: reference
title: AccessDBProviderSample05
description: AccessDBProviderSample05
ms.openlocfilehash: ad273720ded0b200530f4f81482d01a8fbb82aa3
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92656907"
---
# <a name="accessdbprovidersample05"></a><span data-ttu-id="310e9-103">AccessDBProviderSample05</span><span class="sxs-lookup"><span data-stu-id="310e9-103">AccessDBProviderSample05</span></span>

<span data-ttu-id="310e9-104">此示例演示如何覆盖容器方法以支持调用 `Move-Item` 和 `Join-Path` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="310e9-104">This sample shows how to overwrite container methods to support calls to the `Move-Item` and `Join-Path` cmdlets.</span></span> <span data-ttu-id="310e9-105">当用户需要移动容器中的项时，如果数据存储区包含嵌套的容器，则应实现这些方法。</span><span class="sxs-lookup"><span data-stu-id="310e9-105">These methods should be implemented when the user needs to move items within a container and if the data store contains nested containers.</span></span> <span data-ttu-id="310e9-106">此示例中的提供程序类派生自 [Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) 类。</span><span class="sxs-lookup"><span data-stu-id="310e9-106">The provider class in this sample derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="310e9-107">演示</span><span class="sxs-lookup"><span data-stu-id="310e9-107">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="310e9-108">提供程序类最有可能派生自以下类之一，并可能实现其他提供程序接口：</span><span class="sxs-lookup"><span data-stu-id="310e9-108">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> - <span data-ttu-id="310e9-109">" [Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) " 类。</span><span class="sxs-lookup"><span data-stu-id="310e9-109">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="310e9-110">请参阅 [AccessDBProviderSample03](./accessdbprovidersample03.md)。</span><span class="sxs-lookup"><span data-stu-id="310e9-110">See [AccessDBProviderSample03](./accessdbprovidersample03.md).</span></span>
> - <span data-ttu-id="310e9-111">" [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) " 类。</span><span class="sxs-lookup"><span data-stu-id="310e9-111">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="310e9-112">请参阅 [AccessDBProviderSample04](./accessdbprovidersample04.md)。</span><span class="sxs-lookup"><span data-stu-id="310e9-112">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> - <span data-ttu-id="310e9-113">" [Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) " 类。</span><span class="sxs-lookup"><span data-stu-id="310e9-113">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>
>
> <span data-ttu-id="310e9-114">有关根据提供程序功能选择要从哪个提供程序类派生的详细信息，请参阅 [设计你的 Windows PowerShell 提供程序](./provider-types.md)。</span><span class="sxs-lookup"><span data-stu-id="310e9-114">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="310e9-115">此示例对下列内容进行了说明：</span><span class="sxs-lookup"><span data-stu-id="310e9-115">This sample demonstrates the following:</span></span>

- <span data-ttu-id="310e9-116">声明 `CmdletProvider` 特性。</span><span class="sxs-lookup"><span data-stu-id="310e9-116">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="310e9-117">定义一个派生自 [Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) 类的提供程序类。</span><span class="sxs-lookup"><span data-stu-id="310e9-117">Defining a provider class that derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>

- <span data-ttu-id="310e9-118">覆盖 [Navigationcmdletprovider. Moveitem \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) 方法以更改 cmdlet 的行为 `Move-Item` ，允许用户将项从一个位置移到另一个位置。</span><span class="sxs-lookup"><span data-stu-id="310e9-118">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) method to change the behavior of the `Move-Item` cmdlet, allowing the user to move items from one location to another.</span></span> <span data-ttu-id="310e9-119"> (此示例不显示如何将动态参数添加到 `Move-Item` cmdlet。 ) </span><span class="sxs-lookup"><span data-stu-id="310e9-119">(This sample does not show how to add dynamic parameters to the `Move-Item` cmdlet.)</span></span>

- <span data-ttu-id="310e9-120">覆盖 [Navigationcmdletprovider. Makepath \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) 方法，以更改 cmdlet 的行为方式 `Join-Path` 。</span><span class="sxs-lookup"><span data-stu-id="310e9-120">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) method to change the behavior of the `Join-Path` cmdlet.</span></span>

- <span data-ttu-id="310e9-121">正在重写 [Navigationcmdletprovider. Isitemcontainer \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) 方法。</span><span class="sxs-lookup"><span data-stu-id="310e9-121">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Isitemcontainer\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) method.</span></span>

- <span data-ttu-id="310e9-122">正在重写 [Navigationcmdletprovider. Getchildname \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) 方法。</span><span class="sxs-lookup"><span data-stu-id="310e9-122">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Getchildname\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) method.</span></span>

- <span data-ttu-id="310e9-123">正在重写 [Navigationcmdletprovider. Getparentpath \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) 方法。</span><span class="sxs-lookup"><span data-stu-id="310e9-123">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Getparentpath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) method.</span></span>

- <span data-ttu-id="310e9-124">正在重写 [Navigationcmdletprovider. Normalizerelativepath \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) 方法。</span><span class="sxs-lookup"><span data-stu-id="310e9-124">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Normalizerelativepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) method.</span></span>

## <a name="example"></a><span data-ttu-id="310e9-125">示例</span><span class="sxs-lookup"><span data-stu-id="310e9-125">Example</span></span>

<span data-ttu-id="310e9-126">此示例演示如何覆盖在 Microsoft Access 数据库中移动项所需的方法。</span><span class="sxs-lookup"><span data-stu-id="310e9-126">This sample shows how to overwrite the methods needed to move items in a Microsoft Access data base.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample05/AccessDBProviderSample05.cs" range="11-1960":::

## <a name="see-also"></a><span data-ttu-id="310e9-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="310e9-127">See Also</span></span>

[<span data-ttu-id="310e9-128">"Itemcmdletprovider"。</span><span class="sxs-lookup"><span data-stu-id="310e9-128">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="310e9-129">"Containercmdletprovider"。</span><span class="sxs-lookup"><span data-stu-id="310e9-129">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="310e9-130">"Navigationcmdletprovider"。</span><span class="sxs-lookup"><span data-stu-id="310e9-130">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="310e9-131">设计 Windows PowerShell 提供程序</span><span class="sxs-lookup"><span data-stu-id="310e9-131">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)
