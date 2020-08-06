---
title: 创建 Windows PowerShell 容器提供程序
ms.date: 09/13/2016
ms.openlocfilehash: a5bcba425909eb98c010a1ea010cb02b995771f3
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787200"
---
# <a name="creating-a-windows-powershell-container-provider"></a><span data-ttu-id="097a4-102">创建 Windows PowerShell 容器提供程序</span><span class="sxs-lookup"><span data-stu-id="097a4-102">Creating a Windows PowerShell Container Provider</span></span>

<span data-ttu-id="097a4-103">本主题介绍如何创建可在多层数据存储上使用的 Windows PowerShell 提供程序。</span><span class="sxs-lookup"><span data-stu-id="097a4-103">This topic describes how to create a Windows PowerShell provider that can work on multi-layer data stores.</span></span> <span data-ttu-id="097a4-104">对于这种类型的数据存储，存储区的顶层包含根项，而每个后续级别称为子项的节点。</span><span class="sxs-lookup"><span data-stu-id="097a4-104">For this type of data store, the top level of the store contains the root items and each subsequent level is referred to as a node of child items.</span></span> <span data-ttu-id="097a4-105">通过允许用户在这些子节点上工作，用户可以通过数据存储区进行分层交互。</span><span class="sxs-lookup"><span data-stu-id="097a4-105">By allowing the user to work on these child nodes, a user can interact hierarchically through the data store.</span></span>

<span data-ttu-id="097a4-106">可在多级别数据存储上使用的提供程序称为 "Windows PowerShell 容器提供程序"。</span><span class="sxs-lookup"><span data-stu-id="097a4-106">Providers that can work on multi-level data stores are referred to as Windows PowerShell container providers.</span></span> <span data-ttu-id="097a4-107">但请注意，只有当一个容器 (没有与其中的项) 任何嵌套容器时，才能使用 Windows PowerShell 容器提供程序。</span><span class="sxs-lookup"><span data-stu-id="097a4-107">However, be aware that a Windows PowerShell container provider can be used only when there is one container (no nested containers) with items in it.</span></span> <span data-ttu-id="097a4-108">如果有嵌套容器，则必须实现 Windows PowerShell 导航提供程序。</span><span class="sxs-lookup"><span data-stu-id="097a4-108">If there are nested containers, then you must implement a Windows PowerShell navigation provider.</span></span> <span data-ttu-id="097a4-109">有关实现 Windows PowerShell 导航提供程序的详细信息，请参阅[创建 Windows Powershell 导航提供程序](./creating-a-windows-powershell-navigation-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="097a4-109">For more information about implementing Windows PowerShell navigation provider, see [Creating a Windows PowerShell Navigation Provider](./creating-a-windows-powershell-navigation-provider.md).</span></span>

> [!NOTE]
> <span data-ttu-id="097a4-110">你可以使用适用于 Windows Vista 的 Microsoft Windows 软件开发工具包和 .NET Framework 3.0 运行时组件) 为此提供程序下载 c # 源文件 (。</span><span class="sxs-lookup"><span data-stu-id="097a4-110">You can download the C# source file (AccessDBSampleProvider04.cs) for this provider using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="097a4-111">有关下载说明，请参阅[如何安装 Windows powershell 和下载 Windows POWERSHELL SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk)。</span><span class="sxs-lookup"><span data-stu-id="097a4-111">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="097a4-112">下载的源文件在目录中提供 **\<PowerShell Samples>** 。</span><span class="sxs-lookup"><span data-stu-id="097a4-112">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span> <span data-ttu-id="097a4-113">有关其他 Windows PowerShell 提供程序实现的详细信息，请参阅[设计 Windows Powershell 提供程序](./designing-your-windows-powershell-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="097a4-113">For more information about other Windows PowerShell provider implementations, see [Designing Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md).</span></span>

<span data-ttu-id="097a4-114">此处所述的 Windows PowerShell 容器提供程序将数据库定义为其单个容器，并将数据库的表和行定义为容器的项。</span><span class="sxs-lookup"><span data-stu-id="097a4-114">The Windows PowerShell container provider described here defines the database as its single container, with the tables and rows of the database defined as items of the container.</span></span>

> [!CAUTION]
> <span data-ttu-id="097a4-115">请注意，此设计假设有一个数据库，该数据库具有名称为 ID 的字段，并且该字段的类型为 LongInteger。</span><span class="sxs-lookup"><span data-stu-id="097a4-115">Be aware that this design assumes a database that has a field with the name ID, and that the type of the field is LongInteger.</span></span>

## <a name="defining-a-windows-powershell-container-provider-class"></a><span data-ttu-id="097a4-116">定义 Windows PowerShell 容器提供程序类</span><span class="sxs-lookup"><span data-stu-id="097a4-116">Defining a Windows PowerShell Container Provider Class</span></span>

<span data-ttu-id="097a4-117">Windows PowerShell 容器提供程序必须定义一个从[Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)基类派生的 .net 类的 .net 类。</span><span class="sxs-lookup"><span data-stu-id="097a4-117">A Windows PowerShell container provider must define a .NET class that derives from the [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) base class.</span></span> <span data-ttu-id="097a4-118">下面是本部分中所述的 Windows PowerShell 容器提供程序的类定义。</span><span class="sxs-lookup"><span data-stu-id="097a4-118">Here is the class definition for the Windows PowerShell container provider described in this section.</span></span>

```csharp
[CmdletProvider("AccessDB", ProviderCapabilities.None)]
public class AccessDBProvider : ContainerCmdletProvider
```

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs" range="34-35":::

<span data-ttu-id="097a4-119">请注意，在此类定义中， [Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute)属性包括两个参数。</span><span class="sxs-lookup"><span data-stu-id="097a4-119">Notice that in this class definition, the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) attribute includes two parameters.</span></span> <span data-ttu-id="097a4-120">第一个参数指定 Windows PowerShell 使用的提供程序的用户友好名称。</span><span class="sxs-lookup"><span data-stu-id="097a4-120">The first parameter specifies a user-friendly name for the provider that is used by Windows PowerShell.</span></span> <span data-ttu-id="097a4-121">第二个参数指定 Windows PowerShell 特定功能，该功能是在命令处理过程中提供给 Windows PowerShell 运行时的。</span><span class="sxs-lookup"><span data-stu-id="097a4-121">The second parameter specifies the Windows PowerShell specific capabilities that the provider exposes to the Windows PowerShell runtime during command processing.</span></span> <span data-ttu-id="097a4-122">对于此提供程序，没有添加的 Windows PowerShell 特定功能。</span><span class="sxs-lookup"><span data-stu-id="097a4-122">For this provider, there are no Windows PowerShell specific capabilities that are added.</span></span>

## <a name="defining-base-functionality"></a><span data-ttu-id="097a4-123">定义基本功能</span><span class="sxs-lookup"><span data-stu-id="097a4-123">Defining Base Functionality</span></span>

