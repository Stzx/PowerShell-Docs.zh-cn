---
ms.date: 09/13/2016
ms.topic: reference
title: Windows PowerShell 提供程序概述
description: Windows PowerShell 提供程序概述
ms.openlocfilehash: 2f1c5f5991a64fb2b85ece7feba915164ebd34ee
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355504"
---
# <a name="windows-powershell-provider-overview"></a><span data-ttu-id="fc20f-103">Windows PowerShell 提供程序概述</span><span class="sxs-lookup"><span data-stu-id="fc20f-103">Windows PowerShell Provider Overview</span></span>

<span data-ttu-id="fc20f-104">Windows PowerShell 提供程序允许像文件系统一样公开任何数据存储，就像它是装入的驱动器一样。</span><span class="sxs-lookup"><span data-stu-id="fc20f-104">A Windows PowerShell provider allows any data store to be exposed like a file system as if it were a mounted drive.</span></span> <span data-ttu-id="fc20f-105">例如，内置的注册表提供程序允许你在注册表中导航，就像浏览 `c` 计算机驱动器一样。</span><span class="sxs-lookup"><span data-stu-id="fc20f-105">For example, the built-in Registry provider allows you to navigate the registry like you would navigate the `c` drive of your computer.</span></span> <span data-ttu-id="fc20f-106">提供程序还可以重写 `Item` cmdlet (例如，、等） `Get-Item` `Set-Item` ) 这样可以处理数据存储区中的数据，如在导航文件系统时处理文件和目录。</span><span class="sxs-lookup"><span data-stu-id="fc20f-106">A provider can also override the `Item` cmdlets (for example, `Get-Item`, `Set-Item`, etc.) such that the data in your data store can be treated like files and directories are treated when navigating a file system.</span></span> <span data-ttu-id="fc20f-107">有关提供程序和驱动器以及 Windows PowerShell 中的内置提供程序的详细信息，请参阅 [about_Providers](/powershell/module/microsoft.powershell.core/about/about_providers)。</span><span class="sxs-lookup"><span data-stu-id="fc20f-107">For more information about providers and drives, and the built-in providers in Windows PowerShell, see [about_Providers](/powershell/module/microsoft.powershell.core/about/about_providers).</span></span>

## <a name="providers-and-drives"></a><span data-ttu-id="fc20f-108">提供商和驱动器</span><span class="sxs-lookup"><span data-stu-id="fc20f-108">Providers and Drives</span></span>

<span data-ttu-id="fc20f-109">提供程序定义用于访问、导航和编辑数据存储区的逻辑，而驱动器则指定数据存储的特定入口点 (或数据存储区的某个部分) 此访问接口定义的类型。</span><span class="sxs-lookup"><span data-stu-id="fc20f-109">A Provider defines the logic that is used to access, navigate, and edit a data store, while a drive specifies a specific entry point to a data store (or a portion of a data store) that is of the type defined by the provider.</span></span> <span data-ttu-id="fc20f-110">例如，注册表提供程序允许访问注册表中的配置单元和密钥，并且 HKLM 和 HKCU 驱动器指定注册表中的相应配置单元。</span><span class="sxs-lookup"><span data-stu-id="fc20f-110">For example, the Registry provider allows you to access hives and keys in a registry, and the HKLM and HKCU drives specify the corresponding hives within the registry.</span></span> <span data-ttu-id="fc20f-111">HKLM 和 HKCU 驱动器都使用注册表提供程序。</span><span class="sxs-lookup"><span data-stu-id="fc20f-111">The HKLM and HKCU drives both use the Registry provider.</span></span>

<span data-ttu-id="fc20f-112">当你编写提供程序时，可以指定默认驱动器-在提供程序可用时自动创建的驱动器。</span><span class="sxs-lookup"><span data-stu-id="fc20f-112">When you write a provider, you can specify default drives-drives that are created automatically when the provider is available.</span></span> <span data-ttu-id="fc20f-113">还定义了一个方法来创建使用该提供程序的新驱动器。</span><span class="sxs-lookup"><span data-stu-id="fc20f-113">You also define a method to create new drives that use that provider.</span></span>

## <a name="type-of-providers"></a><span data-ttu-id="fc20f-114">提供程序的类型</span><span class="sxs-lookup"><span data-stu-id="fc20f-114">Type of Providers</span></span>

