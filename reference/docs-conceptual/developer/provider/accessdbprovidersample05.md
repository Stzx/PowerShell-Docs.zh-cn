---
title: AccessDBProviderSample05 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 67a10d9192350b339da1b82d9eb367ee4af6ef86
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786843"
---
# <a name="accessdbprovidersample05"></a><span data-ttu-id="950ae-102">AccessDBProviderSample05</span><span class="sxs-lookup"><span data-stu-id="950ae-102">AccessDBProviderSample05</span></span>

<span data-ttu-id="950ae-103">此示例演示如何覆盖容器方法以支持调用 `Move-Item` 和 `Join-Path` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="950ae-103">This sample shows how to overwrite container methods to support calls to the `Move-Item` and `Join-Path` cmdlets.</span></span> <span data-ttu-id="950ae-104">当用户需要移动容器中的项时，如果数据存储区包含嵌套的容器，则应实现这些方法。</span><span class="sxs-lookup"><span data-stu-id="950ae-104">These methods should be implemented when the user needs to move items within a container and if the data store contains nested containers.</span></span> <span data-ttu-id="950ae-105">此示例中的提供程序类派生自[Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)类。</span><span class="sxs-lookup"><span data-stu-id="950ae-105">The provider class in this sample derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="950ae-106">演示</span><span class="sxs-lookup"><span data-stu-id="950ae-106">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="950ae-107">提供程序类最有可能派生自以下类之一，并可能实现其他提供程序接口：</span><span class="sxs-lookup"><span data-stu-id="950ae-107">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> - <span data-ttu-id="950ae-108">" [Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) " 类。</span><span class="sxs-lookup"><span data-stu-id="950ae-108">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="950ae-109">请参阅[AccessDBProviderSample03](./accessdbprovidersample03.md)。</span><span class="sxs-lookup"><span data-stu-id="950ae-109">See [AccessDBProviderSample03](./accessdbprovidersample03.md).</span></span>
> - <span data-ttu-id="950ae-110">" [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) " 类。</span><span class="sxs-lookup"><span data-stu-id="950ae-110">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="950ae-111">请参阅[AccessDBProviderSample04](./accessdbprovidersample04.md)。</span><span class="sxs-lookup"><span data-stu-id="950ae-111">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> - <span data-ttu-id="950ae-112">" [Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) " 类。</span><span class="sxs-lookup"><span data-stu-id="950ae-112">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>
>
> <span data-ttu-id="950ae-113">有关根据提供程序功能选择要从哪个提供程序类派生的详细信息，请参阅[设计你的 Windows PowerShell 提供程序](./provider-types.md)。</span><span class="sxs-lookup"><span data-stu-id="950ae-113">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="950ae-114">此示例对下列内容进行了说明：</span><span class="sxs-lookup"><span data-stu-id="950ae-114">This sample demonstrates the following:</span></span>

- <span data-ttu-id="950ae-115">声明 `CmdletProvider` 特性。</span><span class="sxs-lookup"><span data-stu-id="950ae-115">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="950ae-116">定义一个派生自[Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)类的提供程序类。</span><span class="sxs-lookup"><span data-stu-id="950ae-116">Defining a provider class that derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>

- <span data-ttu-id="950ae-117">覆盖[Navigationcmdletprovider. Moveitem \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem)方法以更改 cmdlet 的行为 `Move-Item` ，允许用户将项从一个位置移到另一个位置。</span><span class="sxs-lookup"><span data-stu-id="950ae-117">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) method to change the behavior of the `Move-Item` cmdlet, allowing the user to move items from one location to another.</span></span> <span data-ttu-id="950ae-118"> (此示例不显示如何将动态参数添加到 `Move-Item` cmdlet。 ) </span><span class="sxs-lookup"><span data-stu-id="950ae-118">(This sample does not show how to add dynamic parameters to the `Move-Item` cmdlet.)</span></span>

- <span data-ttu-id="950ae-119">覆盖[Navigationcmdletprovider. Makepath \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath)方法，以更改 cmdlet 的行为方式 `Join-Path` 。</span><span class="sxs-lookup"><span data-stu-id="950ae-119">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) method to change the behavior of the `Join-Path` cmdlet.</span></span>

- <span data-ttu-id="950ae-120">正在重写[Navigationcmdletprovider. Isitemcontainer \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer)方法。</span><span class="sxs-lookup"><span data-stu-id="950ae-120">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Isitemcontainer\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) method.</span></span>

- <span data-ttu-id="950ae-121">正在重写[Navigationcmdletprovider. Getchildname \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName)方法。</span><span class="sxs-lookup"><span data-stu-id="950ae-121">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Getchildname\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) method.</span></span>

- <span data-ttu-id="950ae-122">正在重写[Navigationcmdletprovider. Getparentpath \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath)方法。</span><span class="sxs-lookup"><span data-stu-id="950ae-122">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Getparentpath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) method.</span></span>

- <span data-ttu-id="950ae-123">正在重写[Navigationcmdletprovider. Normalizerelativepath \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath)方法。</span><span class="sxs-lookup"><span data-stu-id="950ae-123">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Normalizerelativepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) method.</span></span>

## <a name="example"></a><span data-ttu-id="950ae-124">示例</span><span class="sxs-lookup"><span data-stu-id="950ae-124">Example</span></span>

<span data-ttu-id="950ae-125">此示例演示如何覆盖在 Microsoft Access 数据库中移动项所需的方法。</span><span class="sxs-lookup"><span data-stu-id="950ae-125">This sample shows how to overwrite the methods needed to move items in a Microsoft Access data base.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample05/AccessDBProviderSample05.cs" range="11-1960":::

## <a name="see-also"></a><span data-ttu-id="950ae-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="950ae-126">See Also</span></span>

[<span data-ttu-id="950ae-127">"Itemcmdletprovider"。</span><span class="sxs-lookup"><span data-stu-id="950ae-127">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="950ae-128">"Containercmdletprovider"。</span><span class="sxs-lookup"><span data-stu-id="950ae-128">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="950ae-129">"Navigationcmdletprovider"。</span><span class="sxs-lookup"><span data-stu-id="950ae-129">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="950ae-130">设计 Windows PowerShell 提供程序</span><span class="sxs-lookup"><span data-stu-id="950ae-130">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)
