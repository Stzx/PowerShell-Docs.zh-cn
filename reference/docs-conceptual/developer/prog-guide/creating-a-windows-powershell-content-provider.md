---
ms.date: 09/13/2016
ms.topic: reference
title: 创建 Windows PowerShell 内容提供程序
description: 创建 Windows PowerShell 内容提供程序
ms.openlocfilehash: 7890f0ab8d1cc7f29bdc077b342bae950cfa7827
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645363"
---
# <a name="creating-a-windows-powershell-content-provider"></a><span data-ttu-id="dd316-103">创建 Windows PowerShell 内容提供程序</span><span class="sxs-lookup"><span data-stu-id="dd316-103">Creating a Windows PowerShell Content Provider</span></span>

<span data-ttu-id="dd316-104">本主题介绍如何创建 Windows PowerShell 提供程序，该提供程序使用户能够操作数据存储区中的项的内容。</span><span class="sxs-lookup"><span data-stu-id="dd316-104">This topic describes how to create a Windows PowerShell provider that enables the user to manipulate the contents of the items in a data store.</span></span> <span data-ttu-id="dd316-105">因此，可操作项内容的提供程序称为 Windows PowerShell 内容提供程序。</span><span class="sxs-lookup"><span data-stu-id="dd316-105">As a consequence, a provider that can manipulate the contents of items is referred to as a Windows PowerShell content provider.</span></span>

> [!NOTE]
> <span data-ttu-id="dd316-106">你可以使用适用于 Windows Vista 的 Microsoft Windows 软件开发工具包和 .NET Framework 3.0 运行时组件) 为此提供程序下载 c # 源文件 (。</span><span class="sxs-lookup"><span data-stu-id="dd316-106">You can download the C# source file (AccessDBSampleProvider06.cs) for this provider using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="dd316-107">有关下载说明，请参阅 [如何安装 Windows powershell 和下载 Windows POWERSHELL SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk)。</span><span class="sxs-lookup"><span data-stu-id="dd316-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="dd316-108">下载的源文件在目录中提供 **\<PowerShell Samples>** 。</span><span class="sxs-lookup"><span data-stu-id="dd316-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span> <span data-ttu-id="dd316-109">有关其他 Windows PowerShell 提供程序实现的详细信息，请参阅 [设计 Windows Powershell 提供程序](./designing-your-windows-powershell-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="dd316-109">For more information about other Windows PowerShell provider implementations, see [Designing Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md).</span></span>

## <a name="define-the-windows-powershell-content-provider-class"></a><span data-ttu-id="dd316-110">定义 Windows PowerShell 内容提供程序类</span><span class="sxs-lookup"><span data-stu-id="dd316-110">Define the Windows PowerShell Content Provider Class</span></span>

<span data-ttu-id="dd316-111">Windows PowerShell 内容提供程序必须创建一个支持 [Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) 接口的 .net 类。</span><span class="sxs-lookup"><span data-stu-id="dd316-111">A Windows PowerShell content provider must create a .NET class that supports the [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) interface.</span></span> <span data-ttu-id="dd316-112">下面是本部分中所述的项提供程序的类定义。</span><span class="sxs-lookup"><span data-stu-id="dd316-112">Here is the class definition for the item provider described in this section.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs" range="32-33":::

<span data-ttu-id="dd316-113">请注意，在此类定义中， [Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) 属性包括两个参数。</span><span class="sxs-lookup"><span data-stu-id="dd316-113">Note that in this class definition, the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) attribute includes two parameters.</span></span> <span data-ttu-id="dd316-114">第一个参数指定 Windows PowerShell 使用的提供程序的用户友好名称。</span><span class="sxs-lookup"><span data-stu-id="dd316-114">The first parameter specifies a user-friendly name for the provider that is used by Windows PowerShell.</span></span> <span data-ttu-id="dd316-115">第二个参数指定 Windows PowerShell 特定功能，该功能是在命令处理过程中提供给 Windows PowerShell 运行时的。</span><span class="sxs-lookup"><span data-stu-id="dd316-115">The second parameter specifies the Windows PowerShell specific capabilities that the provider exposes to the Windows PowerShell runtime during command processing.</span></span> <span data-ttu-id="dd316-116">对于此提供程序，没有添加 Windows PowerShell 特定功能。</span><span class="sxs-lookup"><span data-stu-id="dd316-116">For this provider, there are no added Windows PowerShell specific capabilities.</span></span>

## <a name="define-functionality-of-base-class"></a><span data-ttu-id="dd316-117">定义基类的功能</span><span class="sxs-lookup"><span data-stu-id="dd316-117">Define Functionality of Base Class</span></span>