<span data-ttu-id="fc20f-115">提供了几种类型的提供程序，每种类型提供不同的功能级别。</span><span class="sxs-lookup"><span data-stu-id="fc20f-115">There are several types of providers, each of which provides a different level of functionality.</span></span> <span data-ttu-id="fc20f-116">提供程序作为从[SessionStateCategory](/dotnet/api/system.management.automation.sessionstatecategory) 
 **CmdletProvider** 类的其中一个子代派生的类来实现。</span><span class="sxs-lookup"><span data-stu-id="fc20f-116">A provider is implemented as a class that derives from one of the descendants of the [System.Management.Automation.SessionStateCategory](/dotnet/api/system.management.automation.sessionstatecategory)
**CmdletProvider** class.</span></span> <span data-ttu-id="fc20f-117">有关不同类型的提供程序的信息，请参阅 [提供程序类型](./provider-types.md)。</span><span class="sxs-lookup"><span data-stu-id="fc20f-117">For information about the different types of providers, see [Provider types](./provider-types.md).</span></span>

## <a name="provider-cmdlets"></a><span data-ttu-id="fc20f-118">提供程序 cmdlet</span><span class="sxs-lookup"><span data-stu-id="fc20f-118">Provider cmdlets</span></span>

<span data-ttu-id="fc20f-119">提供程序可以实现与 cmdlet 相对应的方法，并在该提供程序的驱动器中使用时为这些 cmdlet 创建自定义行为。</span><span class="sxs-lookup"><span data-stu-id="fc20f-119">Providers can implement methods that correspond to cmdlets, creating custom behaviors for those cmdlets when used in a drive for that provider.</span></span> <span data-ttu-id="fc20f-120">根据提供程序的类型，有不同的 cmdlet 集可用。</span><span class="sxs-lookup"><span data-stu-id="fc20f-120">Depending on the type of provider, different sets of cmdlets are available.</span></span> <span data-ttu-id="fc20f-121">有关提供程序中可供自定义的 cmdlet 的完整列表，请参阅 [提供程序 cmdlet](./provider-cmdlets.md)。</span><span class="sxs-lookup"><span data-stu-id="fc20f-121">For a complete list of the cmdlets available for customization in providers, see [Provider cmdlets](./provider-cmdlets.md).</span></span>

## <a name="provider-paths"></a><span data-ttu-id="fc20f-122">提供程序路径</span><span class="sxs-lookup"><span data-stu-id="fc20f-122">Provider paths</span></span>

<span data-ttu-id="fc20f-123">用户浏览提供商驱动器，如文件系统。</span><span class="sxs-lookup"><span data-stu-id="fc20f-123">Users navigate provider drives like file systems.</span></span> <span data-ttu-id="fc20f-124">因此，它们期望路径的语法对应于文件系统导航中使用的路径。</span><span class="sxs-lookup"><span data-stu-id="fc20f-124">Because of this, they expect the syntax of paths to correspond to the paths used in file system navigation.</span></span> <span data-ttu-id="fc20f-125">用户运行提供程序 cmdlet 时，将指定要访问的项的路径。</span><span class="sxs-lookup"><span data-stu-id="fc20f-125">When a user runs a provider cmdlet, they specify a path to the item to be accessed.</span></span> <span data-ttu-id="fc20f-126">可以通过多种方式解释指定的路径。</span><span class="sxs-lookup"><span data-stu-id="fc20f-126">The path that is specified can be interpreted in several ways.</span></span> <span data-ttu-id="fc20f-127">提供程序应支持以下一个或多个路径类型。</span><span class="sxs-lookup"><span data-stu-id="fc20f-127">A provider should support one or more of the following path types.</span></span>

### <a name="drive-qualified-paths"></a><span data-ttu-id="fc20f-128">驱动器限定路径</span><span class="sxs-lookup"><span data-stu-id="fc20f-128">Drive-qualified paths</span></span>

