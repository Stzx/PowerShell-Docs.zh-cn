---
ms.date: 09/13/2016
ms.topic: reference
title: AccessDBProviderSample03
description: AccessDBProviderSample03
ms.openlocfilehash: bfd402903a9023b58dec8865663e3d649a50e1e1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667396"
---
# <a name="accessdbprovidersample03"></a><span data-ttu-id="17277-103">AccessDBProviderSample03</span><span class="sxs-lookup"><span data-stu-id="17277-103">AccessDBProviderSample03</span></span>

<span data-ttu-id="17277-104">此示例演示如何覆盖[Getitem \* 和 Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) [\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)方法，以支持对 `Get-Item` 和 cmdlet 的调用的情况下出现的情况，请重写。 `Set-Item`</span><span class="sxs-lookup"><span data-stu-id="17277-104">This sample shows how to overwrite the [System.Management.Automation.Provider.Itemcmdletprovider.Getitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) and [System.Management.Automation.Provider.Itemcmdletprovider.Setitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) methods to support calls to the `Get-Item` and `Set-Item` cmdlets.</span></span> <span data-ttu-id="17277-105">此示例中的提供程序类派生自 [Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) 类。</span><span class="sxs-lookup"><span data-stu-id="17277-105">The provider class in this sample derives from the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="17277-106">演示</span><span class="sxs-lookup"><span data-stu-id="17277-106">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="17277-107">提供程序类最有可能派生自以下类之一，并可能实现其他提供程序接口：</span><span class="sxs-lookup"><span data-stu-id="17277-107">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> - <span data-ttu-id="17277-108">" [Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) " 类。</span><span class="sxs-lookup"><span data-stu-id="17277-108">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span>
> - <span data-ttu-id="17277-109">" [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) " 类。</span><span class="sxs-lookup"><span data-stu-id="17277-109">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="17277-110">请参阅 [AccessDBProviderSample04](./accessdbprovidersample04.md)。</span><span class="sxs-lookup"><span data-stu-id="17277-110">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> - <span data-ttu-id="17277-111">" [Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) " 类。</span><span class="sxs-lookup"><span data-stu-id="17277-111">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span> <span data-ttu-id="17277-112">请参阅 [AccessDBProviderSample05](./accessdbprovidersample05.md)。</span><span class="sxs-lookup"><span data-stu-id="17277-112">See [AccessDBProviderSample05](./accessdbprovidersample05.md).</span></span>
>
> <span data-ttu-id="17277-113">有关根据提供程序功能选择要从哪个提供程序类派生的详细信息，请参阅 [设计你的 Windows PowerShell 提供程序](./provider-types.md)。</span><span class="sxs-lookup"><span data-stu-id="17277-113">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="17277-114">此示例对下列内容进行了说明：</span><span class="sxs-lookup"><span data-stu-id="17277-114">This sample demonstrates the following:</span></span>

- <span data-ttu-id="17277-115">声明 `CmdletProvider` 特性。</span><span class="sxs-lookup"><span data-stu-id="17277-115">Declaring the `CmdletProvider` attribute.</span></span>
- <span data-ttu-id="17277-116">定义一个派生自 [Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) 类的提供程序类。</span><span class="sxs-lookup"><span data-stu-id="17277-116">Defining a provider class that derives from the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span>
- <span data-ttu-id="17277-117">覆盖 [Drivecmdletprovider. Newdrive \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) 方法，以更改 cmdlet 的行为 `New-PSDrive` ，从而允许用户创建新的驱动器。</span><span class="sxs-lookup"><span data-stu-id="17277-117">Overwriting the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) method to change the behavior of the `New-PSDrive` cmdlet, allowing the user to create new drives.</span></span>
  <span data-ttu-id="17277-118"> (此示例不显示如何将动态参数添加到 `New-PSDrive` cmdlet。 ) </span><span class="sxs-lookup"><span data-stu-id="17277-118">(This sample does not show how to add dynamic parameters to the `New-PSDrive` cmdlet.)</span></span>
