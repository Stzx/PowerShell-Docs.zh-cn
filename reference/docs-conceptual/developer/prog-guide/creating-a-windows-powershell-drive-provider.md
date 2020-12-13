---
ms.date: 09/13/2016
ms.topic: reference
title: 创建 Windows PowerShell 驱动器提供程序
description: 创建 Windows PowerShell 驱动器提供程序
ms.openlocfilehash: 639518fce27d941b7529b091364c5905c91a5c0c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92663032"
---
# <a name="creating-a-windows-powershell-drive-provider"></a><span data-ttu-id="c5414-103">创建 Windows PowerShell 驱动器提供程序</span><span class="sxs-lookup"><span data-stu-id="c5414-103">Creating a Windows PowerShell Drive Provider</span></span>

<span data-ttu-id="c5414-104">本主题介绍如何创建 Windows PowerShell 驱动器提供程序，该提供程序通过 Windows PowerShell 驱动器提供访问数据存储区的方式。</span><span class="sxs-lookup"><span data-stu-id="c5414-104">This topic describes how to create a Windows PowerShell drive provider that provides a way to access a data store through a Windows PowerShell drive.</span></span> <span data-ttu-id="c5414-105">这种类型的提供程序也称为 Windows PowerShell 驱动器提供程序。</span><span class="sxs-lookup"><span data-stu-id="c5414-105">This type of provider is also referred to as Windows PowerShell drive providers.</span></span> <span data-ttu-id="c5414-106">提供程序使用的 Windows PowerShell 驱动器提供连接到数据存储的方法。</span><span class="sxs-lookup"><span data-stu-id="c5414-106">The Windows PowerShell drives used by the provider provide the means to connect to the data store.</span></span>

<span data-ttu-id="c5414-107">此处所述的 Windows PowerShell 驱动器提供程序提供对 Microsoft Access 数据库的访问权限。</span><span class="sxs-lookup"><span data-stu-id="c5414-107">The Windows PowerShell drive provider described here provides access to a Microsoft Access database.</span></span>
<span data-ttu-id="c5414-108">对于此提供程序，Windows PowerShell 驱动器表示数据库 (可以将任意数量的驱动器添加到驱动器提供程序) ，驱动器的顶层容器表示数据库中的表，而容器中的项表示表中的行。</span><span class="sxs-lookup"><span data-stu-id="c5414-108">For this provider, the Windows PowerShell drive represents the database (it is possible to add any number of drives to a drive provider), the top-level containers of the drive represent the tables in the database, and the items of the containers represent the rows in the tables.</span></span>

## <a name="defining-the-windows-powershell-provider-class"></a><span data-ttu-id="c5414-109">定义 Windows PowerShell 提供程序类</span><span class="sxs-lookup"><span data-stu-id="c5414-109">Defining the Windows PowerShell Provider Class</span></span>

<span data-ttu-id="c5414-110">你的驱动器提供程序必须定义一个从 [Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) 基类派生的 .net 类。</span><span class="sxs-lookup"><span data-stu-id="c5414-110">Your drive provider must define a .NET class that derives from the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) base class.</span></span> <span data-ttu-id="c5414-111">下面是此驱动器提供程序的类定义：</span><span class="sxs-lookup"><span data-stu-id="c5414-111">Here is the class definition for this drive provider:</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs" range="29-30":::