<span data-ttu-id="fc20f-129">驱动器限定路径是项名称、项所在的容器和子容器的组合，以及通过其访问该项的 Windows PowerShell 驱动器。</span><span class="sxs-lookup"><span data-stu-id="fc20f-129">A drive-qualified path is a combination of the item name, the container and subcontainers in which the item is located, and the Windows PowerShell drive through which the item is accessed.</span></span> <span data-ttu-id="fc20f-130"> (驱动器由用于访问数据存储的提供程序定义。</span><span class="sxs-lookup"><span data-stu-id="fc20f-130">(Drives are defined by the provider that is used to access the data store.</span></span> <span data-ttu-id="fc20f-131">此路径以驱动器名称开头，后面跟一个冒号 (： ) 。</span><span class="sxs-lookup"><span data-stu-id="fc20f-131">This path starts with the drive name followed by a colon (:).</span></span> <span data-ttu-id="fc20f-132">例如： `get-childitem C:`</span><span class="sxs-lookup"><span data-stu-id="fc20f-132">For example: `get-childitem C:`</span></span>

### <a name="provider-qualified-paths"></a><span data-ttu-id="fc20f-133">提供程序限定路径</span><span class="sxs-lookup"><span data-stu-id="fc20f-133">Provider-qualified paths</span></span>

<span data-ttu-id="fc20f-134">若要允许 Windows PowerShell 引擎初始化和取消初始化提供程序，提供程序必须支持提供程序限定的路径。</span><span class="sxs-lookup"><span data-stu-id="fc20f-134">To allow the Windows PowerShell engine to initialize and uninitialize your provider, the provider must support a provider-qualified path.</span></span> <span data-ttu-id="fc20f-135">例如，用户可以初始化和取消初始化 FileSystem 提供程序，因为它定义以下提供程序限定路径： `FileSystem::\\uncshare\abc\bar` 。</span><span class="sxs-lookup"><span data-stu-id="fc20f-135">For example, the user can initialize and uninitialize the FileSystem provider because it defines the following provider-qualified path: `FileSystem::\\uncshare\abc\bar`.</span></span>

### <a name="provider-direct-paths"></a><span data-ttu-id="fc20f-136">提供程序-直接路径</span><span class="sxs-lookup"><span data-stu-id="fc20f-136">Provider-direct paths</span></span>

<span data-ttu-id="fc20f-137">若要允许远程访问你的 Windows PowerShell 提供程序，它应该支持直接传递到 Windows PowerShell 提供程序以获取当前位置的提供程序直接路径。</span><span class="sxs-lookup"><span data-stu-id="fc20f-137">To allow remote access to your Windows PowerShell provider, it should support a provider-direct path to pass directly to the Windows PowerShell provider for the current location.</span></span> <span data-ttu-id="fc20f-138">例如，Windows PowerShell 提供程序的注册表可以用作 `\\server\regkeypath` 提供程序-直接路径。</span><span class="sxs-lookup"><span data-stu-id="fc20f-138">For example, the registry Windows PowerShell provider can use `\\server\regkeypath` as a provider-direct path.</span></span>

### <a name="provider-internal-paths"></a><span data-ttu-id="fc20f-139">提供程序-内部路径</span><span class="sxs-lookup"><span data-stu-id="fc20f-139">Provider-internal paths</span></span>

<span data-ttu-id="fc20f-140">若要允许提供程序 cmdlet 使用非 Windows PowerShell 应用程序编程接口访问数据 (Api) ，你的 Windows PowerShell 提供程序应支持提供程序内部路径。</span><span class="sxs-lookup"><span data-stu-id="fc20f-140">To allow the provider cmdlet to access data using non-Windows PowerShell application programming interfaces (APIs), your Windows PowerShell provider should support a provider-internal path.</span></span> <span data-ttu-id="fc20f-141">此路径在提供程序限定的路径中的 "：：" 后指示。</span><span class="sxs-lookup"><span data-stu-id="fc20f-141">This path is indicated after the "::" in the provider-qualified path.</span></span> <span data-ttu-id="fc20f-142">例如，filesystem Windows PowerShell 提供程序的提供程序内部路径为 `\\uncshare\abc\bar` 。</span><span class="sxs-lookup"><span data-stu-id="fc20f-142">For example, the provider-internal path for the filesystem Windows PowerShell provider is `\\uncshare\abc\bar`.</span></span>

## <a name="overriding-cmdlet-parameters"></a><span data-ttu-id="fc20f-143">重写 cmdlet 参数</span><span class="sxs-lookup"><span data-stu-id="fc20f-143">Overriding cmdlet parameters</span></span>

<span data-ttu-id="fc20f-144">某些特定于提供程序的 cmdlet 的行为可由提供程序重写。</span><span class="sxs-lookup"><span data-stu-id="fc20f-144">The behavior of some provider-specific cmdlets can be overridden by a provider.</span></span> <span data-ttu-id="fc20f-145">有关可以重写的参数的列表，以及如何在提供程序类中重写这些参数的列表，请参阅 [提供程序 cmdlet 参数](./provider-cmdlet-parameters.md)</span><span class="sxs-lookup"><span data-stu-id="fc20f-145">For a list of parameters that can be overridden, and how to override them in your provider class, see [Provider cmdlet parameters](./provider-cmdlet-parameters.md)</span></span>

## <a name="dynamic-parameters"></a><span data-ttu-id="fc20f-146">动态参数</span><span class="sxs-lookup"><span data-stu-id="fc20f-146">Dynamic parameters</span></span>

<span data-ttu-id="fc20f-147">当用户为 cmdlet 的一个静态参数指定特定值时，提供程序可以定义添加到提供程序 cmdlet 的动态参数。</span><span class="sxs-lookup"><span data-stu-id="fc20f-147">Providers can define dynamic parameters that are added to a provider cmdlet when the user specifies a certain value for one of the static parameters of the cmdlet.</span></span> <span data-ttu-id="fc20f-148">提供程序通过实现一个或多个动态参数方法来实现此功能。</span><span class="sxs-lookup"><span data-stu-id="fc20f-148">A provider does this by implementing one or more dynamic parameter methods.</span></span> <span data-ttu-id="fc20f-149">有关可用于添加动态参数的 cmdlet 参数的列表，以及用于实现它们的方法，请参阅 [提供程序 cmdlet 动态参数](./provider-cmdlet-dynamic-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="fc20f-149">For a list of cmdlet parameters that can be used to add dynamic parameter, and the methods used to implement them, see [Provider cmdlet dynamic parameters](./provider-cmdlet-dynamic-parameters.md).</span></span>

## <a name="provider-capabilities"></a><span data-ttu-id="fc20f-150">提供程序功能</span><span class="sxs-lookup"><span data-stu-id="fc20f-150">Provider capabilities</span></span>

<span data-ttu-id="fc20f-151">[Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)枚举定义了提供程序可支持的多个功能。</span><span class="sxs-lookup"><span data-stu-id="fc20f-151">The [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeration defines a number of capabilities that providers can support.</span></span> <span data-ttu-id="fc20f-152">其中包括使用通配符、筛选项和支持事务的功能。</span><span class="sxs-lookup"><span data-stu-id="fc20f-152">These include the ability to use wildcards, filter items, and support transactions.</span></span> <span data-ttu-id="fc20f-153">若要为提供程序指定功能，请添加[Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)枚举值的列表，并将其与逻辑操作组合在一起，并将其与 `OR` [Cmdletproviderattribute. Providercapabilities \*](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute.ProviderCapabilities)属性组合在一起， (提供程序类的特性的) 属性的第二个参数。） [](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) 。</span><span class="sxs-lookup"><span data-stu-id="fc20f-153">To specify capabilities for a provider, add a list of values of the [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeration, combined with a logical `OR` operation, as the [System.Management.Automation.Provider.Cmdletproviderattribute.Providercapabilities\*](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute.ProviderCapabilities) property (the second parameter of the attribute) of the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) attribute for your provider class.</span></span> <span data-ttu-id="fc20f-154">例如，下面的特性指定提供程序支持[Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) 
 **ShouldProcess** 和[Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) 
 **事务** 功能的访问器的支持程序管理器。</span><span class="sxs-lookup"><span data-stu-id="fc20f-154">For example, the following attribute specifies that the provider supports the [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)
**ShouldProcess** and [System.Management.Automation.Provider.ProviderCapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)
**Transactions** capabilities.</span></span>

```csharp
[CmdletProvider(RegistryProvider.ProviderName, ProviderCapabilities.ShouldProcess | ProviderCapabilities.Transactions)]

```

## <a name="provider-cmdlet-help"></a><span data-ttu-id="fc20f-155">提供程序 cmdlet 帮助</span><span class="sxs-lookup"><span data-stu-id="fc20f-155">Provider cmdlet help</span></span>

<span data-ttu-id="fc20f-156">编写提供程序时，可以为所支持的提供程序 cmdlet 实现自己的帮助。</span><span class="sxs-lookup"><span data-stu-id="fc20f-156">When writing a provider, you can implement your own Help for the provider cmdlets that you support.</span></span>
<span data-ttu-id="fc20f-157">这包括针对每个提供程序 cmdlet 的单个帮助主题，或者针对提供程序 cmdlet 根据动态参数使用方式不同的情况的多个帮助主题版本。</span><span class="sxs-lookup"><span data-stu-id="fc20f-157">This includes a single help topic for each provider cmdlet or multiple versions of a help topic for cases where the provider cmdlet acts differently based on the use of dynamic parameters.</span></span> <span data-ttu-id="fc20f-158">若要支持特定于提供程序 cmdlet 的帮助，提供程序必须实现 [Icmdletprovidersupportshelp](/dotnet/api/System.Management.Automation.Provider.ICmdletProviderSupportsHelp) 接口。</span><span class="sxs-lookup"><span data-stu-id="fc20f-158">To support provider cmdlet-specific help, your provider must implement the [System.Management.Automation.Provider.Icmdletprovidersupportshelp](/dotnet/api/System.Management.Automation.Provider.ICmdletProviderSupportsHelp) interface.</span></span>

<span data-ttu-id="fc20f-159">Windows PowerShell 引擎调用 [Icmdletprovidersupportshelp. Gethelpmaml \*](/dotnet/api/System.Management.Automation.Provider.ICmdletProviderSupportsHelp.GetHelpMaml) 方法，以显示提供程序 Cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="fc20f-159">The Windows PowerShell engine calls the [System.Management.Automation.Provider.Icmdletprovidersupportshelp.Gethelpmaml\*](/dotnet/api/System.Management.Automation.Provider.ICmdletProviderSupportsHelp.GetHelpMaml) method to display the Help topic for your provider cmdlets.</span></span> <span data-ttu-id="fc20f-160">引擎提供用户在运行 cmdlet 时指定的 cmdlet 的名称 `Get-Help` ，以及用户的当前路径。</span><span class="sxs-lookup"><span data-stu-id="fc20f-160">The engine provides the name of the cmdlet that the user specified when running the `Get-Help` cmdlet and the current path of the user.</span></span>
<span data-ttu-id="fc20f-161">如果提供程序为不同的驱动器实现相同的提供程序 cmdlet 的不同版本，则当前路径是必需的。</span><span class="sxs-lookup"><span data-stu-id="fc20f-161">The current path is required if your provider implements different versions of the same provider cmdlet for different drives.</span></span> <span data-ttu-id="fc20f-162">此方法必须返回一个字符串，其中包含用于 cmdlet 的 XML 帮助。</span><span class="sxs-lookup"><span data-stu-id="fc20f-162">The method must return a string that contains the XML for the cmdlet Help.</span></span>

<span data-ttu-id="fc20f-163">使用 PSMAML XML 编写帮助文件的内容。</span><span class="sxs-lookup"><span data-stu-id="fc20f-163">The content for the Help file is written using PSMAML XML.</span></span> <span data-ttu-id="fc20f-164">这是用于写入独立 cmdlet 的帮助内容的相同 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="fc20f-164">This is the same XML schema that is used for writing Help content for stand-alone cmdlets.</span></span> <span data-ttu-id="fc20f-165">在元素下，将自定义 cmdlet 帮助的内容添加到提供程序的帮助文件 `CmdletHelpPaths` 。</span><span class="sxs-lookup"><span data-stu-id="fc20f-165">Add the content for your custom cmdlet Help to the Help file for your provider under the `CmdletHelpPaths` element.</span></span> <span data-ttu-id="fc20f-166">下面的示例演示 `command` 单个提供程序 cmdlet 的元素，并演示如何指定提供程序的提供程序 cmdlet 的名称。</span><span class="sxs-lookup"><span data-stu-id="fc20f-166">The following example shows the `command` element for a single provider cmdlet, and it shows how you specify the name of the provider cmdlet that your provider.</span></span> <span data-ttu-id="fc20f-167">支持</span><span class="sxs-lookup"><span data-stu-id="fc20f-167">supports</span></span>

```xml
<CmdletHelpPaths>
  <command:command>
    <command:details>
      <command:name>ProviderCmdletName</command:name>
      <command:verb>Verb</command:verb>
      <command:noun>Noun</command:noun>
    <command:details>
  </command:command>
<CmdletHelpPath>
```

## <a name="see-also"></a><span data-ttu-id="fc20f-168">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc20f-168">See Also</span></span>

[<span data-ttu-id="fc20f-169">Windows PowerShell 提供程序功能</span><span class="sxs-lookup"><span data-stu-id="fc20f-169">Windows PowerShell Provider Functionality</span></span>](./provider-types.md)

[<span data-ttu-id="fc20f-170">提供程序 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="fc20f-170">Provider Cmdlets</span></span>](./provider-cmdlets.md)

[<span data-ttu-id="fc20f-171">编写 Windows PowerShell 提供程序</span><span class="sxs-lookup"><span data-stu-id="fc20f-171">Writing a Windows PowerShell Provider</span></span>](./writing-a-windows-powershell-provider.md)