- <span data-ttu-id="17277-119">覆盖 [Drivecmdletprovider. Removedrive \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) 方法，以支持删除现有驱动器。</span><span class="sxs-lookup"><span data-stu-id="17277-119">Overwriting the [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) method to support removing existing drives.</span></span>
- <span data-ttu-id="17277-120">覆盖 [Itemcmdletprovider. Getitem \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) 方法，以更改 cmdlet 的行为 `Get-Item` ，从而允许用户从数据存储中检索项。</span><span class="sxs-lookup"><span data-stu-id="17277-120">Overwriting the [System.Management.Automation.Provider.Itemcmdletprovider.Getitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) method to change the behavior of the `Get-Item` cmdlet, allowing the user to retrieve items from the data store.</span></span> <span data-ttu-id="17277-121"> (此示例不显示如何将动态参数添加到 `Get-Item` cmdlet。 ) </span><span class="sxs-lookup"><span data-stu-id="17277-121">(This sample does not show how to add dynamic parameters to the `Get-Item` cmdlet.)</span></span>
- <span data-ttu-id="17277-122">覆盖 [Setitem \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) 方法以更改 cmdlet 的行为 `Set-Item` ，使用户能够更新数据存储区中的项，从而使其 Itemcmdletprovider。</span><span class="sxs-lookup"><span data-stu-id="17277-122">Overwriting the [System.Management.Automation.Provider.Itemcmdletprovider.Setitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) method to change the behavior of the `Set-Item` cmdlet, allowing the user to update the items in the data store.</span></span> <span data-ttu-id="17277-123"> (此示例不显示如何将动态参数添加到 `Get-Item` cmdlet。 ) </span><span class="sxs-lookup"><span data-stu-id="17277-123">(This sample does not show how to add dynamic parameters to the `Get-Item` cmdlet.)</span></span>
- <span data-ttu-id="17277-124">覆盖 [Itemcmdletprovider. Itemexists \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) 方法，以更改 cmdlet 的行为方式 `Test-Path` 。</span><span class="sxs-lookup"><span data-stu-id="17277-124">Overwriting the [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) method to change the behavior of the `Test-Path` cmdlet.</span></span> <span data-ttu-id="17277-125"> (此示例不显示如何将动态参数添加到 `Test-Path` cmdlet。 ) </span><span class="sxs-lookup"><span data-stu-id="17277-125">(This sample does not show how to add dynamic parameters to the `Test-Path` cmdlet.)</span></span>
- <span data-ttu-id="17277-126">覆盖 [Itemcmdletprovider. Isvalidpath \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) 方法，以确定提供的路径是否有效。</span><span class="sxs-lookup"><span data-stu-id="17277-126">Overwriting the [System.Management.Automation.Provider.Itemcmdletprovider.Isvalidpath\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) method to determine if the provided path is valid.</span></span>

## <a name="example"></a><span data-ttu-id="17277-127">示例</span><span class="sxs-lookup"><span data-stu-id="17277-127">Example</span></span>

<span data-ttu-id="17277-128">此示例演示如何覆盖获取和设置 Microsoft Access 数据库中的项所需的方法。</span><span class="sxs-lookup"><span data-stu-id="17277-128">This sample shows how to overwrite the methods needed to get and set items in a Microsoft Access data base.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample03/AccessDBProviderSample03.cs" range="11-976":::

## <a name="see-also"></a><span data-ttu-id="17277-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="17277-129">See Also</span></span>

[<span data-ttu-id="17277-130">"Itemcmdletprovider"。</span><span class="sxs-lookup"><span data-stu-id="17277-130">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="17277-131">"Containercmdletprovider"。</span><span class="sxs-lookup"><span data-stu-id="17277-131">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="17277-132">"Navigationcmdletprovider"。</span><span class="sxs-lookup"><span data-stu-id="17277-132">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="17277-133">设计 Windows PowerShell 提供程序</span><span class="sxs-lookup"><span data-stu-id="17277-133">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)