<span data-ttu-id="c5414-112">请注意，在此示例中， [Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) 属性指定提供程序的用户友好名称，以及提供程序在命令处理过程中向 windows powershell 运行时公开的 windows powershell 特定功能。</span><span class="sxs-lookup"><span data-stu-id="c5414-112">Notice that in this example, the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) attribute specifies a user-friendly name for the provider and the Windows PowerShell specific capabilities that the provider exposes to the Windows PowerShell runtime during command processing.</span></span>
<span data-ttu-id="c5414-113">提供程序功能的可能值是由 [Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) 枚举定义的。</span><span class="sxs-lookup"><span data-stu-id="c5414-113">The possible values for the provider capabilities are defined by the [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeration.</span></span> <span data-ttu-id="c5414-114">此驱动器提供程序不支持其中任何一种功能。</span><span class="sxs-lookup"><span data-stu-id="c5414-114">This drive provider does not support any of these capabilities.</span></span>

## <a name="defining-base-functionality"></a><span data-ttu-id="c5414-115">定义基本功能</span><span class="sxs-lookup"><span data-stu-id="c5414-115">Defining Base Functionality</span></span>

<span data-ttu-id="c5414-116">如 [设计你的 Windows PowerShell 提供程序](./designing-your-windows-powershell-provider.md)中所述， [Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) 类派生自 [Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) 基类，此类定义初始化和取消初始化提供程序所需的方法。</span><span class="sxs-lookup"><span data-stu-id="c5414-116">As described in [Design Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md), the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class derives from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) base class that defines the methods needed for initializing and uninitializing the provider.</span></span> <span data-ttu-id="c5414-117">若要实现添加特定于会话的初始化信息以及释放提供程序所用资源的功能，请参阅 [创建基本 Windows PowerShell 提供程序](./creating-a-basic-windows-powershell-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="c5414-117">To implement functionality for adding session-specific initialization information and for releasing resources that are used by the provider, see [Creating a Basic Windows PowerShell Provider](./creating-a-basic-windows-powershell-provider.md).</span></span>
<span data-ttu-id="c5414-118">但是，大多数提供程序 (包括此处所述的提供程序) 可以使用 Windows PowerShell 提供的此功能的默认实现。</span><span class="sxs-lookup"><span data-stu-id="c5414-118">However, most providers (including the provider described here) can use the default implementation of this functionality that is provided by Windows PowerShell.</span></span>

## <a name="creating-drive-state-information"></a><span data-ttu-id="c5414-119">正在创建驱动器状态信息</span><span class="sxs-lookup"><span data-stu-id="c5414-119">Creating Drive State Information</span></span>

<span data-ttu-id="c5414-120">所有 Windows PowerShell 提供程序都被视为无状态，这意味着驱动器提供程序需要创建 Windows PowerShell 运行时在调用提供程序时所需的任何状态信息。</span><span class="sxs-lookup"><span data-stu-id="c5414-120">All Windows PowerShell providers are considered stateless, which means that your drive provider needs to create any state information that is needed by the Windows PowerShell runtime when it calls your provider.</span></span>

<span data-ttu-id="c5414-121">对于此驱动器提供程序，状态信息包括与数据库的连接，并将其保存为驱动器信息的一部分。</span><span class="sxs-lookup"><span data-stu-id="c5414-121">For this drive provider, state information includes the connection to the database that is kept as part of the drive information.</span></span> <span data-ttu-id="c5414-122">下面的代码演示如何将此信息存储在描述驱动器 [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) 对象中：</span><span class="sxs-lookup"><span data-stu-id="c5414-122">Here is code that shows how this information is stored in the [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) object that describes the drive:</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs" range="130-151":::

## <a name="creating-a-drive"></a><span data-ttu-id="c5414-123">创建驱动器</span><span class="sxs-lookup"><span data-stu-id="c5414-123">Creating a Drive</span></span>

<span data-ttu-id="c5414-124">若要允许 Windows PowerShell 运行时创建驱动器，驱动器提供程序必须实现 [Drivecmdletprovider. Newdrive \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) 方法。</span><span class="sxs-lookup"><span data-stu-id="c5414-124">To allow the Windows PowerShell runtime to create a drive, the drive provider must implement the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) method.</span></span> <span data-ttu-id="c5414-125">下面的代码演示了此驱动器提供程序的 [Drivecmdletprovider. Newdrive \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) 方法的实现：</span><span class="sxs-lookup"><span data-stu-id="c5414-125">The following code shows the implementation of the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) method for this drive provider:</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs" range="42-84":::

<span data-ttu-id="c5414-126">重写此方法应执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c5414-126">Your override of this method should do the following:</span></span>