<span data-ttu-id="097a4-124">如[设计你的 Windows PowerShell 提供](./designing-your-windows-powershell-provider.md)程序中所述， [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)类派生自其他一些类，这些类提供了不同的提供程序功能。</span><span class="sxs-lookup"><span data-stu-id="097a4-124">As described in [Designing Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md), the [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class derives from several other classes that provided different provider functionality.</span></span> <span data-ttu-id="097a4-125">因此，Windows PowerShell 容器提供程序需要定义这些类提供的所有功能。</span><span class="sxs-lookup"><span data-stu-id="097a4-125">A Windows PowerShell container provider, therefore, needs to define all of the functionality provided by those classes.</span></span>

<span data-ttu-id="097a4-126">若要实现添加特定于会话的初始化信息以及释放提供程序所用资源的功能，请参阅[创建基本 Windows PowerShell 提供程序](./creating-a-basic-windows-powershell-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="097a4-126">To implement functionality for adding session-specific initialization information and for releasing resources that are used by the provider, see [Creating a Basic Windows PowerShell Provider](./creating-a-basic-windows-powershell-provider.md).</span></span>
<span data-ttu-id="097a4-127">但是，大多数提供程序 (包括此处所述的提供程序) 可以使用 Windows PowerShell 提供的此功能的默认实现。</span><span class="sxs-lookup"><span data-stu-id="097a4-127">However, most providers (including the provider described here) can use the default implementation of this functionality that is provided by Windows PowerShell.</span></span>

<span data-ttu-id="097a4-128">若要获取对数据存储区的访问权限，提供程序必须实现[Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)基类的方法。</span><span class="sxs-lookup"><span data-stu-id="097a4-128">To get access to the data store, the provider must implement the methods of the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) base class.</span></span> <span data-ttu-id="097a4-129">有关实现这些方法的详细信息，请参阅[创建 Windows PowerShell 驱动器提供程序](./creating-a-windows-powershell-drive-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="097a4-129">For more information about implementing these methods, see [Creating an Windows PowerShell Drive Provider](./creating-a-windows-powershell-drive-provider.md).</span></span>

<span data-ttu-id="097a4-130">若要操作数据存储区的项（如获取、设置和清除项），提供程序必须实现[Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)基类提供的方法。</span><span class="sxs-lookup"><span data-stu-id="097a4-130">To manipulate the items of a data store, such as getting, setting, and clearing items, the provider must implement the methods provided by the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) base class.</span></span> <span data-ttu-id="097a4-131">有关实现这些方法的详细信息，请参阅[创建 Windows PowerShell 项提供程序](./creating-a-windows-powershell-item-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="097a4-131">For more information about implementing these methods, see [Creating an Windows PowerShell Item Provider](./creating-a-windows-powershell-item-provider.md).</span></span>

## <a name="retrieving-child-items"></a><span data-ttu-id="097a4-132">检索子项</span><span class="sxs-lookup"><span data-stu-id="097a4-132">Retrieving Child Items</span></span>

<span data-ttu-id="097a4-133">若要检索子项，Windows PowerShell 容器提供程序必须重写[Containercmdletprovider. Getchilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)方法，以支持来自 cmdlet 的调用 `Get-ChildItem` 。</span><span class="sxs-lookup"><span data-stu-id="097a4-133">To retrieve a child item, the Windows PowerShell container provider must override the [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) method to support calls from the `Get-ChildItem` cmdlet.</span></span> <span data-ttu-id="097a4-134">此方法从数据存储中检索子项目，并将其作为对象写入管道。</span><span class="sxs-lookup"><span data-stu-id="097a4-134">This method retrieves child items from the data store and writes them to the pipeline as objects.</span></span> <span data-ttu-id="097a4-135">如果 `recurse` 指定了 cmdlet 的参数，则该方法将检索所有子项，而不管它们处于什么级别。</span><span class="sxs-lookup"><span data-stu-id="097a4-135">If the `recurse` parameter of the cmdlet is specified, the method retrieves all children regardless of what level they are at.</span></span> <span data-ttu-id="097a4-136">如果 `recurse` 未指定参数，则方法只检索一级子级。</span><span class="sxs-lookup"><span data-stu-id="097a4-136">If the `recurse` parameter is not specified, the method retrieves only a single level of children.</span></span>

<span data-ttu-id="097a4-137">下面是此提供程序的[Containercmdletprovider. Getchilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)方法的实现。</span><span class="sxs-lookup"><span data-stu-id="097a4-137">Here is the implementation of the [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) method for this provider.</span></span> <span data-ttu-id="097a4-138">请注意，当路径指示 Access 数据库时，此方法将检索所有数据库表中的子项目，如果路径指示数据表，则从该表的行中检索子项。</span><span class="sxs-lookup"><span data-stu-id="097a4-138">Notice that this method retrieves the child items in all database tables when the path indicates the Access database, and retrieves the child items from the rows of that table if the path indicates a data table.</span></span>

```csharp
protected override void GetChildItems(string path, bool recurse)
{
    // If path represented is a drive then the children in the path are
    // tables. Hence all tables in the drive represented will have to be
    // returned
    if (PathIsDrive(path))
    {
        foreach (DatabaseTableInfo table in GetTables())
        {
            WriteItemObject(table, path, true);

            // if the specified item exists and recurse has been set then
            // all child items within it have to be obtained as well
            if (ItemExists(path) && recurse)
            {
                GetChildItems(path + pathSeparator + table.Name, recurse);
            }
        } // foreach (DatabaseTableInfo...
    } // if (PathIsDrive...
    else
    {
        // Get the table name, row number and type of path from the
        // path specified
        string tableName;
        int rowNumber;

        PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

        if (type == PathType.Table)
        {
            // Obtain all the rows within the table
            foreach (DatabaseRowInfo row in GetRows(tableName))
            {
                WriteItemObject(row, path + pathSeparator + row.RowNumber,
                        false);
            } // foreach (DatabaseRowInfo...
        }
        else if (type == PathType.Row)
        {
            // In this case the user has directly specified a row, hence
            // just give that particular row
            DatabaseRowInfo row = GetRow(tableName, rowNumber);
            WriteItemObject(row, path + pathSeparator + row.RowNumber,
                        false);
        }
        else
        {
            // In this case, the path specified is not valid
            ThrowTerminatingInvalidPathException(path);
        }
    } // else
} // GetChildItems
```

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs" range="311-362":::

#### <a name="things-to-remember-about-implementing-getchilditems"></a><span data-ttu-id="097a4-139">有关实现 GetChildItems 的注意事项</span><span class="sxs-lookup"><span data-stu-id="097a4-139">Things to Remember About Implementing GetChildItems</span></span>

<span data-ttu-id="097a4-140">以下情况可能适用于你的[Containercmdletprovider. Getchilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)实现：</span><span class="sxs-lookup"><span data-stu-id="097a4-140">The following conditions may apply to your implementation of [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems):</span></span>

- <span data-ttu-id="097a4-141">定义提供程序类时，Windows PowerShell 容器提供程序可能会声明 ExpandWildcards、Filter、Include 或 Exclude 的提供程序功能， [Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)枚举。</span><span class="sxs-lookup"><span data-stu-id="097a4-141">When defining the provider class, a Windows PowerShell container provider might declare provider capabilities of ExpandWildcards, Filter, Include, or Exclude, from the [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeration.</span></span> <span data-ttu-id="097a4-142">在这些情况下， [Containercmdletprovider. Getchilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)方法的实现需要确保传递给方法的路径满足指定的功能的要求。）。</span><span class="sxs-lookup"><span data-stu-id="097a4-142">In these cases, the implementation of the [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) method needs to ensure that the path passed to the method meets the requirements of the specified capabilities.</span></span> <span data-ttu-id="097a4-143">若要执行此操作，方法应访问相应的属性，例如， [Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude)和[Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include)属性中的相应属性，例如 ""。</span><span class="sxs-lookup"><span data-stu-id="097a4-143">To do this, the method should access the appropriate property, for example, the [System.Management.Automation.Provider.Cmdletprovider.Exclude\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) and [System.Management.Automation.Provider.Cmdletprovider.Include\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) properties.</span></span>

- <span data-ttu-id="097a4-144">此方法的实现应将对该项的任何形式的访问权限考虑到对用户可见的项。</span><span class="sxs-lookup"><span data-stu-id="097a4-144">The implementation of this method should take into account any form of access to the item that might make the item visible to the user.</span></span> <span data-ttu-id="097a4-145">例如，如果用户通过文件系统提供程序对文件的写入访问权限 (由 Windows PowerShell 提供) 但不是读取访问权限，则该文件仍然存在， [Itemexists \* 返回 Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) `true` 。</span><span class="sxs-lookup"><span data-stu-id="097a4-145">For example, if a user has write access to a file through the FileSystem provider (supplied by Windows PowerShell), but not read access, the file still exists and [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) returns `true`.</span></span> <span data-ttu-id="097a4-146">您的实现可能需要检查父项，以查看是否可以枚举子级。</span><span class="sxs-lookup"><span data-stu-id="097a4-146">Your implementation might require the checking of a parent item to see if the child can be enumerated.</span></span>

- <span data-ttu-id="097a4-147">写入多个项时， [Containercmdletprovider. Getchilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)方法可能需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="097a4-147">When writing multiple items, the [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) method can take some time.</span></span> <span data-ttu-id="097a4-148">你可以设计提供程序，以一次一个地使用[Cmdletprovider. Writeitemobject \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject)方法来编写项。</span><span class="sxs-lookup"><span data-stu-id="097a4-148">You can design your provider to write the items using the [System.Management.Automation.Provider.Cmdletprovider.Writeitemobject\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject) method one at a time.</span></span> <span data-ttu-id="097a4-149">使用此方法会向用户提供流中的项。</span><span class="sxs-lookup"><span data-stu-id="097a4-149">Using this technique will present the items to the user in a stream.</span></span>

- <span data-ttu-id="097a4-150">当存在循环链接时， [Containercmdletprovider. Getchilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)的实现会阻止无限递归，如所示。</span><span class="sxs-lookup"><span data-stu-id="097a4-150">Your implementation of [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) is responsible for preventing infinite recursion when there are circular links, and the like.</span></span> <span data-ttu-id="097a4-151">应该引发适当的终止异常来反映这种情况。</span><span class="sxs-lookup"><span data-stu-id="097a4-151">An appropriate terminating exception should be thrown to reflect such a condition.</span></span>

## <a name="attaching-dynamic-parameters-to-the-get-childitem-cmdlet"></a><span data-ttu-id="097a4-152">将动态参数附加到 Get-childitem Cmdlet</span><span class="sxs-lookup"><span data-stu-id="097a4-152">Attaching Dynamic Parameters to the Get-ChildItem Cmdlet</span></span>

<span data-ttu-id="097a4-153">有时 `Get-ChildItem` 调用[Containercmdletprovider. Getchilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)的 cmdlet 需要在运行时动态指定的其他参数。</span><span class="sxs-lookup"><span data-stu-id="097a4-153">Sometimes the `Get-ChildItem` cmdlet that calls [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) requires additional parameters that are specified dynamically at runtime.</span></span> <span data-ttu-id="097a4-154">若要提供这些动态参数，Windows PowerShell 容器提供程序必须实现[Containercmdletprovider. Getchilditemsdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters)方法。</span><span class="sxs-lookup"><span data-stu-id="097a4-154">To provide these dynamic parameters, the Windows PowerShell container provider must implement the [System.Management.Automation.Provider.Containercmdletprovider.Getchilditemsdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters) method.</span></span> <span data-ttu-id="097a4-155">此方法检索指定路径处的项的动态参数，并返回一个对象，该对象具有与 cmdlet 类或[Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)对象类似的分析特性的属性和字段。</span><span class="sxs-lookup"><span data-stu-id="097a4-155">This method retrieves dynamic parameters for the item at the indicated path and returns an object that has properties and fields with parsing attributes similar to a cmdlet class or a [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) object.</span></span> <span data-ttu-id="097a4-156">Windows PowerShell 运行时使用返回的对象将参数添加到 `Get-ChildItem` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="097a4-156">The Windows PowerShell runtime uses the returned object to add the parameters to the `Get-ChildItem` cmdlet.</span></span>

<span data-ttu-id="097a4-157">此 Windows PowerShell 容器提供程序未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="097a4-157">This Windows PowerShell container provider does not implement this method.</span></span> <span data-ttu-id="097a4-158">但是，下面的代码是此方法的默认实现。</span><span class="sxs-lookup"><span data-stu-id="097a4-158">However, the following code is the default implementation of this method.</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidergetchilditemsdynamicparameters](Msh_samplestestcmdlets#testprovidergetchilditemsdynamicparameters)]  -->

## <a name="retrieving-child-item-names"></a><span data-ttu-id="097a4-159">检索子项名称</span><span class="sxs-lookup"><span data-stu-id="097a4-159">Retrieving Child Item Names</span></span>

<span data-ttu-id="097a4-160">若要检索子项的名称，Windows PowerShell 容器提供程序必须重写[Containercmdletprovider Getchildnames](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames)方法，以便 `Get-ChildItem` 在指定了其参数时支持来自 cmdlet 的调用 `Name` 。</span><span class="sxs-lookup"><span data-stu-id="097a4-160">To retrieve the names of child items, the Windows PowerShell container provider must override the [System.Management.Automation.Provider.Containercmdletprovider.Getchildnames\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) method to support calls from the `Get-ChildItem` cmdlet when its `Name` parameter is specified.</span></span> <span data-ttu-id="097a4-161">如果指定了 cmdlet 的参数，则此方法将检索所有容器的指定路径或子项目名称的子项目的名称 `returnAllContainers` 。</span><span class="sxs-lookup"><span data-stu-id="097a4-161">This method retrieves the names of the child items for the specified path or child item names for all containers if the `returnAllContainers` parameter of the cmdlet is specified.</span></span> <span data-ttu-id="097a4-162">子名称是路径的叶部分。</span><span class="sxs-lookup"><span data-stu-id="097a4-162">A child name is the leaf portion of a path.</span></span> <span data-ttu-id="097a4-163">例如，路径 c:\windows\system32\abc.dll 的子名称为 "abc.dll"。</span><span class="sxs-lookup"><span data-stu-id="097a4-163">For example, the child name for the path c:\windows\system32\abc.dll is "abc.dll".</span></span> <span data-ttu-id="097a4-164">目录 c:\windows\system32 的子名称为 "system32"。</span><span class="sxs-lookup"><span data-stu-id="097a4-164">The child name for the directory c:\windows\system32 is "system32".</span></span>

<span data-ttu-id="097a4-165">下面是此提供程序的[Containercmdletprovider. Getchildnames \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames)方法的实现。</span><span class="sxs-lookup"><span data-stu-id="097a4-165">Here is the implementation of the [System.Management.Automation.Provider.Containercmdletprovider.Getchildnames\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) method for this provider.</span></span> <span data-ttu-id="097a4-166">请注意，如果指定的路径指示 Access 数据库 (驱动器) 和行号（如果路径指示表），则方法将检索表名称。</span><span class="sxs-lookup"><span data-stu-id="097a4-166">Notice that the method retrieves table names if the specified path indicates the Access database (drive) and row numbers if the path indicates a table.</span></span>

```csharp
protected override void GetChildNames(string path,
                            ReturnContainers returnContainers)
{
    // If the path represented is a drive, then the child items are
    // tables. get the names of all the tables in the drive.
    if (PathIsDrive(path))
    {
        foreach (DatabaseTableInfo table in GetTables())
        {
            WriteItemObject(table.Name, path, true);
        } // foreach (DatabaseTableInfo...
    } // if (PathIsDrive...
    else
    {
        // Get type, table name and row number from path specified
        string tableName;
        int rowNumber;

        PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

        if (type == PathType.Table)
        {
            // Get all the rows in the table and then write out the
            // row numbers.
            foreach (DatabaseRowInfo row in GetRows(tableName))
            {
                WriteItemObject(row.RowNumber, path, false);
            } // foreach (DatabaseRowInfo...
        }
        else if (type == PathType.Row)
        {
            // In this case the user has directly specified a row, hence
            // just give that particular row
            DatabaseRowInfo row = GetRow(tableName, rowNumber);

            WriteItemObject(row.RowNumber, path, false);
        }
        else
        {
            ThrowTerminatingInvalidPathException(path);
        }
    } // else
} // GetChildNames
```

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs" range="369-411":::

#### <a name="things-to-remember-about-implementing-getchildnames"></a><span data-ttu-id="097a4-167">有关实现 GetChildNames 的注意事项</span><span class="sxs-lookup"><span data-stu-id="097a4-167">Things to Remember About Implementing GetChildNames</span></span>

<span data-ttu-id="097a4-168">以下情况可能适用于你的[Containercmdletprovider. Getchilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)实现：</span><span class="sxs-lookup"><span data-stu-id="097a4-168">The following conditions may apply to your implementation of [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems):</span></span>

- <span data-ttu-id="097a4-169">定义提供程序类时，Windows PowerShell 容器提供程序可能会声明 ExpandWildcards、Filter、Include 或 Exclude 的提供程序功能， [Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)枚举。</span><span class="sxs-lookup"><span data-stu-id="097a4-169">When defining the provider class, a Windows PowerShell container provider might declare provider capabilities of ExpandWildcards, Filter, Include, or Exclude, from the [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeration.</span></span> <span data-ttu-id="097a4-170">在这些情况下， [Containercmdletprovider. Getchilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)方法的实现需要确保传递给方法的路径满足指定的功能的要求。）。</span><span class="sxs-lookup"><span data-stu-id="097a4-170">In these cases, the implementation of the [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) method needs to ensure that the path passed to the method meets the requirements of the specified capabilities.</span></span> <span data-ttu-id="097a4-171">若要执行此操作，方法应访问相应的属性，例如， [Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude)和[Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include)属性中的相应属性，例如 ""。</span><span class="sxs-lookup"><span data-stu-id="097a4-171">To do this, the method should access the appropriate property, for example, the [System.Management.Automation.Provider.Cmdletprovider.Exclude\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) and [System.Management.Automation.Provider.Cmdletprovider.Include\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) properties.</span></span>

  > [!NOTE]
  > <span data-ttu-id="097a4-172">当指定 cmdlet 的参数时，将发生此规则的例外情况 `returnAllContainers` 。</span><span class="sxs-lookup"><span data-stu-id="097a4-172">An exception to this rule occurs when the `returnAllContainers` parameter of the cmdlet is specified.</span></span> <span data-ttu-id="097a4-173">在这种情况下，该方法应检索某个容器的任何子名称，即使该名称与[Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Filter)\* 或[Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include)\* 或 Cmdletprovider \* 属性的值不匹配，也是如此。 [System.Management.Automation.Provider.Cmdletprovider.Exclude\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) \* 属性的值的值相同，则为。</span><span class="sxs-lookup"><span data-stu-id="097a4-173">In this case, the method should retrieve any child name for a container, even if it does not match the values of the [System.Management.Automation.Provider.Cmdletprovider.Filter\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Filter), [System.Management.Automation.Provider.Cmdletprovider.Include\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include), or [System.Management.Automation.Provider.Cmdletprovider.Exclude\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) properties.</span></span>

- <span data-ttu-id="097a4-174">默认情况下，除非指定了[Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)属性，否则此方法的重写不应检索用户通常隐藏的对象的名称。</span><span class="sxs-lookup"><span data-stu-id="097a4-174">By default, overrides of this method should not retrieve names of objects that are generally hidden from the user unless the [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) property is specified.</span></span> <span data-ttu-id="097a4-175">如果指定的路径指示一个容器，则不需要[Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)属性（& e）。</span><span class="sxs-lookup"><span data-stu-id="097a4-175">If the specified path indicates a container, the [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) property is not required.</span></span>

- <span data-ttu-id="097a4-176">当存在循环链接时， [Containercmdletprovider. Getchildnames \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames)的实现会阻止无限递归，如所示。</span><span class="sxs-lookup"><span data-stu-id="097a4-176">Your implementation of [System.Management.Automation.Provider.Containercmdletprovider.Getchildnames\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) is responsible for preventing infinite recursion when there are circular links, and the like.</span></span> <span data-ttu-id="097a4-177">应该引发适当的终止异常来反映这种情况。</span><span class="sxs-lookup"><span data-stu-id="097a4-177">An appropriate terminating exception should be thrown to reflect such a condition.</span></span>

## <a name="attaching-dynamic-parameters-to-the-get-childitem-cmdlet-name"></a><span data-ttu-id="097a4-178">将动态参数附加到 Get-childitem Cmdlet (名称) </span><span class="sxs-lookup"><span data-stu-id="097a4-178">Attaching Dynamic Parameters to the Get-ChildItem Cmdlet (Name)</span></span>

<span data-ttu-id="097a4-179">有时， `Get-ChildItem` 与 `Name` 参数)  (cmdlet 需要在运行时动态指定的其他参数。</span><span class="sxs-lookup"><span data-stu-id="097a4-179">Sometimes the `Get-ChildItem` cmdlet (with the `Name` parameter) requires additional parameters that are specified dynamically at runtime.</span></span> <span data-ttu-id="097a4-180">若要提供这些动态参数，Windows PowerShell 容器提供程序必须实现[Containercmdletprovider. Getchildnamesdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters)方法。</span><span class="sxs-lookup"><span data-stu-id="097a4-180">To provide these dynamic parameters, the Windows PowerShell container provider must implement the [System.Management.Automation.Provider.Containercmdletprovider.Getchildnamesdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters) method.</span></span> <span data-ttu-id="097a4-181">此方法检索指定路径处的项的动态参数，并返回一个对象，该对象具有与 cmdlet 类或[Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)对象类似的分析特性的属性和字段。</span><span class="sxs-lookup"><span data-stu-id="097a4-181">This method retrieves the dynamic parameters for the item at the indicated path and returns an object that has properties and fields with parsing attributes similar to a cmdlet class or a [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) object.</span></span> <span data-ttu-id="097a4-182">Windows PowerShell 运行时使用返回的对象将参数添加到 `Get-ChildItem` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="097a4-182">The Windows PowerShell runtime uses the returned object to add the parameters to the `Get-ChildItem` cmdlet.</span></span>

<span data-ttu-id="097a4-183">此提供程序未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="097a4-183">This provider does not implement this method.</span></span> <span data-ttu-id="097a4-184">但是，下面的代码是此方法的默认实现。</span><span class="sxs-lookup"><span data-stu-id="097a4-184">However, the following code is the default implementation of this method.</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidergetchildnamesdynamicparameters](Msh_samplestestcmdlets#testprovidergetchildnamesdynamicparameters)]  -->

## <a name="renaming-items"></a><span data-ttu-id="097a4-185">重命名项</span><span class="sxs-lookup"><span data-stu-id="097a4-185">Renaming Items</span></span>

<span data-ttu-id="097a4-186">若要重命名某个项，Windows PowerShell 容器提供程序必须重写[Containercmdletprovider. Renameitem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem)方法，以支持来自 cmdlet 的调用 `Rename-Item` 。</span><span class="sxs-lookup"><span data-stu-id="097a4-186">To rename an item, a Windows PowerShell container provider must override the [System.Management.Automation.Provider.Containercmdletprovider.Renameitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) method to support calls from the `Rename-Item` cmdlet.</span></span> <span data-ttu-id="097a4-187">此方法将指定路径处的项的名称更改为提供的新名称。</span><span class="sxs-lookup"><span data-stu-id="097a4-187">This method changes the name of the item at the specified path to the new name provided.</span></span> <span data-ttu-id="097a4-188">新名称必须始终相对于父项 (容器) 。</span><span class="sxs-lookup"><span data-stu-id="097a4-188">The new name must always be relative to the parent item (container).</span></span>

<span data-ttu-id="097a4-189">此提供程序不重写[Containercmdletprovider. Renameitem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem)方法。</span><span class="sxs-lookup"><span data-stu-id="097a4-189">This provider does not override the [System.Management.Automation.Provider.Containercmdletprovider.Renameitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) method.</span></span> <span data-ttu-id="097a4-190">但是，下面是默认实现。</span><span class="sxs-lookup"><span data-stu-id="097a4-190">However, the following is the default implementation.</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderrenameitem](Msh_samplestestcmdlets#testproviderrenameitem)]  -->

#### <a name="things-to-remember-about-implementing-renameitem"></a><span data-ttu-id="097a4-191">有关实现 RenameItem 的注意事项</span><span class="sxs-lookup"><span data-stu-id="097a4-191">Things to Remember About Implementing RenameItem</span></span>

<span data-ttu-id="097a4-192">以下情况可能适用于你的[Containercmdletprovider. Renameitem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem)实现：</span><span class="sxs-lookup"><span data-stu-id="097a4-192">The following conditions may apply to your implementation of [System.Management.Automation.Provider.Containercmdletprovider.Renameitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem):</span></span>

- <span data-ttu-id="097a4-193">定义提供程序类时，Windows PowerShell 容器提供程序可能会声明 ExpandWildcards、Filter、Include 或 Exclude 的提供程序功能， [Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)枚举。</span><span class="sxs-lookup"><span data-stu-id="097a4-193">When defining the provider class, a Windows PowerShell container provider might declare provider capabilities of ExpandWildcards, Filter, Include, or Exclude, from the [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeration.</span></span> <span data-ttu-id="097a4-194">在这些情况下， [Containercmdletprovider. Getchilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)方法的实现需要确保传递给方法的路径满足指定的功能的要求。）。</span><span class="sxs-lookup"><span data-stu-id="097a4-194">In these cases, the implementation of the [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) method needs to ensure that the path passed to the method meets the requirements of the specified capabilities.</span></span> <span data-ttu-id="097a4-195">若要执行此操作，方法应访问相应的属性，例如， [Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude)和[Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include)属性中的相应属性，例如 ""。</span><span class="sxs-lookup"><span data-stu-id="097a4-195">To do this, the method should access the appropriate property, for example, the [System.Management.Automation.Provider.Cmdletprovider.Exclude\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) and [System.Management.Automation.Provider.Cmdletprovider.Include\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) properties.</span></span>

- <span data-ttu-id="097a4-196">[Containercmdletprovider. Renameitem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem)方法仅用于修改某个项的名称，而不是用于移动操作的修改。</span><span class="sxs-lookup"><span data-stu-id="097a4-196">The [System.Management.Automation.Provider.Containercmdletprovider.Renameitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) method is intended for the modification of the name of an item only, and not for move operations.</span></span>
  <span data-ttu-id="097a4-197">如果参数包含路径分隔符，则方法的实现应写入错误 `newName` ，否则可能导致项更改其父位置。</span><span class="sxs-lookup"><span data-stu-id="097a4-197">Your implementation of the method should write an error if the `newName` parameter contains path separators, or might otherwise cause the item to change its parent location.</span></span>

- <span data-ttu-id="097a4-198">默认情况下，除非指定了[Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)属性，否则此方法的重写不应重命名对象。</span><span class="sxs-lookup"><span data-stu-id="097a4-198">By default, overrides of this method should not rename objects unless the [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) property is specified.</span></span> <span data-ttu-id="097a4-199">如果指定的路径指示一个容器，则不需要[Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)属性（& e）。</span><span class="sxs-lookup"><span data-stu-id="097a4-199">If the specified path indicates a container, the [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) property is not required.</span></span>

- <span data-ttu-id="097a4-200">在对数据存储进行任何更改之前，你的[Containercmdletprovider 和 Renameitem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem)方法的实现应调用[Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) ，并检查其返回值，然后再进行更改。</span><span class="sxs-lookup"><span data-stu-id="097a4-200">Your implementation of the [System.Management.Automation.Provider.Containercmdletprovider.Renameitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) method should call [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) and check its return value before making any changes to the data store.</span></span> <span data-ttu-id="097a4-201">此方法用于在对系统状态进行更改时（例如，重命名文件）确认操作的执行。</span><span class="sxs-lookup"><span data-stu-id="097a4-201">This method is used to confirm execution of an operation when a change is made to system state, for example, renaming files.</span></span>
  <span data-ttu-id="097a4-202">[Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)发送要更改为用户的资源的名称，Windows PowerShell 运行时在确定应显示的内容时考虑了任何命令行设置或首选项变量。</span><span class="sxs-lookup"><span data-stu-id="097a4-202">[System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) sends the name of the resource to be changed to the user, with the Windows PowerShell runtime taking into account any command line settings or preference variables in determining what should be displayed.</span></span>

  <span data-ttu-id="097a4-203">在对 Cmdletprovider 的调用返回后， [ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)方法 `true` 应调用[Containercmdletprovider。 Renameitem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem)方法应调用. Cmdletprovider 方法的[调用方的](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue)调用程序的调用程序的。</span><span class="sxs-lookup"><span data-stu-id="097a4-203">After the call to [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) returns `true`, the [System.Management.Automation.Provider.Containercmdletprovider.Renameitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) method should call the [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) method.</span></span> <span data-ttu-id="097a4-204">此方法向用户发送一条确认消息，以允许其他反馈显示是否应继续进行操作。</span><span class="sxs-lookup"><span data-stu-id="097a4-204">This method sends a message a confirmation message to the user to allow additional feedback to say if the operation should be continued.</span></span> <span data-ttu-id="097a4-205">提供程序应调用[Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue)作为额外检查来检查是否存在潜在的危险系统修改。</span><span class="sxs-lookup"><span data-stu-id="097a4-205">A provider should call [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) as an additional check for potentially dangerous system modifications.</span></span>

## <a name="attaching-dynamic-parameters-to-the-rename-item-cmdlet"></a><span data-ttu-id="097a4-206">将动态参数附加到重命名项 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="097a4-206">Attaching Dynamic Parameters to the Rename-Item Cmdlet</span></span>

<span data-ttu-id="097a4-207">有时，该 `Rename-Item` cmdlet 需要在运行时动态指定的其他参数。</span><span class="sxs-lookup"><span data-stu-id="097a4-207">Sometimes the `Rename-Item` cmdlet requires additional parameters that are specified dynamically at runtime.</span></span> <span data-ttu-id="097a4-208">若要提供这些动态参数，Windows PowerShell 容器提供程序必须实现[Containercmdletprovider. Renameitemdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters)方法。</span><span class="sxs-lookup"><span data-stu-id="097a4-208">To provide these dynamic parameters, Windows PowerShell container provider must implement the [System.Management.Automation.Provider.Containercmdletprovider.Renameitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters) method.</span></span> <span data-ttu-id="097a4-209">此方法检索指定路径处的项的参数，并返回一个对象，该对象具有与 cmdlet 类或[Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)对象类似的分析特性的属性和字段。</span><span class="sxs-lookup"><span data-stu-id="097a4-209">This method retrieves the parameters for the item at the indicated path and returns an object that has properties and fields with parsing attributes similar to a cmdlet class or a [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) object.</span></span> <span data-ttu-id="097a4-210">Windows PowerShell 运行时使用返回的对象将参数添加到 `Rename-Item` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="097a4-210">The Windows PowerShell runtime uses the returned object to add the parameters to the `Rename-Item` cmdlet.</span></span>

<span data-ttu-id="097a4-211">此容器提供程序不实现此方法。</span><span class="sxs-lookup"><span data-stu-id="097a4-211">This container provider does not implement this method.</span></span> <span data-ttu-id="097a4-212">但是，下面的代码是此方法的默认实现。</span><span class="sxs-lookup"><span data-stu-id="097a4-212">However, the following code is the default implementation of this method.</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderrenameitemdynamicparameters](Msh_samplestestcmdlets#testproviderrenameitemdynamicparameters)]  -->

## <a name="creating-new-items"></a><span data-ttu-id="097a4-213">正在创建新项</span><span class="sxs-lookup"><span data-stu-id="097a4-213">Creating New Items</span></span>

<span data-ttu-id="097a4-214">若要创建新项，容器提供程序必须实现[Containercmdletprovider. Newitem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)方法，以支持来自 cmdlet 的调用 `New-Item` 。</span><span class="sxs-lookup"><span data-stu-id="097a4-214">To create new items, a container provider must implement the [System.Management.Automation.Provider.Containercmdletprovider.Newitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) method to support calls from the `New-Item` cmdlet.</span></span> <span data-ttu-id="097a4-215">此方法创建位于指定路径的数据项。</span><span class="sxs-lookup"><span data-stu-id="097a4-215">This method creates a data item located at the specified path.</span></span> <span data-ttu-id="097a4-216">`type`Cmdlet 的参数包含用于新项的提供程序定义的类型。</span><span class="sxs-lookup"><span data-stu-id="097a4-216">The `type` parameter of the cmdlet contains the provider-defined type for the new item.</span></span> <span data-ttu-id="097a4-217">例如，FileSystem 提供程序使用值为 `type` "file" 或 "directory" 的参数。</span><span class="sxs-lookup"><span data-stu-id="097a4-217">For example, the FileSystem provider uses a `type` parameter with a value of "file" or "directory".</span></span> <span data-ttu-id="097a4-218">`newItemValue`Cmdlet 的参数为新项指定特定于提供程序的值。</span><span class="sxs-lookup"><span data-stu-id="097a4-218">The `newItemValue` parameter of the cmdlet specifies a provider-specific value for the new item.</span></span>

<span data-ttu-id="097a4-219">下面是此提供程序的[Containercmdletprovider. Newitem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)方法的实现。</span><span class="sxs-lookup"><span data-stu-id="097a4-219">Here is the implementation of the [System.Management.Automation.Provider.Containercmdletprovider.Newitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) method for this provider.</span></span>

```csharp
protected override void NewItem( string path, string type, object newItemValue )
{
    // Create the new item here after
    // performing necessary validations
    //
    // WriteItemObject(newItemValue, path, false);

    // Example
    //
    // if (ShouldProcess(path, "new item"))
    // {
    //      // Create a new item and then call WriteObject
    //      WriteObject(newItemValue, path, false);
    // }

} // NewItem
```

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs" range="939-955":::

#### <a name="things-to-remember-about-implementing-newitem"></a><span data-ttu-id="097a4-220">有关实现 NewItem 的注意事项</span><span class="sxs-lookup"><span data-stu-id="097a4-220">Things to Remember About Implementing NewItem</span></span>

<span data-ttu-id="097a4-221">以下情况可能适用于你的[Containercmdletprovider. Newitem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)实现：</span><span class="sxs-lookup"><span data-stu-id="097a4-221">The following conditions may apply to your implementation of [System.Management.Automation.Provider.Containercmdletprovider.Newitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem):</span></span>

- <span data-ttu-id="097a4-222">[Containercmdletprovider. Newitem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)方法应执行在参数中传递的字符串的不区分大小写的比较 `type` 。</span><span class="sxs-lookup"><span data-stu-id="097a4-222">The [System.Management.Automation.Provider.Containercmdletprovider.Newitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) method should perform a case-insensitive comparison of the string passed in the `type` parameter.</span></span>
  <span data-ttu-id="097a4-223">它还应允许最小不明确匹配。</span><span class="sxs-lookup"><span data-stu-id="097a4-223">It should also allow for least ambiguous matches.</span></span> <span data-ttu-id="097a4-224">例如，对于类型 "file" 和 "directory"，只需第一个字母来消除歧义。</span><span class="sxs-lookup"><span data-stu-id="097a4-224">For example, for the types "file" and "directory", only the first letter is required to disambiguate.</span></span> <span data-ttu-id="097a4-225">如果 `type` 参数指示提供程序无法创建的类型，则[Containercmdletprovider. Newitem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)方法应使用指示提供程序可以创建的类型的消息编写 ArgumentException。</span><span class="sxs-lookup"><span data-stu-id="097a4-225">If the `type` parameter indicates a type your provider cannot create, the [System.Management.Automation.Provider.Containercmdletprovider.Newitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) method should write an ArgumentException with a message indicating the types the provider can create.</span></span>

- <span data-ttu-id="097a4-226">对于 `newItemValue` 参数，建议使用[Containercmdletprovider. Newitem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)方法的实现来接受至少一个字符串的字符串。</span><span class="sxs-lookup"><span data-stu-id="097a4-226">For the `newItemValue` parameter, the implementation of the [System.Management.Automation.Provider.Containercmdletprovider.Newitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) method is recommended to accept strings at a minimum.</span></span> <span data-ttu-id="097a4-227">它还应接受由[Itemcmdletprovider. Getitem \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem)方法为同一路径检索的对象的类型的对象。</span><span class="sxs-lookup"><span data-stu-id="097a4-227">It should also accept the type of object that is retrieved by the [System.Management.Automation.Provider.Itemcmdletprovider.Getitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) method for the same path.</span></span> <span data-ttu-id="097a4-228">[Containercmdletprovider. Newitem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)方法可以使用[languageprimitives.physicalequality. convertto-html \*](/dotnet/api/System.Management.Automation.LanguagePrimitives.ConvertTo)方法将类型转换为所需的类型（& i）。</span><span class="sxs-lookup"><span data-stu-id="097a4-228">The [System.Management.Automation.Provider.Containercmdletprovider.Newitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) method can use the [System.Management.Automation.Languageprimitives.Convertto\*](/dotnet/api/System.Management.Automation.LanguagePrimitives.ConvertTo) method to convert types to the desired type.</span></span>

- <span data-ttu-id="097a4-229">在对数据存储进行任何更改之前，你的[Containercmdletprovider 和 Newitem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)方法的实现应调用[Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) ，并检查其返回值，然后再进行更改。</span><span class="sxs-lookup"><span data-stu-id="097a4-229">Your implementation of the [System.Management.Automation.Provider.Containercmdletprovider.Newitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) method should call [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) and check its return value before making any changes to the data store.</span></span> <span data-ttu-id="097a4-230">在对 Cmdletprovider 的调用返回 true 后，ShouldProcess[方法应](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue)调用[System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)方法作为额外的检查，以应对潜在的危险系统修改情况进行检查，然后再调用[Containercmdletprovider. Newitem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)方法，则为。</span><span class="sxs-lookup"><span data-stu-id="097a4-230">After the call to [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) returns true, the [System.Management.Automation.Provider.Containercmdletprovider.Newitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) method should call the [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) method as an additional check for potentially dangerous system modifications.</span></span>

## <a name="attaching-dynamic-parameters-to-the-new-item-cmdlet"></a><span data-ttu-id="097a4-231">将动态参数附加到新项 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="097a4-231">Attaching Dynamic Parameters to the New-Item Cmdlet</span></span>

<span data-ttu-id="097a4-232">有时，该 `New-Item` cmdlet 需要在运行时动态指定的其他参数。</span><span class="sxs-lookup"><span data-stu-id="097a4-232">Sometimes the `New-Item` cmdlet requires additional parameters that are specified dynamically at runtime.</span></span> <span data-ttu-id="097a4-233">为了提供这些动态参数，容器提供程序必须实现[Containercmdletprovider. Newitemdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItemDynamicParameters)方法。</span><span class="sxs-lookup"><span data-stu-id="097a4-233">To provide these dynamic parameters, the container provider must implement the [System.Management.Automation.Provider.Containercmdletprovider.Newitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItemDynamicParameters) method.</span></span> <span data-ttu-id="097a4-234">此方法检索指定路径处的项的参数，并返回一个对象，该对象具有与 cmdlet 类或[Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)对象类似的分析特性的属性和字段。</span><span class="sxs-lookup"><span data-stu-id="097a4-234">This method retrieves the parameters for the item at the indicated path and returns an object that has properties and fields with parsing attributes similar to a cmdlet class or a [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) object.</span></span> <span data-ttu-id="097a4-235">Windows PowerShell 运行时使用返回的对象将参数添加到 `New-Item` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="097a4-235">The Windows PowerShell runtime uses the returned object to add the parameters to the `New-Item` cmdlet.</span></span>

<span data-ttu-id="097a4-236">此提供程序未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="097a4-236">This provider does not implement this method.</span></span> <span data-ttu-id="097a4-237">但是，下面的代码是此方法的默认实现。</span><span class="sxs-lookup"><span data-stu-id="097a4-237">However, the following code is the default implementation of this method.</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidernewitemdynamicparameters](Msh_samplestestcmdlets#testprovidernewitemdynamicparameters)]  -->

## <a name="removing-items"></a><span data-ttu-id="097a4-238">删除项</span><span class="sxs-lookup"><span data-stu-id="097a4-238">Removing Items</span></span>

<span data-ttu-id="097a4-239">若要删除项，Windows PowerShell 提供程序必须重写[Containercmdletprovider. Removeitem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem)方法，以支持来自 cmdlet 的调用 `Remove-Item` 。</span><span class="sxs-lookup"><span data-stu-id="097a4-239">To remove items, the Windows PowerShell provider must override the [System.Management.Automation.Provider.Containercmdletprovider.Removeitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) method to support calls from the `Remove-Item` cmdlet.</span></span> <span data-ttu-id="097a4-240">此方法从数据存储区中的指定路径删除一个项。</span><span class="sxs-lookup"><span data-stu-id="097a4-240">This method deletes an item from the data store at the specified path.</span></span> <span data-ttu-id="097a4-241">如果 `recurse` 将 cmdlet 的参数 `Remove-Item` 设置为 `true` ，则方法将删除所有子项，而不考虑它们的级别。</span><span class="sxs-lookup"><span data-stu-id="097a4-241">If the `recurse` parameter of the `Remove-Item` cmdlet is set to `true`, the method removes all child items regardless of their level.</span></span> <span data-ttu-id="097a4-242">如果将参数设置为 `false` ，则方法只删除指定路径中的单个项。</span><span class="sxs-lookup"><span data-stu-id="097a4-242">If the parameter is set to `false`, the method removes only a single item at the specified path.</span></span>

<span data-ttu-id="097a4-243">此提供程序不支持删除项。</span><span class="sxs-lookup"><span data-stu-id="097a4-243">This provider does not support item removal.</span></span> <span data-ttu-id="097a4-244">但是，下面的代码是[Containercmdletprovider. Removeitem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem)的默认实现。</span><span class="sxs-lookup"><span data-stu-id="097a4-244">However, the following code is the default implementation of [System.Management.Automation.Provider.Containercmdletprovider.Removeitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem).</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderremoveitem](Msh_samplestestcmdlets#testproviderremoveitem)]  -->

#### <a name="things-to-remember-about-implementing-removeitem"></a><span data-ttu-id="097a4-245">有关实现 RemoveItem 的注意事项</span><span class="sxs-lookup"><span data-stu-id="097a4-245">Things to Remember About Implementing RemoveItem</span></span>

<span data-ttu-id="097a4-246">以下情况可能适用于你的[Containercmdletprovider. Newitem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)实现：</span><span class="sxs-lookup"><span data-stu-id="097a4-246">The following conditions may apply to your implementation of [System.Management.Automation.Provider.Containercmdletprovider.Newitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem):</span></span>

- <span data-ttu-id="097a4-247">定义提供程序类时，Windows PowerShell 容器提供程序可能会声明 ExpandWildcards、Filter、Include 或 Exclude 的提供程序功能， [Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)枚举。</span><span class="sxs-lookup"><span data-stu-id="097a4-247">When defining the provider class, a Windows PowerShell container provider might declare provider capabilities of ExpandWildcards, Filter, Include, or Exclude, from the [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeration.</span></span> <span data-ttu-id="097a4-248">在这些情况下， [Containercmdletprovider. Getchilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)方法的实现需要确保传递给方法的路径满足指定的功能的要求。）。</span><span class="sxs-lookup"><span data-stu-id="097a4-248">In these cases, the implementation of the [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) method needs to ensure that the path passed to the method meets the requirements of the specified capabilities.</span></span> <span data-ttu-id="097a4-249">若要执行此操作，方法应访问相应的属性，例如， [Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude)和[Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include)属性中的相应属性，例如 ""。</span><span class="sxs-lookup"><span data-stu-id="097a4-249">To do this, the method should access the appropriate property, for example, the [System.Management.Automation.Provider.Cmdletprovider.Exclude\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) and [System.Management.Automation.Provider.Cmdletprovider.Include\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) properties.</span></span>

- <span data-ttu-id="097a4-250">默认情况下，除非[Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)属性设置为 true，否则此方法的重写不应删除对象。</span><span class="sxs-lookup"><span data-stu-id="097a4-250">By default, overrides of this method should not remove objects unless the [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) property is set to true.</span></span> <span data-ttu-id="097a4-251">如果指定的路径指示一个容器，则不需要[Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)属性（& e）。</span><span class="sxs-lookup"><span data-stu-id="097a4-251">If the specified path indicates a container, the [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) property is not required.</span></span>

- <span data-ttu-id="097a4-252">当存在循环链接时， [Containercmdletprovider. Removeitem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem)的实现会阻止无限递归，如所示。</span><span class="sxs-lookup"><span data-stu-id="097a4-252">Your implementation of [System.Management.Automation.Provider.Containercmdletprovider.Removeitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) is responsible for preventing infinite recursion when there are circular links, and the like.</span></span> <span data-ttu-id="097a4-253">应该引发适当的终止异常来反映这种情况。</span><span class="sxs-lookup"><span data-stu-id="097a4-253">An appropriate terminating exception should be thrown to reflect such a condition.</span></span>

- <span data-ttu-id="097a4-254">在对数据存储进行任何更改之前，你的[Containercmdletprovider 和 Removeitem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem)方法的实现应调用[Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) ，并检查其返回值，然后再进行更改。</span><span class="sxs-lookup"><span data-stu-id="097a4-254">Your implementation of the [System.Management.Automation.Provider.Containercmdletprovider.Removeitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) method should call [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) and check its return value before making any changes to the data store.</span></span> <span data-ttu-id="097a4-255">对[Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)的调用返回后 `true` ， [Containercmdletprovider. Removeitem \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem)方法应调用 ShouldProcess 方法作为额外的检查，以检查是否存在潜在的危险系统修改的情况下出现[System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue)的其他检查内容。），则</span><span class="sxs-lookup"><span data-stu-id="097a4-255">After the call to [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) returns `true`, the [System.Management.Automation.Provider.Containercmdletprovider.Removeitem\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) method should call the [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) method as an additional check for potentially dangerous system modifications.</span></span>

## <a name="attaching-dynamic-parameters-to-the-remove-item-cmdlet"></a><span data-ttu-id="097a4-256">将动态参数附加到移除项 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="097a4-256">Attaching Dynamic Parameters to the Remove-Item Cmdlet</span></span>

<span data-ttu-id="097a4-257">有时，该 `Remove-Item` cmdlet 需要在运行时动态指定的其他参数。</span><span class="sxs-lookup"><span data-stu-id="097a4-257">Sometimes the `Remove-Item` cmdlet requires additional parameters that are specified dynamically at runtime.</span></span> <span data-ttu-id="097a4-258">为了提供这些动态参数，容器提供程序必须实现[Containercmdletprovider. Removeitemdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters)方法来处理这些参数。</span><span class="sxs-lookup"><span data-stu-id="097a4-258">To provide these dynamic parameters, the container provider must implement the [System.Management.Automation.Provider.Containercmdletprovider.Removeitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters) method to handle these parameters.</span></span> <span data-ttu-id="097a4-259">此方法检索指定路径处的项的动态参数，并返回一个对象，该对象具有与 cmdlet 类或[Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)对象类似的分析特性的属性和字段。</span><span class="sxs-lookup"><span data-stu-id="097a4-259">This method retrieves the dynamic parameters for the item at the indicated path and returns an object that has properties and fields with parsing attributes similar to a cmdlet class or a [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) object.</span></span> <span data-ttu-id="097a4-260">Windows PowerShell 运行时使用返回的对象将参数添加到 `Remove-Item` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="097a4-260">The Windows PowerShell runtime uses the returned object to add the parameters to the `Remove-Item` cmdlet.</span></span>

<span data-ttu-id="097a4-261">此容器提供程序不实现此方法。</span><span class="sxs-lookup"><span data-stu-id="097a4-261">This container provider does not implement this method.</span></span> <span data-ttu-id="097a4-262">但是，下面的代码是[Containercmdletprovider. Removeitemdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters)的默认实现。</span><span class="sxs-lookup"><span data-stu-id="097a4-262">However, the following code is the default implementation of [System.Management.Automation.Provider.Containercmdletprovider.Removeitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters).</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderremoveitemdynamicparameters](Msh_samplestestcmdlets#testproviderremoveitemdynamicparameters)]  -->

## <a name="querying-for-child-items"></a><span data-ttu-id="097a4-263">查询子项</span><span class="sxs-lookup"><span data-stu-id="097a4-263">Querying for Child Items</span></span>

<span data-ttu-id="097a4-264">若要检查子项目是否存在于指定的路径，Windows PowerShell 容器提供程序必须重写[Containercmdletprovider. Haschilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems)方法。</span><span class="sxs-lookup"><span data-stu-id="097a4-264">To check to see if child items exist at the specified path, the Windows PowerShell container provider must override the [System.Management.Automation.Provider.Containercmdletprovider.Haschilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems) method.</span></span> <span data-ttu-id="097a4-265">`true`如果项具有子级，则此方法将返回， `false` 否则返回。</span><span class="sxs-lookup"><span data-stu-id="097a4-265">This method returns `true` if the item has children, and `false` otherwise.</span></span> <span data-ttu-id="097a4-266">对于 null 或空路径，方法会将数据存储区中的所有项视为子级，并返回 `true` 。</span><span class="sxs-lookup"><span data-stu-id="097a4-266">For a null or empty path, the method considers any items in the data store to be children and returns `true`.</span></span>

<span data-ttu-id="097a4-267">下面是对[Containercmdletprovider. Haschilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems)方法的重写。</span><span class="sxs-lookup"><span data-stu-id="097a4-267">Here is the override for the [System.Management.Automation.Provider.Containercmdletprovider.Haschilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems) method.</span></span> <span data-ttu-id="097a4-268">如果 ChunkPath helper 方法创建了两个以上的路径部分，则该方法将返回 `false` ，因为只定义了一个数据库容器和一个表容器。</span><span class="sxs-lookup"><span data-stu-id="097a4-268">If there are more than two path parts created by the ChunkPath helper method, the method returns `false`, since only a database container and a table container are defined.</span></span> <span data-ttu-id="097a4-269">有关此帮助器方法的详细信息，请参阅[创建 Windows PowerShell 项提供程序](./creating-a-windows-powershell-item-provider.md)中介绍的 ChunkPath 方法。</span><span class="sxs-lookup"><span data-stu-id="097a4-269">For more information about this helper method, see the ChunkPath method is discussed in [Creating a Windows PowerShell Item Provider](./creating-a-windows-powershell-item-provider.md).</span></span>

```csharp
protected override bool HasChildItems( string path )
{
    return false;
} // HasChildItems
```

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs" range="1094-1097":::

#### <a name="things-to-remember-about-implementing-haschilditems"></a><span data-ttu-id="097a4-270">有关实现 HasChildItems 的注意事项</span><span class="sxs-lookup"><span data-stu-id="097a4-270">Things to Remember About Implementing HasChildItems</span></span>

<span data-ttu-id="097a4-271">以下情况可能适用于你的[Containercmdletprovider. Haschilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems)实现：</span><span class="sxs-lookup"><span data-stu-id="097a4-271">The following conditions may apply to your implementation of [System.Management.Automation.Provider.Containercmdletprovider.Haschilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems):</span></span>

- <span data-ttu-id="097a4-272">如果容器提供程序公开包含所需的装入点的根，则当为路径传递了 null 或空字符串时， [Containercmdletprovider。 Haschilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems)方法的实现应返回。 `true`</span><span class="sxs-lookup"><span data-stu-id="097a4-272">If the container provider exposes a root that contains interesting mount points, the implementation of the [System.Management.Automation.Provider.Containercmdletprovider.Haschilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems) method should return `true` when a null or an empty string is passed in for the path.</span></span>

## <a name="copying-items"></a><span data-ttu-id="097a4-273">复制项</span><span class="sxs-lookup"><span data-stu-id="097a4-273">Copying Items</span></span>

<span data-ttu-id="097a4-274">若要复制项，容器提供程序必须实现[ContainerCmdletProvider. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)方法以支持来自 cmdlet 的调用 `Copy-Item` 。</span><span class="sxs-lookup"><span data-stu-id="097a4-274">To copy items, the container provider must implement the [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) method to support calls from the `Copy-Item` cmdlet.</span></span> <span data-ttu-id="097a4-275">此方法将数据项从 cmdlet 的参数指示的位置复制 `path` 到参数指示的位置 `copyPath` 。</span><span class="sxs-lookup"><span data-stu-id="097a4-275">This method copies a data item from the location indicated by the `path` parameter of the cmdlet to the location indicated by the `copyPath` parameter.</span></span> <span data-ttu-id="097a4-276">如果 `recurse` 指定了参数，则该方法将复制所有子容器。</span><span class="sxs-lookup"><span data-stu-id="097a4-276">If the `recurse` parameter is specified, the method copies all sub-containers.</span></span> <span data-ttu-id="097a4-277">如果未指定参数，则方法只复制单个级别的项。</span><span class="sxs-lookup"><span data-stu-id="097a4-277">If the parameter is not specified, the method copies only a single level of items.</span></span>

<span data-ttu-id="097a4-278">此提供程序未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="097a4-278">This provider does not implement this method.</span></span> <span data-ttu-id="097a4-279">但是，下面的代码是[ContainerCmdletProvider. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)的默认实现。</span><span class="sxs-lookup"><span data-stu-id="097a4-279">However, the following code is the default implementation of [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem).</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidercopyitem](Msh_samplestestcmdlets#testprovidercopyitem)]  -->

#### <a name="things-to-remember-about-implementing-copyitem"></a><span data-ttu-id="097a4-280">有关实现 CopyItem 的注意事项</span><span class="sxs-lookup"><span data-stu-id="097a4-280">Things to Remember About Implementing CopyItem</span></span>

<span data-ttu-id="097a4-281">以下情况可能适用于你的 ContainerCmdletProvider 的实现。 [CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)：</span><span class="sxs-lookup"><span data-stu-id="097a4-281">The following conditions may apply to your implementation of [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem):</span></span>

- <span data-ttu-id="097a4-282">定义提供程序类时，Windows PowerShell 容器提供程序可能会声明 ExpandWildcards、Filter、Include 或 Exclude 的提供程序功能， [Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)枚举。</span><span class="sxs-lookup"><span data-stu-id="097a4-282">When defining the provider class, a Windows PowerShell container provider might declare provider capabilities of ExpandWildcards, Filter, Include, or Exclude, from the [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeration.</span></span> <span data-ttu-id="097a4-283">在这些情况下， [Containercmdletprovider. Getchilditems \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)方法的实现需要确保传递给方法的路径满足指定的功能的要求。）。</span><span class="sxs-lookup"><span data-stu-id="097a4-283">In these cases, the implementation of the [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) method needs to ensure that the path passed to the method meets the requirements of the specified capabilities.</span></span> <span data-ttu-id="097a4-284">若要执行此操作，方法应访问相应的属性，例如， [Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude)和[Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include)属性中的相应属性，例如 ""。</span><span class="sxs-lookup"><span data-stu-id="097a4-284">To do this, the method should access the appropriate property, for example, the [System.Management.Automation.Provider.Cmdletprovider.Exclude\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) and [System.Management.Automation.Provider.Cmdletprovider.Include\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Include) properties.</span></span>

- <span data-ttu-id="097a4-285">默认情况下，此方法的重写不应将对象复制到现有对象上，除非[Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)属性设置为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="097a4-285">By default, overrides of this method should not copy objects over existing objects unless the [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) property is set to `true`.</span></span> <span data-ttu-id="097a4-286">例如，FileSystem 提供程序将不会通过现有 c:\abc.txt 文件复制 c:\temp\abc.txt，除非[Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)属性被设置为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="097a4-286">For example, the FileSystem provider will not copy c:\temp\abc.txt over an existing c:\abc.txt file unless the [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) property is set to `true`.</span></span> <span data-ttu-id="097a4-287">如果在参数中指定的路径 `copyPath` 存在，并指示一个容器，则不需要[Cmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)属性。</span><span class="sxs-lookup"><span data-stu-id="097a4-287">If the path specified in the `copyPath` parameter exists and indicates a container, the [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) property is not required.</span></span> <span data-ttu-id="097a4-288">在这种情况下， [ContainerCmdletProvider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)应将由参数指示的项复制 `path` 到参数所指示的 `copyPath` 子容器。</span><span class="sxs-lookup"><span data-stu-id="097a4-288">In this case, [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) should copy the item indicated by the `path` parameter to the container indicated by the `copyPath` parameter as a child.</span></span>

- <span data-ttu-id="097a4-289">当存在循环链接时，你的[ContainerCmdletProvider CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)的实现负责阻止无限递归，如所示。</span><span class="sxs-lookup"><span data-stu-id="097a4-289">Your implementation of [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) is responsible for preventing infinite recursion when there are circular links, and the like.</span></span> <span data-ttu-id="097a4-290">应该引发适当的终止异常来反映这种情况。</span><span class="sxs-lookup"><span data-stu-id="097a4-290">An appropriate terminating exception should be thrown to reflect such a condition.</span></span>

- <span data-ttu-id="097a4-291">在对数据存储进行任何更改之前，你的[ContainerCmdletProvider CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)方法的实现应调用[Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) ，并检查其返回值，然后再进行更改。</span><span class="sxs-lookup"><span data-stu-id="097a4-291">Your implementation of the [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) method should call [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) and check its return value before making any changes to the data store.</span></span> <span data-ttu-id="097a4-292">在对 Cmdletprovider 的调用返回 true 后，ShouldProcess 方法应调用[System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)方法作为额外的检查，以检查是否存在潜在的危险系统修改的情况下出现的其他[检查功能。](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) ） [。 "。](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)</span><span class="sxs-lookup"><span data-stu-id="097a4-292">After the call to [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) returns true, the [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) method should call the [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) method as an additional check for potentially dangerous system modifications.</span></span> <span data-ttu-id="097a4-293">有关调用这些方法的详细信息，请参阅[Rename 项](#renaming-items)。</span><span class="sxs-lookup"><span data-stu-id="097a4-293">For more information about calling these methods, see [Rename Items](#renaming-items).</span></span>

## <a name="attaching-dynamic-parameters-to-the-copy-item-cmdlet"></a><span data-ttu-id="097a4-294">将动态参数附加到复制项 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="097a4-294">Attaching Dynamic Parameters to the Copy-Item Cmdlet</span></span>

<span data-ttu-id="097a4-295">有时，该 `Copy-Item` cmdlet 需要在运行时动态指定的其他参数。</span><span class="sxs-lookup"><span data-stu-id="097a4-295">Sometimes the `Copy-Item` cmdlet requires additional parameters that are specified dynamically at runtime.</span></span> <span data-ttu-id="097a4-296">为了提供这些动态参数，Windows PowerShell 容器提供程序必须实现[Containercmdletprovider. Copyitemdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters)方法来处理这些参数。</span><span class="sxs-lookup"><span data-stu-id="097a4-296">To provide these dynamic parameters, the Windows PowerShell container provider must implement the [System.Management.Automation.Provider.Containercmdletprovider.Copyitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters) method to handle these parameters.</span></span> <span data-ttu-id="097a4-297">此方法检索指定路径处的项的参数，并返回一个对象，该对象具有与 cmdlet 类或[Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)对象类似的分析特性的属性和字段。</span><span class="sxs-lookup"><span data-stu-id="097a4-297">This method retrieves the parameters for the item at the indicated path and returns an object that has properties and fields with parsing attributes similar to a cmdlet class or a [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) object.</span></span> <span data-ttu-id="097a4-298">Windows PowerShell 运行时使用返回的对象将参数添加到 `Copy-Item` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="097a4-298">The Windows PowerShell runtime uses the returned object to add the parameters to the `Copy-Item` cmdlet.</span></span>

<span data-ttu-id="097a4-299">此提供程序未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="097a4-299">This provider does not implement this method.</span></span> <span data-ttu-id="097a4-300">但是，下面的代码是[Containercmdletprovider. Copyitemdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters)的默认实现。</span><span class="sxs-lookup"><span data-stu-id="097a4-300">However, the following code is the default implementation of [System.Management.Automation.Provider.Containercmdletprovider.Copyitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters).</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidercopyitemdynamicparameters](Msh_samplestestcmdlets#testprovidercopyitemdynamicparameters)]  -->

## <a name="code-sample"></a><span data-ttu-id="097a4-301">代码示例</span><span class="sxs-lookup"><span data-stu-id="097a4-301">Code Sample</span></span>

<span data-ttu-id="097a4-302">有关完整的示例代码，请参阅[AccessDbProviderSample04 代码示例](./accessdbprovidersample04-code-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="097a4-302">For complete sample code, see [AccessDbProviderSample04 Code Sample](./accessdbprovidersample04-code-sample.md).</span></span>

## <a name="building-the-windows-powershell-provider"></a><span data-ttu-id="097a4-303">生成 Windows PowerShell 提供程序</span><span class="sxs-lookup"><span data-stu-id="097a4-303">Building the Windows PowerShell Provider</span></span>

<span data-ttu-id="097a4-304">请参阅[如何注册 cmdlet、提供程序和主机应用程序](/previous-versions/ms714644(v=vs.85))。</span><span class="sxs-lookup"><span data-stu-id="097a4-304">See [How to Register Cmdlets, Providers, and Host Applications](/previous-versions/ms714644(v=vs.85)).</span></span>

## <a name="testing-the-windows-powershell-provider"></a><span data-ttu-id="097a4-305">测试 Windows PowerShell 提供程序</span><span class="sxs-lookup"><span data-stu-id="097a4-305">Testing the Windows PowerShell Provider</span></span>

<span data-ttu-id="097a4-306">向 Windows powershell 注册 Windows PowerShell 提供程序后，可以通过在命令行上运行支持的 cmdlet 来对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="097a4-306">When your Windows PowerShell provider has been registered with Windows PowerShell, you can test it by running the supported cmdlets on the command line.</span></span> <span data-ttu-id="097a4-307">请注意，以下示例输出使用虚构的 Access 数据库。</span><span class="sxs-lookup"><span data-stu-id="097a4-307">Be aware that the following example output uses a fictitious Access database.</span></span>

1. <span data-ttu-id="097a4-308">运行此 `Get-ChildItem` cmdlet 可在 Access 数据库中检索 Customers 表中的子项列表。</span><span class="sxs-lookup"><span data-stu-id="097a4-308">Run the `Get-ChildItem` cmdlet to retrieve the list of child items from a Customers table in the Access database.</span></span>

   ```powershell
   Get-ChildItem mydb:customers
   ```

   <span data-ttu-id="097a4-309">将显示以下输出。</span><span class="sxs-lookup"><span data-stu-id="097a4-309">The following output appears.</span></span>

   ```output
   PSPath        : AccessDB::customers
   PSDrive       : mydb
   PSProvider    : System.Management.Automation.ProviderInfo
   PSIsContainer : True
   Data          : System.Data.DataRow
   Name          : Customers
   RowCount      : 91
   Columns       :
   ```

2. <span data-ttu-id="097a4-310">再次运行该 `Get-ChildItem` cmdlet 以检索表的数据。</span><span class="sxs-lookup"><span data-stu-id="097a4-310">Run the `Get-ChildItem` cmdlet again to retrieve the data of a table.</span></span>

   ```powershell
   (Get-ChildItem mydb:customers).data
   ```

   <span data-ttu-id="097a4-311">将显示以下输出。</span><span class="sxs-lookup"><span data-stu-id="097a4-311">The following output appears.</span></span>

   ```output
   TABLE_CAT   : c:\PS\northwind
   TABLE_SCHEM :
   TABLE_NAME  : Customers
   TABLE_TYPE  : TABLE
   REMARKS     :
   ```

3. <span data-ttu-id="097a4-312">现在，使用 `Get-Item` cmdlet 检索数据表中第0行处的项。</span><span class="sxs-lookup"><span data-stu-id="097a4-312">Now use the `Get-Item` cmdlet to retrieve the items at row 0 in the data table.</span></span>

   ```powershell
   Get-Item mydb:\customers\0
   ```

   <span data-ttu-id="097a4-313">将显示以下输出。</span><span class="sxs-lookup"><span data-stu-id="097a4-313">The following output appears.</span></span>

   ```output
   PSPath        : AccessDB::customers\0
   PSDrive       : mydb
   PSProvider    : System.Management.Automation.ProviderInfo
   PSIsContainer : False
   Data          : System.Data.DataRow
   RowNumber     : 0
   ```

4. <span data-ttu-id="097a4-314">重复使用 `Get-Item` 检索第0行中的项的数据。</span><span class="sxs-lookup"><span data-stu-id="097a4-314">Reuse `Get-Item` to retrieve the data for the items in row 0.</span></span>

   ```powershell
   (Get-Item mydb:\customers\0).data
   ```

   <span data-ttu-id="097a4-315">将显示以下输出。</span><span class="sxs-lookup"><span data-stu-id="097a4-315">The following output appears.</span></span>

   ```output
   CustomerID   : 1234
   CompanyName  : Fabrikam
   ContactName  : Eric Gruber
   ContactTitle : President
   Address      : 4567 Main Street
   City         : Buffalo
   Region       : NY
   PostalCode   : 98052
   Country      : USA
   Phone        : (425) 555-0100
   Fax          : (425) 555-0101
   ```

5. <span data-ttu-id="097a4-316">现在，使用 `New-Item` cmdlet 向现有表中添加行。</span><span class="sxs-lookup"><span data-stu-id="097a4-316">Now use the `New-Item` cmdlet to add a row to an existing table.</span></span> <span data-ttu-id="097a4-317">`Path`参数指定行的完整路径，并且必须指示大于表中现有行数的行号。</span><span class="sxs-lookup"><span data-stu-id="097a4-317">The `Path` parameter specifies the full path to the row, and must indicate a row number that is greater than the existing number of rows in the table.</span></span> <span data-ttu-id="097a4-318">`Type`参数指示 "行" 以指定要添加的项的类型。</span><span class="sxs-lookup"><span data-stu-id="097a4-318">The `Type` parameter indicates "row" to specify that type of item to add.</span></span>
   <span data-ttu-id="097a4-319">最后， `Value` 参数为行指定以逗号分隔的列值列表。</span><span class="sxs-lookup"><span data-stu-id="097a4-319">Finally, the `Value` parameter specifies a comma-delimited list of column values for the row.</span></span>

   ```powershell
   New-Item -Path mydb:\Customers\3 -ItemType "row" -Value "3,CustomerFirstName,CustomerLastName,CustomerEmailAddress,CustomerTitle,CustomerCompany,CustomerPhone, CustomerAddress,CustomerCity,CustomerState,CustomerZip,CustomerCountry"
   ```

6. <span data-ttu-id="097a4-320">验证新项操作的正确性，如下所示。</span><span class="sxs-lookup"><span data-stu-id="097a4-320">Verify the correctness of the new item operation as follows.</span></span>

   ```none
   PS mydb:\> cd Customers
   PS mydb:\Customers> (Get-Item 3).data
   ```

   <span data-ttu-id="097a4-321">将显示以下输出。</span><span class="sxs-lookup"><span data-stu-id="097a4-321">The following output appears.</span></span>

   ```output
   ID        : 3
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
   ```

## <a name="see-also"></a><span data-ttu-id="097a4-322">另请参阅</span><span class="sxs-lookup"><span data-stu-id="097a4-322">See Also</span></span>

[<span data-ttu-id="097a4-323">创建 Windows PowerShell 提供程序</span><span class="sxs-lookup"><span data-stu-id="097a4-323">Creating Windows PowerShell Providers</span></span>](./how-to-create-a-windows-powershell-provider.md)

[<span data-ttu-id="097a4-324">设计 Windows PowerShell 提供程序</span><span class="sxs-lookup"><span data-stu-id="097a4-324">Designing Your Windows PowerShell Provider</span></span>](./designing-your-windows-powershell-provider.md)

[<span data-ttu-id="097a4-325">实现 Windows PowerShell 提供程序项</span><span class="sxs-lookup"><span data-stu-id="097a4-325">Implementing an Item Windows PowerShell Provider</span></span>](./creating-a-windows-powershell-item-provider.md)

[<span data-ttu-id="097a4-326">实现导航 Windows PowerShell 提供程序</span><span class="sxs-lookup"><span data-stu-id="097a4-326">Implementing a Navigation Windows PowerShell Provider</span></span>](./creating-a-windows-powershell-navigation-provider.md)

<span data-ttu-id="097a4-327">[如何注册 Cmdlet、提供程序和主机应用程序](/previous-versions/ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="097a4-327">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions/ms714644(v=vs.85))</span></span>

[<span data-ttu-id="097a4-328">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="097a4-328">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="097a4-329">Windows PowerShell 程序员指南</span><span class="sxs-lookup"><span data-stu-id="097a4-329">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)
