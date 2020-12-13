---
ms.date: 09/13/2016
ms.topic: reference
title: 创建基础 Windows PowerShell 提供程序
description: 创建基础 Windows PowerShell 提供程序
ms.openlocfilehash: 03b5784fd063b5457fc64d92a32e286e3bf9cce4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647509"
---
# <a name="creating-a-basic-windows-powershell-provider"></a><span data-ttu-id="e78fe-103">创建基础 Windows PowerShell 提供程序</span><span class="sxs-lookup"><span data-stu-id="e78fe-103">Creating a Basic Windows PowerShell Provider</span></span>

<span data-ttu-id="e78fe-104">本主题是学习如何创建 Windows PowerShell 提供程序的起点。</span><span class="sxs-lookup"><span data-stu-id="e78fe-104">This topic is the starting point for learning how to create a Windows PowerShell provider.</span></span> <span data-ttu-id="e78fe-105">此处所述的基本提供程序提供了启动和停止提供程序的方法，但尽管此提供程序不提供访问数据存储或获取或设置数据存储中的数据的方法，但它确实提供了所有提供程序所需的基本功能。</span><span class="sxs-lookup"><span data-stu-id="e78fe-105">The basic provider described here provides methods for starting and stopping the provider, and although this provider does not provide a means to access a data store or to get or set the data in the data store, it does provide the basic functionality that is required by all providers.</span></span>

<span data-ttu-id="e78fe-106">如前所述，此处所述的基本提供程序实现了用于启动和停止提供程序的方法。</span><span class="sxs-lookup"><span data-stu-id="e78fe-106">As mentioned previously, the basic provider described here implements methods for starting and stopping the provider.</span></span> <span data-ttu-id="e78fe-107">Windows PowerShell 运行时调用这些方法来初始化和取消初始化提供程序。</span><span class="sxs-lookup"><span data-stu-id="e78fe-107">The Windows PowerShell runtime calls these methods to initialize and uninitialize the provider.</span></span>

> [!NOTE]
> <span data-ttu-id="e78fe-108">可在 Windows PowerShell 提供的 AccessDBSampleProvider01.cs 文件中找到该提供程序的示例。</span><span class="sxs-lookup"><span data-stu-id="e78fe-108">You can find a sample of this provider in the AccessDBSampleProvider01.cs file provided by Windows PowerShell.</span></span>

## <a name="defining-the-windows-powershell-provider-class"></a><span data-ttu-id="e78fe-109">定义 Windows PowerShell 提供程序类</span><span class="sxs-lookup"><span data-stu-id="e78fe-109">Defining the Windows PowerShell Provider Class</span></span>

<span data-ttu-id="e78fe-110">创建 Windows PowerShell 提供程序的第一步是定义其 .NET 类。</span><span class="sxs-lookup"><span data-stu-id="e78fe-110">The first step in creating a Windows PowerShell provider is to define its .NET class.</span></span> <span data-ttu-id="e78fe-111">此基本提供程序定义了一个名为 `AccessDBProvider` 的类，该类派生自 [Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) 基类。</span><span class="sxs-lookup"><span data-stu-id="e78fe-111">This basic provider defines a class called `AccessDBProvider` that derives from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) base class.</span></span>

<span data-ttu-id="e78fe-112">建议将提供程序类放在 `Providers` API 命名空间的命名空间中，例如，xxx。</span><span class="sxs-lookup"><span data-stu-id="e78fe-112">It is recommended that you place your provider classes in a `Providers` namespace of your API namespace, for example, xxx.PowerShell.Providers.</span></span> <span data-ttu-id="e78fe-113">此提供程序使用 `Microsoft.Samples.PowerShell.Provider` 命名空间，在该命名空间中运行所有 Windows PowerShell 提供程序示例。</span><span class="sxs-lookup"><span data-stu-id="e78fe-113">This provider uses the `Microsoft.Samples.PowerShell.Provider` namespace, in which all Windows PowerShell provider samples run.</span></span>

> [!NOTE]
> <span data-ttu-id="e78fe-114">Windows PowerShell 提供程序的类必须显式标记为公共。</span><span class="sxs-lookup"><span data-stu-id="e78fe-114">The class for a Windows PowerShell provider must be explicitly marked as public.</span></span> <span data-ttu-id="e78fe-115">未标记为 "公共" 的类将默认为内部类，且不会由 Windows PowerShell 运行时找到。</span><span class="sxs-lookup"><span data-stu-id="e78fe-115">Classes not marked as public will default to internal and will not be found by the Windows PowerShell runtime.</span></span>