- <span data-ttu-id="c5414-127">验证 [System.Management.Automation.PSDriveinfo。Root \*](/dotnet/api/System.Management.Automation.PSDriveInfo.Root) 成员存在，可以建立与数据存储的连接。</span><span class="sxs-lookup"><span data-stu-id="c5414-127">Verify that the [System.Management.Automation.PSDriveinfo.Root\*](/dotnet/api/System.Management.Automation.PSDriveInfo.Root) member exists and that a connection to the data store can be made.</span></span>
- <span data-ttu-id="c5414-128">创建驱动器并填充连接成员，以支持 `New-PSDrive` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c5414-128">Create a drive and populate the connection member, in support of the `New-PSDrive` cmdlet.</span></span>
- <span data-ttu-id="c5414-129">验证建议的驱动器的 [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) 对象。</span><span class="sxs-lookup"><span data-stu-id="c5414-129">Validate the [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) object for the proposed drive.</span></span>
- <span data-ttu-id="c5414-130">修改使用任何所需性能或可靠性信息描述驱动器的 [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) 对象，或使用驱动器为调用方提供额外的数据。</span><span class="sxs-lookup"><span data-stu-id="c5414-130">Modify the [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) object that describes the drive with any required performance or reliability information, or provide extra data for callers using the drive.</span></span>
- <span data-ttu-id="c5414-131">使用 [Cmdletprovider. WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError) 方法处理失败，然后再返回 `null` 。</span><span class="sxs-lookup"><span data-stu-id="c5414-131">Handle failures using the [System.Management.Automation.Provider.Cmdletprovider.WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError) method and then return `null`.</span></span>

  <span data-ttu-id="c5414-132">此方法返回传递给方法的驱动器信息或其特定于提供程序的版本。</span><span class="sxs-lookup"><span data-stu-id="c5414-132">This method returns either the drive information that was passed to the method or a provider-specific version of it.</span></span>

## <a name="attaching-dynamic-parameters-to-newdrive"></a><span data-ttu-id="c5414-133">将动态参数附加到 NewDrive</span><span class="sxs-lookup"><span data-stu-id="c5414-133">Attaching Dynamic Parameters to NewDrive</span></span>

<span data-ttu-id="c5414-134">`New-PSDrive`驱动器提供商支持的 cmdlet 可能需要其他参数。</span><span class="sxs-lookup"><span data-stu-id="c5414-134">The `New-PSDrive` cmdlet supported by your drive provider might require additional parameters.</span></span> <span data-ttu-id="c5414-135">若要将这些动态参数附加到 cmdlet，提供程序将实现 [Drivecmdletprovider. Newdrivedynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) 方法。</span><span class="sxs-lookup"><span data-stu-id="c5414-135">To attach these dynamic parameters to the cmdlet, the provider implements the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrivedynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) method.</span></span> <span data-ttu-id="c5414-136">此方法返回一个对象，该对象具有与 cmdlet 类或 [Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) 对象类似的分析特性的属性和字段。</span><span class="sxs-lookup"><span data-stu-id="c5414-136">This method returns an object that has properties and fields with parsing attributes similar to a cmdlet class or a [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) object.</span></span>