<span data-ttu-id="dd316-118">如 [设计你的 Windows PowerShell 提供程序](./designing-your-windows-powershell-provider.md)中所述， [Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) 类从提供不同提供程序功能的其他一些类派生。</span><span class="sxs-lookup"><span data-stu-id="dd316-118">As described in [Design Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md), the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class derives from several other classes that provided different provider functionality.</span></span> <span data-ttu-id="dd316-119">因此，Windows PowerShell 内容提供程序通常定义这些类提供的所有功能。</span><span class="sxs-lookup"><span data-stu-id="dd316-119">A Windows PowerShell content provider, therefore, typically defines all of the functionality provided by those classes.</span></span>

<span data-ttu-id="dd316-120">若要详细了解如何实现添加特定于会话的初始化信息以及释放提供程序所用资源的功能，请参阅 [创建基本 Windows PowerShell 提供程序](./creating-a-basic-windows-powershell-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="dd316-120">For more information about how to implement functionality for adding session-specific initialization information and for releasing resources that are used by the provider, see [Creating a Basic Windows PowerShell Provider](./creating-a-basic-windows-powershell-provider.md).</span></span>
<span data-ttu-id="dd316-121">但是，大多数提供程序（包括此处所述的提供程序）都可以使用 Windows PowerShell 提供的此功能的默认实现。</span><span class="sxs-lookup"><span data-stu-id="dd316-121">However, most providers, including the provider described here, can use the default implementation of this functionality that is provided by Windows PowerShell.</span></span>

<span data-ttu-id="dd316-122">若要访问数据存储区，该提供程序必须实现 [Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) 基类的方法。</span><span class="sxs-lookup"><span data-stu-id="dd316-122">To access the data store, the provider must implement the methods of the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) base class.</span></span> <span data-ttu-id="dd316-123">有关实现这些方法的详细信息，请参阅 [创建 Windows PowerShell 驱动器提供程序](./creating-a-windows-powershell-drive-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="dd316-123">For more information about implementing these methods, see [Creating a Windows PowerShell Drive Provider](./creating-a-windows-powershell-drive-provider.md).</span></span>

<span data-ttu-id="dd316-124">若要操作数据存储区的项（如获取、设置和清除项），提供程序必须实现 [Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) 基类提供的方法。</span><span class="sxs-lookup"><span data-stu-id="dd316-124">To manipulate the items of a data store, such as getting, setting, and clearing items, the provider must implement the methods provided by the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) base class.</span></span> <span data-ttu-id="dd316-125">有关实现这些方法的详细信息，请参阅 [创建 Windows PowerShell 项提供程序](./creating-a-windows-powershell-item-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="dd316-125">For more information about implementing these methods, see [Creating a Windows PowerShell Item Provider](./creating-a-windows-powershell-item-provider.md).</span></span>

<span data-ttu-id="dd316-126">若要处理多层数据存储区，提供程序必须实现 [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) 基类所提供的方法。</span><span class="sxs-lookup"><span data-stu-id="dd316-126">To work on multi-layer data stores, the provider must implement the methods provided by the [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) base class.</span></span> <span data-ttu-id="dd316-127">有关实现这些方法的详细信息，请参阅 [创建 Windows PowerShell 容器提供程序](./creating-a-windows-powershell-container-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="dd316-127">For more information about implementing these methods, see [Creating a Windows PowerShell Container Provider](./creating-a-windows-powershell-container-provider.md).</span></span>

<span data-ttu-id="dd316-128">若要支持递归命令、嵌套容器和相对路径，提供程序必须实现 [Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) 基类。</span><span class="sxs-lookup"><span data-stu-id="dd316-128">To support recursive commands, nested containers, and relative paths, the provider must implement the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) base class.</span></span> <span data-ttu-id="dd316-129">此外，此 Windows PowerShell 内容提供程序还可以将 [Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) 接口附加到 [Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) 基类，因此必须实现该类提供的方法，这也是必需的。</span><span class="sxs-lookup"><span data-stu-id="dd316-129">In addition, this Windows PowerShell content provider can attaches [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) interface to the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) base class, and must therefore implement the methods provided by that class.</span></span> <span data-ttu-id="dd316-130">有关详细信息，请参阅实现这些方法。请参阅 [实现导航 Windows PowerShell 提供程序](./creating-a-windows-powershell-navigation-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="dd316-130">For more information, see implementing those methods, see [Implement a Navigation Windows PowerShell Provider](./creating-a-windows-powershell-navigation-provider.md).</span></span>

## <a name="implementing-a-content-reader"></a><span data-ttu-id="dd316-131">实现内容读取器</span><span class="sxs-lookup"><span data-stu-id="dd316-131">Implementing a Content Reader</span></span>

<span data-ttu-id="dd316-132">若要从项读取内容，提供程序必须实现从 [Icontentreader](/dotnet/api/System.Management.Automation.Provider.IContentReader)派生的内容读取器类。</span><span class="sxs-lookup"><span data-stu-id="dd316-132">To read content from an item, a provider must implements a content reader class that derives from [System.Management.Automation.Provider.Icontentreader](/dotnet/api/System.Management.Automation.Provider.IContentReader).</span></span>
<span data-ttu-id="dd316-133">此提供程序的内容读取器允许访问数据表中某行的内容。</span><span class="sxs-lookup"><span data-stu-id="dd316-133">The content reader for this provider allows access to the contents of a row in a data table.</span></span> <span data-ttu-id="dd316-134">内容读取器类定义一个 **读取** 方法，该方法从指示的行中检索数据并返回一个表示该数据的列表、一个移动内容读取器的 **查找** 方法、一个关闭内容读取器的 **关闭** 方法以及一个 **Dispose** 方法。</span><span class="sxs-lookup"><span data-stu-id="dd316-134">The content reader class defines a **Read** method that retrieves the data from the indicated row and returns a list representing that data, a **Seek** method that moves the content reader, a **Close** method that closes the content reader, and a **Dispose** method.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs" range="2115-2241":::

## <a name="implementing-a-content-writer"></a><span data-ttu-id="dd316-135">实现内容编写器</span><span class="sxs-lookup"><span data-stu-id="dd316-135">Implementing a Content Writer</span></span>

<span data-ttu-id="dd316-136">若要向项写入内容，提供程序必须实现从 [Icontentwriter](/dotnet/api/System.Management.Automation.Provider.IContentWriter)派生的内容编写器类。</span><span class="sxs-lookup"><span data-stu-id="dd316-136">To write content to an item, a provider must implement a content writer class derives from [System.Management.Automation.Provider.Icontentwriter](/dotnet/api/System.Management.Automation.Provider.IContentWriter).</span></span>
<span data-ttu-id="dd316-137">内容编写器类定义 **写入** 方法，该方法写入指定的行内容、移动内容编写器的 **Seek** 方法、关闭内容编写器的 **关闭** 方法以及 **Dispose** 方法。</span><span class="sxs-lookup"><span data-stu-id="dd316-137">The content writer class defines a **Write** method that writes the specified row content, a **Seek** method that moves the content writer, a **Close** method that closes the content writer, and a **Dispose** method.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs" range="2250-2394":::

## <a name="retrieving-the-content-reader"></a><span data-ttu-id="dd316-138">检索内容读取器</span><span class="sxs-lookup"><span data-stu-id="dd316-138">Retrieving the Content Reader</span></span>

<span data-ttu-id="dd316-139">若要从项获取内容，提供程序必须实现 [Icontentcmdletprovider. Getcontentreader \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) 以支持 `Get-Content` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="dd316-139">To get content from an item, the provider must implement the [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) to support the `Get-Content` cmdlet.</span></span> <span data-ttu-id="dd316-140">此方法返回位于指定路径处的项的内容读取器。</span><span class="sxs-lookup"><span data-stu-id="dd316-140">This method returns the content reader for the item located at the specified path.</span></span> <span data-ttu-id="dd316-141">然后，可以打开读取器对象来读取内容。</span><span class="sxs-lookup"><span data-stu-id="dd316-141">The reader object can then be opened to read the content.</span></span>

<span data-ttu-id="dd316-142">下面是此提供程序的此方法的 [Icontentcmdletprovider. Getcontentreader \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) 实现。</span><span class="sxs-lookup"><span data-stu-id="dd316-142">Here is the implementation of [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) for this method for this provider.</span></span>

```csharp
public IContentReader GetContentReader(string path)
{
    string tableName;
    int rowNumber;

    PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

    if (type == PathType.Invalid)
    {
        ThrowTerminatingInvalidPathException(path);
    }
    else if (type == PathType.Row)
    {
        throw new InvalidOperationException("contents can be obtained only for tables");
    }

    return new AccessDBContentReader(path, this);
} // GetContentReader
```

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs" range="1829-1846":::

#### <a name="things-to-remember-about-implementing-getcontentreader"></a><span data-ttu-id="dd316-143">有关实现 GetContentReader 的注意事项</span><span class="sxs-lookup"><span data-stu-id="dd316-143">Things to Remember About Implementing GetContentReader</span></span>

<span data-ttu-id="dd316-144">以下条件可能适用于 [Icontentcmdletprovider. Getcontentreader \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader)的实现：。</span><span class="sxs-lookup"><span data-stu-id="dd316-144">The following conditions may apply to an implementation of [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader):</span></span>

- <span data-ttu-id="dd316-145">定义提供程序类时，Windows PowerShell 内容提供程序可以声明 ExpandWildcards、Filter、Include 或 Exclude 的提供程序功能， [Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) 枚举。</span><span class="sxs-lookup"><span data-stu-id="dd316-145">When defining the provider class, a Windows PowerShell content provider might declare provider capabilities of ExpandWildcards, Filter, Include, or Exclude, from the [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeration.</span></span> <span data-ttu-id="dd316-146">在这些情况下， [Icontentcmdletprovider. Getcontentreader \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) 方法的实现必须确保传递给该方法的路径满足指定功能的要求。</span><span class="sxs-lookup"><span data-stu-id="dd316-146">In these cases, the implementation of the [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) method must ensure that the path passed to the method meets the requirements of the specified capabilities.</span></span> <span data-ttu-id="dd316-147">若要执行此操作，方法应访问相应的属性，例如， [Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) 和 [Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) 属性中的相应属性，例如 ""。</span><span class="sxs-lookup"><span data-stu-id="dd316-147">To do this, the method should access the appropriate property, for example, the [System.Management.Automation.Provider.Cmdletprovider.Exclude\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) and [System.Management.Automation.Provider.Cmdletprovider.Include\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) properties.</span></span>

- <span data-ttu-id="dd316-148">默认情况下，除非 [Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) 属性设置为，否则此方法的重写不应检索用户隐藏的对象的读取 `true` 器。</span><span class="sxs-lookup"><span data-stu-id="dd316-148">By default, overrides of this method should not retrieve a reader for objects that are hidden from the user unless the [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) property is set to `true`.</span></span> <span data-ttu-id="dd316-149">如果路径表示从用户和 [Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) 中隐藏的项被设置为，则应将错误写入错误 `false` 。</span><span class="sxs-lookup"><span data-stu-id="dd316-149">An error should be written if the path represents an item that is hidden from the user and [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) is set to `false`.</span></span>

## <a name="attaching-dynamic-parameters-to-the-get-content-cmdlet"></a><span data-ttu-id="dd316-150">将动态参数附加到 Get-Content Cmdlet</span><span class="sxs-lookup"><span data-stu-id="dd316-150">Attaching Dynamic Parameters to the Get-Content Cmdlet</span></span>

<span data-ttu-id="dd316-151">`Get-Content`Cmdlet 可能需要在运行时动态指定的其他参数。</span><span class="sxs-lookup"><span data-stu-id="dd316-151">The `Get-Content` cmdlet might require additional parameters that are specified dynamically at runtime.</span></span> <span data-ttu-id="dd316-152">为了提供这些动态参数，Windows PowerShell 内容提供程序必须实现 [Icontentcmdletprovider. Getcontentreaderdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters) 方法。</span><span class="sxs-lookup"><span data-stu-id="dd316-152">To provide these dynamic parameters, the Windows PowerShell content provider must implement the [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreaderdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters) method.</span></span> <span data-ttu-id="dd316-153">此方法检索指定路径处的项的动态参数，并返回一个对象，该对象具有与 cmdlet 类或 [Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) 对象类似的分析特性的属性和字段。</span><span class="sxs-lookup"><span data-stu-id="dd316-153">This method retrieves dynamic parameters for the item at the indicated path and returns an object that has properties and fields with parsing attributes similar to a cmdlet class or a [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) object.</span></span> <span data-ttu-id="dd316-154">Windows PowerShell 运行时使用返回的对象将参数添加到 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="dd316-154">The Windows PowerShell runtime uses the returned object to add the parameters to the cmdlet.</span></span>

<span data-ttu-id="dd316-155">此 Windows PowerShell 容器提供程序未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="dd316-155">This Windows PowerShell container provider does not implement this method.</span></span> <span data-ttu-id="dd316-156">但是，下面的代码是此方法的默认实现。</span><span class="sxs-lookup"><span data-stu-id="dd316-156">However, the following code is the default implementation of this method.</span></span>

```csharp
public object GetContentReaderDynamicParameters(string path)
{
    return null;
}
```

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs" range="1853-1856":::

## <a name="retrieving-the-content-writer"></a><span data-ttu-id="dd316-157">检索内容编写器</span><span class="sxs-lookup"><span data-stu-id="dd316-157">Retrieving the Content Writer</span></span>

<span data-ttu-id="dd316-158">若要向项写入内容，提供程序必须实现 [Icontentcmdletprovider. Getcontentwriter \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) 以支持 `Set-Content` 和 `Add-Content` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="dd316-158">To write content to an item, the provider must implement the [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriter\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) to support the `Set-Content` and `Add-Content` cmdlets.</span></span> <span data-ttu-id="dd316-159">此方法返回位于指定路径处的项的内容编写器。</span><span class="sxs-lookup"><span data-stu-id="dd316-159">This method returns the content writer for the item located at the specified path.</span></span>

<span data-ttu-id="dd316-160">下面是此方法的 [Icontentcmdletprovider. Getcontentwriter \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) 的实现方法。</span><span class="sxs-lookup"><span data-stu-id="dd316-160">Here is the implementation of [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriter\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) for this method.</span></span>

```csharp
public IContentWriter GetContentWriter(string path)
{
    string tableName;
    int rowNumber;

    PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

    if (type == PathType.Invalid)
    {
        ThrowTerminatingInvalidPathException(path);
    }
    else if (type == PathType.Row)
    {
        throw new InvalidOperationException("contents can be added only to tables");
    }

    return new AccessDBContentWriter(path, this);
}
```

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs" range="1863-1880":::

#### <a name="things-to-remember-about-implementing-getcontentwriter"></a><span data-ttu-id="dd316-161">有关实现 GetContentWriter 的注意事项</span><span class="sxs-lookup"><span data-stu-id="dd316-161">Things to Remember About Implementing GetContentWriter</span></span>

<span data-ttu-id="dd316-162">以下情况可能适用于你的 [Icontentcmdletprovider. Getcontentwriter \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter)实现：</span><span class="sxs-lookup"><span data-stu-id="dd316-162">The following conditions may apply to your implementation of [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriter\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter):</span></span>

- <span data-ttu-id="dd316-163">定义提供程序类时，Windows PowerShell 内容提供程序可以声明 ExpandWildcards、Filter、Include 或 Exclude 的提供程序功能， [Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) 枚举。</span><span class="sxs-lookup"><span data-stu-id="dd316-163">When defining the provider class, a Windows PowerShell content provider might declare provider capabilities of ExpandWildcards, Filter, Include, or Exclude, from the [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeration.</span></span> <span data-ttu-id="dd316-164">在这些情况下， [Icontentcmdletprovider. Getcontentwriter \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) 方法的实现必须确保传递给该方法的路径满足指定功能的要求。</span><span class="sxs-lookup"><span data-stu-id="dd316-164">In these cases, the implementation of the [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriter\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) method must ensure that the path passed to the method meets the requirements of the specified capabilities.</span></span> <span data-ttu-id="dd316-165">若要执行此操作，方法应访问相应的属性，例如， [Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) 和 [Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) 属性中的相应属性，例如 ""。</span><span class="sxs-lookup"><span data-stu-id="dd316-165">To do this, the method should access the appropriate property, for example, the [System.Management.Automation.Provider.Cmdletprovider.Exclude\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) and [System.Management.Automation.Provider.Cmdletprovider.Include\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) properties.</span></span>

- <span data-ttu-id="dd316-166">默认情况下，除非 [Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) 属性设置为，否则此方法的重写不应检索用户隐藏的对象的编写 `true` 器。</span><span class="sxs-lookup"><span data-stu-id="dd316-166">By default, overrides of this method should not retrieve a writer for objects that are hidden from the user unless the [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) property is set to `true`.</span></span> <span data-ttu-id="dd316-167">如果路径表示从用户和 [Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) 中隐藏的项被设置为，则应将错误写入错误 `false` 。</span><span class="sxs-lookup"><span data-stu-id="dd316-167">An error should be written if the path represents an item that is hidden from the user and [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) is set to `false`.</span></span>

## <a name="attaching-dynamic-parameters-to-the-add-content-and-set-content-cmdlets"></a><span data-ttu-id="dd316-168">将动态参数附加到 Add-Content 和 Set-Content Cmdlet</span><span class="sxs-lookup"><span data-stu-id="dd316-168">Attaching Dynamic Parameters to the Add-Content and Set-Content Cmdlets</span></span>

<span data-ttu-id="dd316-169">`Add-Content`和 `Set-Content` cmdlet 可能需要添加了运行时的其他动态参数。</span><span class="sxs-lookup"><span data-stu-id="dd316-169">The `Add-Content` and `Set-Content` cmdlets might require additional dynamic parameters that are added a runtime.</span></span> <span data-ttu-id="dd316-170">为了提供这些动态参数，Windows PowerShell 内容提供程序必须实现 [Icontentcmdletprovider. Getcontentwriterdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters) 方法来处理这些参数。</span><span class="sxs-lookup"><span data-stu-id="dd316-170">To provide these dynamic parameters, the Windows PowerShell content provider must implement the [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriterdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters) method to handle these parameters.</span></span> <span data-ttu-id="dd316-171">此方法检索指定路径处的项的动态参数，并返回一个对象，该对象具有与 cmdlet 类或 [Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) 对象类似的分析特性的属性和字段。</span><span class="sxs-lookup"><span data-stu-id="dd316-171">This method retrieves dynamic parameters for the item at the indicated path and returns an object that has properties and fields with parsing attributes similar to a cmdlet class or a [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) object.</span></span> <span data-ttu-id="dd316-172">Windows PowerShell 运行时使用返回的对象将参数添加到 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="dd316-172">The Windows PowerShell runtime uses the returned object to add the parameters to the cmdlets.</span></span>

<span data-ttu-id="dd316-173">此 Windows PowerShell 容器提供程序未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="dd316-173">This Windows PowerShell container provider does not implement this method.</span></span> <span data-ttu-id="dd316-174">但是，下面的代码是此方法的默认实现。</span><span class="sxs-lookup"><span data-stu-id="dd316-174">However, the following code is the default implementation of this method.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs" range="1887-1890":::

## <a name="clearing-content"></a><span data-ttu-id="dd316-175">清除内容</span><span class="sxs-lookup"><span data-stu-id="dd316-175">Clearing Content</span></span>

<span data-ttu-id="dd316-176">你的内容提供商实现了 [Icontentcmdletprovider. Clearcontent \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) 方法以支持 `Clear-Content` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="dd316-176">Your content provider implements the [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) method in support of the `Clear-Content` cmdlet.</span></span> <span data-ttu-id="dd316-177">此方法删除指定路径处的项的内容，但保留该项不变。</span><span class="sxs-lookup"><span data-stu-id="dd316-177">This method removes the contents of the item at the specified path, but leaves the item intact.</span></span>

<span data-ttu-id="dd316-178">下面是此提供程序的 [Icontentcmdletprovider. Clearcontent \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) 方法的实现。</span><span class="sxs-lookup"><span data-stu-id="dd316-178">Here is the implementation of the [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) method for this provider.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs" range="1775-1812":::

#### <a name="things-to-remember-about-implementing-clearcontent"></a><span data-ttu-id="dd316-179">有关实现 ClearContent 的注意事项</span><span class="sxs-lookup"><span data-stu-id="dd316-179">Things to Remember About Implementing ClearContent</span></span>

<span data-ttu-id="dd316-180">以下条件可能适用于 [Icontentcmdletprovider. Clearcontent \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent)的实现：。</span><span class="sxs-lookup"><span data-stu-id="dd316-180">The following conditions may apply to an implementation of [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent):</span></span>

- <span data-ttu-id="dd316-181">定义提供程序类时，Windows PowerShell 内容提供程序可以声明 ExpandWildcards、Filter、Include 或 Exclude 的提供程序功能， [Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) 枚举。</span><span class="sxs-lookup"><span data-stu-id="dd316-181">When defining the provider class, a Windows PowerShell content provider might declare provider capabilities of ExpandWildcards, Filter, Include, or Exclude, from the [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeration.</span></span> <span data-ttu-id="dd316-182">在这些情况下， [Icontentcmdletprovider. Clearcontent \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) 方法的实现必须确保传递给该方法的路径满足指定功能的要求。</span><span class="sxs-lookup"><span data-stu-id="dd316-182">In these cases, the implementation of the [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) method must ensure that the path passed to the method meets the requirements of the specified capabilities.</span></span> <span data-ttu-id="dd316-183">若要执行此操作，方法应访问相应的属性，例如， [Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) 和 [Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) 属性中的相应属性，例如 ""。</span><span class="sxs-lookup"><span data-stu-id="dd316-183">To do this, the method should access the appropriate property, for example, the [System.Management.Automation.Provider.Cmdletprovider.Exclude\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) and [System.Management.Automation.Provider.Cmdletprovider.Include\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) properties.</span></span>

- <span data-ttu-id="dd316-184">默认情况下，除非将 [Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) 属性设置为，否则此方法的重写不应清除用户隐藏的对象的内容 `true` 。</span><span class="sxs-lookup"><span data-stu-id="dd316-184">By default, overrides of this method should not clear the contents of objects that are hidden from the user unless the [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) property is set to `true`.</span></span> <span data-ttu-id="dd316-185">如果路径表示从用户和 [Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) 中隐藏的项被设置为，则应将错误写入错误 `false` 。</span><span class="sxs-lookup"><span data-stu-id="dd316-185">An error should be written if the path represents an item that is hidden from the user and [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) is set to `false`.</span></span>

- <span data-ttu-id="dd316-186">在对数据存储进行任何更改之前，你的 [Icontentcmdletprovider 和 Clearcontent \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) 方法的实现应调用 [Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) ，并验证其返回值的返回值。</span><span class="sxs-lookup"><span data-stu-id="dd316-186">Your implementation of the [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) method should call [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) and verify its return value before making any changes to the data store.</span></span> <span data-ttu-id="dd316-187">此方法用于确认对数据存储进行更改时（如清除内容）执行操作。</span><span class="sxs-lookup"><span data-stu-id="dd316-187">This method is used to confirm execution of an operation when a change is made to the data store, such as clearing content.</span></span> <span data-ttu-id="dd316-188">[Cmdletprovider. ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)方法发送要更改为用户的资源的名称，并在 Windows PowerShell 运行时处理任何命令行设置或首选项变量来确定应显示的内容。</span><span class="sxs-lookup"><span data-stu-id="dd316-188">The [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) method sends the name of the resource to be changed to the user, with the Windows PowerShell runtime handling any command-line settings or preference variables in determining what should be displayed.</span></span>

  <span data-ttu-id="dd316-189">在对 Cmdletprovider 的调用返回后， [ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) 方法 `true` 应调用 [Icontentcmdletprovider。 Clearcontent \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) 方法应调用. Cmdletprovider 方法的 [调用方的](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) 调用程序的调用程序的。</span><span class="sxs-lookup"><span data-stu-id="dd316-189">After the call to [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) returns `true`, the [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) method should call the [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) method.</span></span> <span data-ttu-id="dd316-190">此方法向用户发送一条消息，以允许反馈验证是否应继续进行操作。</span><span class="sxs-lookup"><span data-stu-id="dd316-190">This method sends a message to the user to allow feedback to verify if the operation should be continued.</span></span> <span data-ttu-id="dd316-191">对 [Cmdletprovider. ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) 的调用允许对潜在的危险系统修改进行额外检查。</span><span class="sxs-lookup"><span data-stu-id="dd316-191">The call to [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) allows an additional check for potentially dangerous system modifications.</span></span>

## <a name="attaching-dynamic-parameters-to-the-clear-content-cmdlet"></a><span data-ttu-id="dd316-192">将动态参数附加到 Clear-Content Cmdlet</span><span class="sxs-lookup"><span data-stu-id="dd316-192">Attaching Dynamic Parameters to the Clear-Content Cmdlet</span></span>

<span data-ttu-id="dd316-193">`Clear-Content`Cmdlet 可能需要在运行时添加的其他动态参数。</span><span class="sxs-lookup"><span data-stu-id="dd316-193">The `Clear-Content` cmdlet might require additional dynamic parameters that are added at runtime.</span></span> <span data-ttu-id="dd316-194">为了提供这些动态参数，Windows PowerShell 内容提供程序必须实现 [Icontentcmdletprovider. Clearcontentdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters) 方法来处理这些参数。</span><span class="sxs-lookup"><span data-stu-id="dd316-194">To provide these dynamic parameters, the Windows PowerShell content provider must implement the [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontentdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters) method to handle these parameters.</span></span> <span data-ttu-id="dd316-195">此方法检索指定路径处的项的参数。</span><span class="sxs-lookup"><span data-stu-id="dd316-195">This method retrieves the parameters for the item at the indicated path.</span></span> <span data-ttu-id="dd316-196">此方法检索指定路径处的项的动态参数，并返回一个对象，该对象具有与 cmdlet 类或 [Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) 对象类似的分析特性的属性和字段。</span><span class="sxs-lookup"><span data-stu-id="dd316-196">This method retrieves dynamic parameters for the item at the indicated path and returns an object that has properties and fields with parsing attributes similar to a cmdlet class or a [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) object.</span></span> <span data-ttu-id="dd316-197">Windows PowerShell 运行时使用返回的对象将参数添加到 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="dd316-197">The Windows PowerShell runtime uses the returned object to add the parameters to the cmdlet.</span></span>

<span data-ttu-id="dd316-198">此 Windows PowerShell 容器提供程序未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="dd316-198">This Windows PowerShell container provider does not implement this method.</span></span> <span data-ttu-id="dd316-199">但是，下面的代码是此方法的默认实现。</span><span class="sxs-lookup"><span data-stu-id="dd316-199">However, the following code is the default implementation of this method.</span></span>

```csharp
public object ClearContentDynamicParameters(string path)
{
    return null;
}
```

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs" range="1819-1822":::

## <a name="code-sample"></a><span data-ttu-id="dd316-200">代码示例</span><span class="sxs-lookup"><span data-stu-id="dd316-200">Code Sample</span></span>

<span data-ttu-id="dd316-201">有关完整的示例代码，请参阅 [AccessDbProviderSample06 代码示例](./accessdbprovidersample06-code-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="dd316-201">For complete sample code, see [AccessDbProviderSample06 Code Sample](./accessdbprovidersample06-code-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="dd316-202">定义对象类型和格式设置</span><span class="sxs-lookup"><span data-stu-id="dd316-202">Defining Object Types and Formatting</span></span>

<span data-ttu-id="dd316-203">编写提供程序时，可能需要将成员添加到现有对象或定义新的对象。</span><span class="sxs-lookup"><span data-stu-id="dd316-203">When writing a provider, it may be necessary to add members to existing objects or define new objects.</span></span> <span data-ttu-id="dd316-204">完成此操作后，你必须创建一个类型文件，Windows PowerShell 可以使用该文件来标识该对象的成员和定义如何显示该对象的格式化文件。</span><span class="sxs-lookup"><span data-stu-id="dd316-204">When this is done, you must create a Types file that Windows PowerShell can use to identify the members of the object and a Format file that defines how the object is displayed.</span></span> <span data-ttu-id="dd316-205">有关详细信息，请参阅 [扩展对象类型和格式](/previous-versions/ms714665(v=vs.85))。</span><span class="sxs-lookup"><span data-stu-id="dd316-205">For more information, see [Extending Object Types and Formatting](/previous-versions/ms714665(v=vs.85)).</span></span>

## <a name="building-the-windows-powershell-provider"></a><span data-ttu-id="dd316-206">生成 Windows PowerShell 提供程序</span><span class="sxs-lookup"><span data-stu-id="dd316-206">Building the Windows PowerShell Provider</span></span>

<span data-ttu-id="dd316-207">请参阅 [如何注册 cmdlet、提供程序和主机应用程序](/previous-versions/ms714644(v=vs.85))。</span><span class="sxs-lookup"><span data-stu-id="dd316-207">See [How to Register Cmdlets, Providers, and Host Applications](/previous-versions/ms714644(v=vs.85)).</span></span>

## <a name="testing-the-windows-powershell-provider"></a><span data-ttu-id="dd316-208">测试 Windows PowerShell 提供程序</span><span class="sxs-lookup"><span data-stu-id="dd316-208">Testing the Windows PowerShell Provider</span></span>

<span data-ttu-id="dd316-209">向 Windows powershell 注册 Windows PowerShell 提供程序后，可以通过在命令行上运行支持的 cmdlet 来对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="dd316-209">When your Windows PowerShell provider has been registered with Windows PowerShell, you can test it by running the supported cmdlets on the command line.</span></span> <span data-ttu-id="dd316-210">例如，测试示例内容提供程序。</span><span class="sxs-lookup"><span data-stu-id="dd316-210">For example, test the sample content provider.</span></span>

<span data-ttu-id="dd316-211">使用 `Get-Content` cmdlet 可在参数所指定的路径中检索数据库表中指定项的内容 `Path` 。</span><span class="sxs-lookup"><span data-stu-id="dd316-211">Use the `Get-Content` cmdlet to retrieve the contents of specified item in the database table at the path specified by the `Path` parameter.</span></span> <span data-ttu-id="dd316-212">`ReadCount`参数指定定义的内容读取器 (默认值 1) 读取的项数。</span><span class="sxs-lookup"><span data-stu-id="dd316-212">The `ReadCount` parameter specifies the number of items for the defined content reader to read (default 1).</span></span> <span data-ttu-id="dd316-213">对于以下命令条目，该 cmdlet 将从表中检索两行 (项) 并显示其内容。</span><span class="sxs-lookup"><span data-stu-id="dd316-213">With the following command entry, the cmdlet retrieves two rows (items) from the table and displays their contents.</span></span> <span data-ttu-id="dd316-214">请注意，下面的示例输出使用虚构的 Access 数据库。</span><span class="sxs-lookup"><span data-stu-id="dd316-214">Note that the following example output uses a fictitious Access database.</span></span>

```powershell
Get-Content -Path mydb:\Customers -ReadCount 2
```

```Output
ID        : 1
FirstName : Eric
LastName  : Gruber
Email     : ericgruber@fabrikam.com
Title     : President
Company   : Fabrikam
WorkPhone : (425) 555-0100
Address   : 4567 Main Street
City      : Buffalo
State     : NY
Zip       : 98052
Country   : USA
ID        : 2
FirstName : Eva
LastName  : Corets
Email     : evacorets@cohowinery.com
Title     : Sales Representative
Company   : Coho Winery
WorkPhone : (360) 555-0100
Address   : 8910 Main Street
City      : Cabmerlot
State     : WA
Zip       : 98089
Country   : USA
```

## <a name="see-also"></a><span data-ttu-id="dd316-215">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dd316-215">See Also</span></span>

[<span data-ttu-id="dd316-216">创建 Windows PowerShell 提供程序</span><span class="sxs-lookup"><span data-stu-id="dd316-216">Creating Windows PowerShell providers</span></span>](./how-to-create-a-windows-powershell-provider.md)

[<span data-ttu-id="dd316-217">设计你的 Windows PowerShell 提供程序</span><span class="sxs-lookup"><span data-stu-id="dd316-217">Design Your Windows PowerShell provider</span></span>](./designing-your-windows-powershell-provider.md)

<span data-ttu-id="dd316-218">[扩展对象类型和格式](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="dd316-218">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

[<span data-ttu-id="dd316-219">实现导航 Windows PowerShell 提供程序</span><span class="sxs-lookup"><span data-stu-id="dd316-219">Implement a Navigation Windows PowerShell provider</span></span>](./creating-a-windows-powershell-navigation-provider.md)

<span data-ttu-id="dd316-220">[如何注册 Cmdlet、提供程序和主机应用程序](/previous-versions/ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="dd316-220">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions/ms714644(v=vs.85))</span></span>

[<span data-ttu-id="dd316-221">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="dd316-221">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="dd316-222">Windows PowerShell 程序员指南</span><span class="sxs-lookup"><span data-stu-id="dd316-222">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)