<span data-ttu-id="e78fe-116">下面是该基本提供程序的类定义：</span><span class="sxs-lookup"><span data-stu-id="e78fe-116">Here is the class definition for this basic provider:</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample01/AccessDBProviderSample01.cs" range="23-24":::

<span data-ttu-id="e78fe-117">在类定义之前，必须用语法 [CmdletProvider ( # A1] 来声明 [Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) 属性，然后才能定义。</span><span class="sxs-lookup"><span data-stu-id="e78fe-117">Right before the class definition, you must declare the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) attribute, with the syntax [CmdletProvider()].</span></span>

<span data-ttu-id="e78fe-118">如有必要，可以设置属性关键字以进一步声明该类。</span><span class="sxs-lookup"><span data-stu-id="e78fe-118">You can set attribute keywords to further declare the class if necessary.</span></span> <span data-ttu-id="e78fe-119">请注意，此处声明的 [Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) 特性包括两个参数。</span><span class="sxs-lookup"><span data-stu-id="e78fe-119">Notice that the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) attribute declared here includes two parameters.</span></span> <span data-ttu-id="e78fe-120">第一个 attribute 参数指定提供程序的默认友好名称，用户可以在以后修改该名称。</span><span class="sxs-lookup"><span data-stu-id="e78fe-120">The first attribute parameter specifies the default-friendly name for the provider, which the user can modify later.</span></span> <span data-ttu-id="e78fe-121">第二个参数指定 Windows PowerShell 定义的功能，提供程序在命令处理过程中将这些功能公开给 Windows PowerShell 运行时。</span><span class="sxs-lookup"><span data-stu-id="e78fe-121">The second parameter specifies the Windows PowerShell-defined capabilities that the provider exposes to the Windows PowerShell runtime during command processing.</span></span> <span data-ttu-id="e78fe-122">提供程序功能的可能值是由 [Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) 枚举定义的。</span><span class="sxs-lookup"><span data-stu-id="e78fe-122">The possible values for the provider capabilities are defined by the [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeration.</span></span> <span data-ttu-id="e78fe-123">因为这是一个基本提供程序，所以它不支持任何功能。</span><span class="sxs-lookup"><span data-stu-id="e78fe-123">Because this is a base provider, it supports no capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="e78fe-124">Windows PowerShell 提供程序的完全限定名称包括在注册提供程序时由 Windows PowerShell 确定的程序集名称和其他属性。</span><span class="sxs-lookup"><span data-stu-id="e78fe-124">The fully qualified name of the Windows PowerShell provider includes the assembly name and other attributes determined by Windows PowerShell upon registration of the provider.</span></span>

## <a name="defining-provider-specific-state-information"></a><span data-ttu-id="e78fe-125">定义 Provider-Specific 状态信息</span><span class="sxs-lookup"><span data-stu-id="e78fe-125">Defining Provider-Specific State Information</span></span>

<span data-ttu-id="e78fe-126">由于 Windows PowerShell 运行时仅根据需要创建提供程序实例，因此 [Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) 基类和所有派生类均被视为无状态。</span><span class="sxs-lookup"><span data-stu-id="e78fe-126">The [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) base class and all derived classes are considered stateless because the Windows PowerShell runtime creates provider instances only as required.</span></span> <span data-ttu-id="e78fe-127">因此，如果提供程序需要完全控制和状态维护特定于提供程序的数据，则必须从 [Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) 类派生一个类。</span><span class="sxs-lookup"><span data-stu-id="e78fe-127">Therefore, if your provider requires full control and state maintenance for provider-specific data, it must derive a class from the [System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) class.</span></span> <span data-ttu-id="e78fe-128">派生类应定义维护状态所需的成员，以便在 Windows PowerShell 运行时调用 [Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) 方法来初始化提供程序时可以访问提供程序特定的数据。</span><span class="sxs-lookup"><span data-stu-id="e78fe-128">Your derived class should define the members necessary to maintain the state so that the provider-specific data can be accessed when the Windows PowerShell runtime calls the [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) method to initialize the provider.</span></span>

<span data-ttu-id="e78fe-129">Windows PowerShell 提供程序也可以维护基于连接的状态。</span><span class="sxs-lookup"><span data-stu-id="e78fe-129">A Windows PowerShell provider can also maintain connection-based state.</span></span> <span data-ttu-id="e78fe-130">有关维护连接状态的详细信息，请参阅 [创建 PowerShell 驱动器提供程序](./creating-a-windows-powershell-drive-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="e78fe-130">For more information about maintaining connection state, see [Creating a PowerShell Drive Provider](./creating-a-windows-powershell-drive-provider.md).</span></span>

## <a name="initializing-the-provider"></a><span data-ttu-id="e78fe-131">正在初始化提供程序</span><span class="sxs-lookup"><span data-stu-id="e78fe-131">Initializing the Provider</span></span>

<span data-ttu-id="e78fe-132">若要初始化该访问接口，Windows powershell 运行时将在启动 Windows PowerShell 时调用 [Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) 方法。</span><span class="sxs-lookup"><span data-stu-id="e78fe-132">To initialize the provider, the Windows PowerShell runtime calls the [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) method when Windows PowerShell is started.</span></span> <span data-ttu-id="e78fe-133">大多数情况下，提供程序可以使用此方法的默认实现，该实现只返回描述提供程序的 [Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) 对象。</span><span class="sxs-lookup"><span data-stu-id="e78fe-133">For the most part, your provider can use the default implementation of this method, which simply returns the [System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) object that describes your provider.</span></span> <span data-ttu-id="e78fe-134">但是，如果你想要添加更多的初始化信息，你应该实现你自己的 [Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) 方法，该方法将返回传递给你的提供程序的已修改版本的 [Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) 对象。</span><span class="sxs-lookup"><span data-stu-id="e78fe-134">However, in the case where you want to add additional initialization information, you should implement your own [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) method that returns a modified version of the [System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) object that is passed to your provider.</span></span> <span data-ttu-id="e78fe-135">通常，此方法应返回传递给它的所提供的 [Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) 对象或包含其他初始化信息的修改后的 [Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) 对象。</span><span class="sxs-lookup"><span data-stu-id="e78fe-135">In general, this method should return the provided [System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) object passed to it or a modified [System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) object that contains other initialization information.</span></span>

<span data-ttu-id="e78fe-136">此基本提供程序不重写此方法。</span><span class="sxs-lookup"><span data-stu-id="e78fe-136">This basic provider does not override this method.</span></span> <span data-ttu-id="e78fe-137">但是，以下代码显示了此方法的默认实现：</span><span class="sxs-lookup"><span data-stu-id="e78fe-137">However, the following code shows the default implementation of this method:</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesaccessdbprov01#accessdbprov01ProviderStart](Msh_samplesaccessdbprov01#accessdbprov01ProviderStart)]  -->

<span data-ttu-id="e78fe-138">提供程序可以维护特定于提供程序的信息的状态，如 [定义特定于提供程序的数据状态](#defining-provider-specific-state-information)中所述。</span><span class="sxs-lookup"><span data-stu-id="e78fe-138">The provider can maintain the state of provider-specific information as described in [Defining Provider-specific Data State](#defining-provider-specific-state-information).</span></span> <span data-ttu-id="e78fe-139">在这种情况下，您的实现必须重写 [Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) 方法才能返回派生类的实例。</span><span class="sxs-lookup"><span data-stu-id="e78fe-139">In this case, your implementation must override the [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) method to return an instance of the derived class.</span></span>

## <a name="start-dynamic-parameters"></a><span data-ttu-id="e78fe-140">启动动态参数</span><span class="sxs-lookup"><span data-stu-id="e78fe-140">Start Dynamic Parameters</span></span>

<span data-ttu-id="e78fe-141">你的 [Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) 方法的提供程序实现可能需要其他参数。</span><span class="sxs-lookup"><span data-stu-id="e78fe-141">Your provider implementation of the [System.Management.Automation.Provider.Cmdletprovider.Start\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) method might require additional parameters.</span></span> <span data-ttu-id="e78fe-142">在这种情况下，提供程序应重写 [Cmdletprovider. Startdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.StartDynamicParameters) 方法，并返回一个对象，该对象具有与 cmdlet 类或 [Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) 对象类似的分析特性的属性和字段。</span><span class="sxs-lookup"><span data-stu-id="e78fe-142">In this case, the provider should override the [System.Management.Automation.Provider.Cmdletprovider.Startdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.StartDynamicParameters) method and return an object that has properties and fields with parsing attributes similar to a cmdlet class or a [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) object.</span></span>

<span data-ttu-id="e78fe-143">此基本提供程序不重写此方法。</span><span class="sxs-lookup"><span data-stu-id="e78fe-143">This basic provider does not override this method.</span></span> <span data-ttu-id="e78fe-144">但是，以下代码显示了此方法的默认实现：</span><span class="sxs-lookup"><span data-stu-id="e78fe-144">However, the following code shows the default implementation of this method:</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesaccessdbprov01#accessdbprov01ProviderDynamicParameters](Msh_samplesaccessdbprov01#accessdbprov01ProviderDynamicParameters)]  -->

## <a name="uninitializing-the-provider"></a><span data-ttu-id="e78fe-145">取消初始化提供程序</span><span class="sxs-lookup"><span data-stu-id="e78fe-145">Uninitializing the Provider</span></span>

<span data-ttu-id="e78fe-146">为了释放 Windows PowerShell 提供程序使用的资源，提供程序应实现其自己的 [Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Stop) 方法。</span><span class="sxs-lookup"><span data-stu-id="e78fe-146">To free resources that the Windows PowerShell provider uses, your provider should implement its own [System.Management.Automation.Provider.Cmdletprovider.Stop\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Stop) method.</span></span> <span data-ttu-id="e78fe-147">Windows PowerShell 运行时调用此方法，以便在会话关闭时对提供程序进行初始化。</span><span class="sxs-lookup"><span data-stu-id="e78fe-147">This method is called by the Windows PowerShell runtime to uninitialize the provider at the close of a session.</span></span>

<span data-ttu-id="e78fe-148">此基本提供程序不重写此方法。</span><span class="sxs-lookup"><span data-stu-id="e78fe-148">This basic provider does not override this method.</span></span> <span data-ttu-id="e78fe-149">但是，以下代码显示了此方法的默认实现：</span><span class="sxs-lookup"><span data-stu-id="e78fe-149">However, the following code shows the default implementation of this method:</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesaccessdbprov01#accessdbprov01ProviderStop](Msh_samplesaccessdbprov01#accessdbprov01ProviderStop)]  -->

## <a name="code-sample"></a><span data-ttu-id="e78fe-150">代码示例</span><span class="sxs-lookup"><span data-stu-id="e78fe-150">Code Sample</span></span>

<span data-ttu-id="e78fe-151">有关完整的示例代码，请参阅 [AccessDbProviderSample01 代码示例](./accessdbprovidersample01-code-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="e78fe-151">For complete sample code, see [AccessDbProviderSample01 Code Sample](./accessdbprovidersample01-code-sample.md).</span></span>

## <a name="testing-the-windows-powershell-provider"></a><span data-ttu-id="e78fe-152">测试 Windows PowerShell 提供程序</span><span class="sxs-lookup"><span data-stu-id="e78fe-152">Testing the Windows PowerShell Provider</span></span>

<span data-ttu-id="e78fe-153">Windows PowerShell 提供程序注册到 Windows PowerShell 后，可以通过在命令行上运行支持的 cmdlet 来对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="e78fe-153">Once your Windows PowerShell provider has been registered with Windows PowerShell, you can test it by running the supported cmdlets on the command line.</span></span> <span data-ttu-id="e78fe-154">对于此基本提供程序，请运行新的 shell 并使用 `Get-PSProvider` cmdlet 来检索提供程序列表，并确保存在 AccessDb 提供程序。</span><span class="sxs-lookup"><span data-stu-id="e78fe-154">For this basic provider, run the new shell and use the `Get-PSProvider` cmdlet to retrieve the list of providers and ensure that the AccessDb provider is present.</span></span>

```powershell
Get-PSProvider
```

<span data-ttu-id="e78fe-155">随即显示以下输出：</span><span class="sxs-lookup"><span data-stu-id="e78fe-155">The following output appears:</span></span>

```Output
Name                 Capabilities                  Drives
----                 ------------                  ------
AccessDb             None                          {}
Alias                ShouldProcess                 {Alias}
Environment          ShouldProcess                 {Env}
FileSystem           Filter, ShouldProcess         {C, Z}
Function             ShouldProcess                 {function}
Registry             ShouldProcess                 {HKLM, HKCU}
```

## <a name="see-also"></a><span data-ttu-id="e78fe-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e78fe-156">See Also</span></span>

[<span data-ttu-id="e78fe-157">创建 Windows PowerShell 提供程序</span><span class="sxs-lookup"><span data-stu-id="e78fe-157">Creating Windows PowerShell Providers</span></span>](./how-to-create-a-windows-powershell-provider.md)

[<span data-ttu-id="e78fe-158">设计 Windows PowerShell 提供程序</span><span class="sxs-lookup"><span data-stu-id="e78fe-158">Designing Your Windows PowerShell Provider</span></span>](./designing-your-windows-powershell-provider.md)