<span data-ttu-id="c5414-137">此驱动器提供程序不重写此方法。</span><span class="sxs-lookup"><span data-stu-id="c5414-137">This drive provider does not override this method.</span></span> <span data-ttu-id="c5414-138">但是，以下代码显示了此方法的默认实现：</span><span class="sxs-lookup"><span data-stu-id="c5414-138">However, the following code shows the default implementation of this method:</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidernewdrivedynamicparameters](Msh_samplestestcmdlets#testprovidernewdrivedynamicparameters)]  -->

## <a name="removing-a-drive"></a><span data-ttu-id="c5414-139">删除驱动器</span><span class="sxs-lookup"><span data-stu-id="c5414-139">Removing a Drive</span></span>

<span data-ttu-id="c5414-140">若要关闭数据库连接，驱动器提供程序必须实现 [Drivecmdletprovider. Removedrive \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) 方法。</span><span class="sxs-lookup"><span data-stu-id="c5414-140">To close the database connection, the drive provider must implement the [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) method.</span></span> <span data-ttu-id="c5414-141">此方法在清理任何提供程序特定的信息后关闭到驱动器的连接。</span><span class="sxs-lookup"><span data-stu-id="c5414-141">This method closes the connection to the drive after cleaning up any provider-specific information.</span></span>

<span data-ttu-id="c5414-142">下面的代码演示了此驱动器提供程序的 [Drivecmdletprovider. Removedrive \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) 方法的实现：</span><span class="sxs-lookup"><span data-stu-id="c5414-142">The following code shows the implementation of the [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) method for this drive provider:</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs" range="91-116":::

<span data-ttu-id="c5414-143">如果可以删除驱动器，方法应返回通过参数传递给方法的信息 `drive` 。</span><span class="sxs-lookup"><span data-stu-id="c5414-143">If the drive can be removed, the method should return the information passed to the method through the `drive` parameter.</span></span> <span data-ttu-id="c5414-144">如果无法删除驱动器，方法应写入异常，然后返回 `null` 。</span><span class="sxs-lookup"><span data-stu-id="c5414-144">If the drive cannot be removed, the method should write an exception and then return `null`.</span></span> <span data-ttu-id="c5414-145">如果提供程序未重写此方法，则此方法的默认实现只返回作为输入传递的驱动器信息。</span><span class="sxs-lookup"><span data-stu-id="c5414-145">If your provider does not override this method, the default implementation of this method just returns the drive information passed as input.</span></span>

## <a name="initializing-default-drives"></a><span data-ttu-id="c5414-146">正在初始化默认驱动器</span><span class="sxs-lookup"><span data-stu-id="c5414-146">Initializing Default Drives</span></span>

<span data-ttu-id="c5414-147">驱动器提供程序实现 [System.Management.Automation.Provider.Drivecmdletprovider.Initializedefaultdrives \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) 方法来装入驱动器。</span><span class="sxs-lookup"><span data-stu-id="c5414-147">Your drive provider implements the [System.Management.Automation.Provider.Drivecmdletprovider.Initializedefaultdrives\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) method to mount drives.</span></span> <span data-ttu-id="c5414-148">例如，如果计算机加入到域中，Active Directory 提供程序可能会为默认命名上下文装载驱动器。</span><span class="sxs-lookup"><span data-stu-id="c5414-148">For example, the Active Directory provider might mount a drive for the default naming context if the computer is joined to a domain.</span></span>

<span data-ttu-id="c5414-149">此方法返回有关已初始化驱动器的驱动器信息的集合，或空集合。</span><span class="sxs-lookup"><span data-stu-id="c5414-149">This method returns a collection of drive information about the initialized drives, or an empty collection.</span></span> <span data-ttu-id="c5414-150">对此方法的调用是在 Windows PowerShell 运行时调用 [Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) 方法以初始化提供程序后进行的。</span><span class="sxs-lookup"><span data-stu-id="c5414-150">The call to this method is made after the Windows PowerShell runtime calls the [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) method to initialize the provider.</span></span>

<span data-ttu-id="c5414-151">此驱动器提供程序不替代 [System.Management.Automation.Provider.Drivecmdletprovider.Initializedefaultdrives \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) 方法。</span><span class="sxs-lookup"><span data-stu-id="c5414-151">This drive provider does not override the [System.Management.Automation.Provider.Drivecmdletprovider.Initializedefaultdrives\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives) method.</span></span> <span data-ttu-id="c5414-152">但是，以下代码演示了返回空驱动器集合的默认实现：</span><span class="sxs-lookup"><span data-stu-id="c5414-152">However, the following code shows the default implementation, which returns an empty drive collection:</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderinitializedefaultdrives](Msh_samplestestcmdlets#testproviderinitializedefaultdrives)]  -->

#### <a name="things-to-remember-about-implementing-initializedefaultdrives"></a><span data-ttu-id="c5414-153">有关实现 InitializeDefaultDrives 的注意事项</span><span class="sxs-lookup"><span data-stu-id="c5414-153">Things to Remember About Implementing InitializeDefaultDrives</span></span>

<span data-ttu-id="c5414-154">所有驱动器提供商都应装载根驱动器，以帮助用户发现。</span><span class="sxs-lookup"><span data-stu-id="c5414-154">All drive providers should mount a root drive to help the user with discoverability.</span></span> <span data-ttu-id="c5414-155">根驱动器可能会列出用作其他已装入驱动器的根的位置。</span><span class="sxs-lookup"><span data-stu-id="c5414-155">The root drive might list locations that serve as roots for other mounted drives.</span></span> <span data-ttu-id="c5414-156">例如，Active Directory 提供程序可能会创建一个驱动器，该驱动器列出根分布式系统环境的属性中找到的命名上下文 `namingContext` (DSE) 。</span><span class="sxs-lookup"><span data-stu-id="c5414-156">For example, the Active Directory provider might create a drive that lists the naming contexts found in the `namingContext` attributes on the root Distributed System Environment (DSE).</span></span> <span data-ttu-id="c5414-157">这有助于用户发现其他驱动器的装入点。</span><span class="sxs-lookup"><span data-stu-id="c5414-157">This helps users discover mount points for other drives.</span></span>

## <a name="code-sample"></a><span data-ttu-id="c5414-158">代码示例</span><span class="sxs-lookup"><span data-stu-id="c5414-158">Code Sample</span></span>

<span data-ttu-id="c5414-159">有关完整的示例代码，请参阅 [AccessDbProviderSample02 代码示例](./accessdbprovidersample02-code-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="c5414-159">For complete sample code, see [AccessDbProviderSample02 Code Sample](./accessdbprovidersample02-code-sample.md).</span></span>

## <a name="testing-the-windows-powershell-drive-provider"></a><span data-ttu-id="c5414-160">测试 Windows PowerShell 驱动器提供程序</span><span class="sxs-lookup"><span data-stu-id="c5414-160">Testing the Windows PowerShell Drive Provider</span></span>

<span data-ttu-id="c5414-161">向 Windows powershell 注册 Windows PowerShell 提供程序后，可以通过在命令行上运行支持的 cmdlet （包括派生提供的任何 cmdlet）来测试 Windows PowerShell 提供程序。</span><span class="sxs-lookup"><span data-stu-id="c5414-161">When your Windows PowerShell provider has been registered with Windows PowerShell, you can test it by running the supported cmdlets on the command line, including any cmdlets made available by derivation.</span></span> <span data-ttu-id="c5414-162">让我们测试示例驱动器提供程序。</span><span class="sxs-lookup"><span data-stu-id="c5414-162">Let's test the sample drive provider.</span></span>

1. <span data-ttu-id="c5414-163">运行 `Get-PSProvider` cmdlet 以检索提供程序列表，以确保存在 AccessDB 驱动器提供程序：</span><span class="sxs-lookup"><span data-stu-id="c5414-163">Run the `Get-PSProvider` cmdlet to retrieve the list of providers to ensure that the AccessDB drive provider is present:</span></span>

   <span data-ttu-id="c5414-164">**PS> `Get-PSProvider`**</span><span class="sxs-lookup"><span data-stu-id="c5414-164">**PS> `Get-PSProvider`**</span></span>

   <span data-ttu-id="c5414-165">随即显示以下输出：</span><span class="sxs-lookup"><span data-stu-id="c5414-165">The following output appears:</span></span>

   ```Output
   Name                 Capabilities                  Drives
   ----                 ------------                  ------
   AccessDB             None                          {}
   Alias                ShouldProcess                 {Alias}
   Environment          ShouldProcess                 {Env}
   FileSystem           Filter, ShouldProcess         {C, Z}
   Function             ShouldProcess                 {function}
   Registry             ShouldProcess                 {HKLM, HKCU}
   ```

2. <span data-ttu-id="c5414-166">通过访问操作系统的 "**管理工具**" 的 "**数据源**" 部分，确保数据库的数据库服务器名称 (DSN) 存在。</span><span class="sxs-lookup"><span data-stu-id="c5414-166">Ensure that a database server name (DSN) exists for the database by accessing the **Data Sources** portion of the **Administrative Tools** for the operating system.</span></span> <span data-ttu-id="c5414-167">在 " **用户 DSN** " 表中，双击 " **MS Access 数据库** " 并添加驱动器路径 `C:\ps\northwind.mdb` 。</span><span class="sxs-lookup"><span data-stu-id="c5414-167">In the **User DSN** table, double-click **MS Access Database** and add the drive path `C:\ps\northwind.mdb`.</span></span>

3. <span data-ttu-id="c5414-168">使用示例驱动器提供程序创建新驱动器：</span><span class="sxs-lookup"><span data-stu-id="c5414-168">Create a new drive using the sample drive provider:</span></span>

   ```powershell
   new-psdrive -name mydb -root c:\ps\northwind.mdb -psprovider AccessDb`
   ```

   <span data-ttu-id="c5414-169">随即显示以下输出：</span><span class="sxs-lookup"><span data-stu-id="c5414-169">The following output appears:</span></span>

   ```Output
   Name     Provider     Root                   CurrentLocation
   ----     --------     ----                   ---------------
   mydb     AccessDB     c:\ps\northwind.mdb
   ```

4. <span data-ttu-id="c5414-170">验证连接。</span><span class="sxs-lookup"><span data-stu-id="c5414-170">Validate the connection.</span></span> <span data-ttu-id="c5414-171">由于连接被定义为驱动器的成员，因此你可以使用 Get-PDDrive cmdlet 检查连接。</span><span class="sxs-lookup"><span data-stu-id="c5414-171">Because the connection is defined as a member of the drive, you can check it using the Get-PDDrive cmdlet.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c5414-172">用户仍无法作为驱动器与提供程序交互，因为提供程序需要容器功能才能进行该交互。</span><span class="sxs-lookup"><span data-stu-id="c5414-172">The user cannot yet interact with the provider as a drive, as the provider needs container functionality for that interaction.</span></span> <span data-ttu-id="c5414-173">有关详细信息，请参阅 [创建 Windows PowerShell 容器提供程序](./creating-a-windows-powershell-container-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="c5414-173">For more information, see [Creating a Windows PowerShell Container Provider](./creating-a-windows-powershell-container-provider.md).</span></span>

   <span data-ttu-id="c5414-174">**PS> (new-psdrive mydb) 连接**</span><span class="sxs-lookup"><span data-stu-id="c5414-174">**PS> (get-psdrive mydb).connection**</span></span>

   <span data-ttu-id="c5414-175">随即显示以下输出：</span><span class="sxs-lookup"><span data-stu-id="c5414-175">The following output appears:</span></span>

   ```Output
   ConnectionString  : Driver={Microsoft Access Driver (*.mdb)};DBQ=c:\ps\northwind.mdb
   ConnectionTimeout : 15
   Database          : c:\ps\northwind
   DataSource        : ACCESS
   ServerVersion     : 04.00.0000
   Driver            : odbcjt32.dll
   State             : Open
   Site              :
   Container         :
   ```

5. <span data-ttu-id="c5414-176">删除驱动器并退出 shell：</span><span class="sxs-lookup"><span data-stu-id="c5414-176">Remove the drive and exit the shell:</span></span>

   ```powershell
   PS> remove-psdrive mydb
   PS> exit
   ```

## <a name="see-also"></a><span data-ttu-id="c5414-177">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c5414-177">See Also</span></span>

[<span data-ttu-id="c5414-178">创建 Windows PowerShell 提供程序</span><span class="sxs-lookup"><span data-stu-id="c5414-178">Creating Windows PowerShell Providers</span></span>](./how-to-create-a-windows-powershell-provider.md)

[<span data-ttu-id="c5414-179">设计你的 Windows PowerShell 提供程序</span><span class="sxs-lookup"><span data-stu-id="c5414-179">Design Your Windows PowerShell Provider</span></span>](./designing-your-windows-powershell-provider.md)

[<span data-ttu-id="c5414-180">创建基础 Windows PowerShell 提供程序</span><span class="sxs-lookup"><span data-stu-id="c5414-180">Creating a Basic Windows PowerShell Provider</span></span>](./creating-a-basic-windows-powershell-provider.md)
