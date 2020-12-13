---
ms.date: 09/13/2016
ms.topic: reference
title: 创建 Windows PowerShell 导航提供程序
description: 创建 Windows PowerShell 导航提供程序
ms.openlocfilehash: 73d4971fb91acaef9e1f20226e7b9b883730e394
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658671"
---
# <a name="creating-a-windows-powershell-navigation-provider"></a>创建 Windows PowerShell 导航提供程序

本主题介绍如何创建可在数据存储中导航的 Windows PowerShell 导航提供程序。 这种类型的提供程序支持递归命令、嵌套容器和相对路径。

> [!NOTE]
> 你可以使用适用于 Windows Vista 的 Microsoft Windows 软件开发工具包和 .NET Framework 3.0 运行时组件) 为此提供程序下载 c # 源文件 (。 有关下载说明，请参阅 [如何安装 Windows powershell 和下载 Windows POWERSHELL SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk)。
> 下载的源文件在目录中提供 **\<PowerShell Samples>** 。 有关其他 Windows PowerShell 提供程序实现的详细信息，请参阅 [设计 Windows Powershell 提供程序](./designing-your-windows-powershell-provider.md)。

此处所述的提供程序使用户能够将 Access 数据库作为驱动器处理，使用户可以导航到数据库中的数据表。 创建自己的导航提供程序时，您可以实现一些方法，这些方法可以使导航需要驱动器限定路径、规范化相对路径、移动数据存储区的项，以及获取子名称的方法、获取项的父路径，以及用于确定项是否为容器的测试。

> [!CAUTION]
> 请注意，此设计假设有一个数据库，该数据库具有名称为 ID 的字段，并且该字段的类型为 LongInteger。

## <a name="define-the-windows-powershell-provider"></a>定义 Windows PowerShell 提供程序

Windows PowerShell 导航提供程序必须创建一个从 [Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) 基类派生的 .net 类的 .net 类。 下面是本部分中所述的导航提供程序的类定义。

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample05/AccessDBProviderSample05.cs" range="31-32":::

请注意，在此提供程序中， [Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) 属性包括两个参数。 第一个参数指定 Windows PowerShell 使用的提供程序的用户友好名称。 第二个参数指定 Windows PowerShell 特定功能，该功能是在命令处理过程中提供给 Windows PowerShell 运行时的。 对于此提供程序，没有添加的 Windows PowerShell 特定功能。

## <a name="defining-base-functionality"></a>定义基本功能

如 [设计 PS 提供程序](./designing-your-windows-powershell-provider.md)中所述， [Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) 基类派生自多个提供不同提供程序功能的其他类。 因此，Windows PowerShell 导航提供程序必须定义这些类提供的所有功能。

若要实现添加特定于会话的初始化信息以及释放提供程序使用的资源的功能，请参阅 [创建基本 PS 提供程序](./creating-a-basic-windows-powershell-provider.md)。 但是，大多数提供程序 (包括此处所述的提供程序) 可以使用 Windows PowerShell 提供的此功能的默认实现。

若要通过 Windows PowerShell 驱动器访问数据存储区，必须实现 [Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) 基类的这些方法的实现方法。 有关实现这些方法的详细信息，请参阅 [创建 Windows PowerShell 驱动器提供程序](./creating-a-windows-powershell-drive-provider.md)。

若要操作数据存储区的项（如获取、设置和清除项），提供程序必须实现 [Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) 基类提供的方法。 有关实现这些方法的详细信息，请参阅 [创建 Windows PowerShell 项提供程序](./creating-a-windows-powershell-item-provider.md)。

若要访问数据存储区的子项目或其名称，以及创建、复制、重命名和删除项的方法，必须实现 [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) 基类提供的方法，然后再执行。 有关实现这些方法的详细信息，请参阅 [创建 Windows PowerShell 容器提供程序](./creating-a-windows-powershell-container-provider.md)。

## <a name="creating-a-windows-powershell-path"></a>创建 Windows PowerShell 路径

Windows PowerShell 导航提供程序使用提供程序内部的 Windows PowerShell 路径导航数据存储区中的项。 若要创建提供程序内部路径，提供程序必须实现 [Navigationcmdletprovider. Makepath *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) 方法，以支持来自 Combine-Path cmdlet 的调用。 此方法使用父路径和子路径之间的特定于提供程序的路径分隔符将父路径和子路径合并到提供程序内部路径中。

默认实现使用路径 "/" 或 " \\ " 作为路径分隔符，将路径分隔符规范化为 " \\ "，将父路径部分与子路径部分组合在一起，然后返回包含组合路径的字符串。

此导航提供程序不实现此方法。 但是，下面的代码是 [Navigationcmdletprovider. Makepath *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) 方法的默认实现方式。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidermakepath](Msh_samplestestcmdlets#testprovidermakepath)]  -->

#### <a name="things-to-remember-about-implementing-makepath"></a>有关实现 MakePath 的注意事项

以下情况可能适用于你的 [Navigationcmdletprovider. Makepath *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath)实现：

- [Navigationcmdletprovider. Makepath *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath)方法的实现不应将该路径作为提供程序命名空间中的合法完全限定路径进行验证。 请注意，每个参数只能表示部分路径，并且组合部件可能不会生成完全限定的路径。 例如，filesystem 提供程序的 [Navigationcmdletprovider. Makepath *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) 方法可能会在参数中收到 "windows\system32" `parent` ，并在参数中接收 "abc.dll" `child` 。 方法使用 "" 分隔符来联接这些值， \\ 并返回 "windows\system32\abc.dll"，这不是一个完全限定的文件系统路径。

  > [!IMPORTANT]
  > 在对 [Navigationcmdletprovider. Makepath *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) 的调用中提供的路径部分可能包含提供程序命名空间中不允许使用的字符。 这些字符最有可能用于通配符扩展，而此方法的实现不应将其删除。

## <a name="retrieving-the-parent-path"></a>检索父路径

Windows PowerShell 导航提供程序可实现 [Navigationcmdletprovider. Getparentpath *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) 方法，以检索指定完整或部分提供程序特定路径的父部分。 方法移除路径的子部分，并返回父路径部分。 `root`参数指定驱动器根目录的完全限定路径。 如果已装载的驱动器未用于检索操作，则此参数可以为 null 或空。 如果指定了根，则该方法必须返回与根位于同一树中的容器的路径。

示例导航提供程序不会重写此方法，但会使用默认实现。
它接受使用 "/" 和 " \\ " 作为路径分隔符的路径。 它首先将路径规范化为仅具有 " \\ " 分隔符，然后在最后一个 "" 处拆分父路径， \\ 并返回父路径。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidergetparentpath](Msh_samplestestcmdlets#testprovidergetparentpath)]  -->

#### <a name="to-remember-about-implementing-getparentpath"></a>要记住如何实现 GetParentPath

[Navigationcmdletprovider. Getparentpath *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath)方法的实现应将词法上的路径拆分为提供程序命名空间的路径分隔符。 例如，filesystem 提供程序使用此方法查找最后一个 " \\ "，并将所有内容返回到分隔符的左侧。

## <a name="retrieve-the-child-path-name"></a>检索子路径名称

你的导航提供程序将实现 [Navigationcmdletprovider. Getchildname *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) 方法，以检索位于指定完整或部分提供程序特定路径的项的子元素)  (叶元素的名称。

示例导航提供程序不重写此方法。 默认实现如下所示。 它接受使用 "/" 和 " \\ " 作为路径分隔符的路径。 它首先将路径规范化为仅具有 " \\ " 分隔符，然后在最后一个 "" 处拆分父路径， \\ 并返回子路径部分的名称。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidergetchildname](Msh_samplestestcmdlets#testprovidergetchildname)]  -->

#### <a name="things-to-remember-about-implementing-getchildname"></a>有关实现 GetChildName 的注意事项

你的 [Navigationcmdletprovider Getchildname](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) 方法的实现应在路径分隔符上拆分词法上的路径。 如果提供的路径不包含任何路径分隔符，方法应返回未修改的路径。

> [!IMPORTANT]
> 对此方法的调用中提供的路径可能包含提供程序命名空间中的非法字符。 这些字符最有可能用于通配符扩展或正则表达式匹配，而此方法的实现不应将其删除。

## <a name="determining-if-an-item-is-a-container"></a>确定项是否为容器

导航提供程序可以实现 [Navigationcmdletprovider. Isitemcontainer *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) 方法，以确定指定的路径是否指示一个容器。 如果路径表示容器，则返回 true; 否则返回 false。 用户需要此方法才能将 `Test-Path` cmdlet 用于提供的路径。

下面的代码演示了示例导航提供程序中的 [Navigationcmdletprovider. Isitemcontainer *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) 实现。 方法验证指定的路径是否正确，并且如果表存在，则返回 true; 如果路径指示容器，则返回 true。

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample05/AccessDBProviderSample05.cs" range="847-872":::

#### <a name="things-to-remember-about-implementing-isitemcontainer"></a>有关实现 IsItemContainer 的注意事项

你的导航提供程序 .NET 类可以声明 ExpandWildcards、Filter、Include 或 Exclude 的提供程序功能， [Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) 枚举。 在这种情况下， [Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) 的实现会要求确保传递的路径满足要求的要求。 为此，此方法应访问相应的属性，例如， [Cmdletprovider *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) 属性的属性为。

## <a name="moving-an-item"></a>移动项

为了支持 `Move-Item` cmdlet，你的导航提供程序将实现 [Navigationcmdletprovider. Moveitem *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) 方法。 此方法将由参数指定的项移动 `path` 到在参数中提供的路径上的容器中 `destination` 。

示例导航提供程序不重写 [Navigationcmdletprovider. Moveitem *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) 方法。 下面是默认实现。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidermoveitem](Msh_samplestestcmdlets#testprovidermoveitem)]  -->

#### <a name="things-to-remember-about-implementing-moveitem"></a>有关实现 MoveItem 的注意事项

你的导航提供程序 .NET 类可以声明 ExpandWildcards、Filter、Include 或 Exclude 的提供程序功能， [Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) 枚举。 在这种情况下， [Navigationcmdletprovider. Moveitem *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) 的实现必须确保传递的路径符合要求。 为此，方法应访问相应的属性，例如 **CmdletProvider** 属性。

默认情况下，此方法的重写不应将对象移到现有对象上，除非 [Cmdletprovider *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) 属性设置为 `true` 。 例如，filesystem 提供程序将不会通过现有 c:\bar.txt 文件复制 c:\temp\abc.txt，除非 [Cmdletprovider *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) 属性被设置为 `true` 。 如果在参数中指定的路径 `destination` 存在并且是一个容器，则不需要 [Cmdletprovider *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) 属性（& e）。 在这种情况下， [Navigationcmdletprovider. Moveitem *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) 应将参数指示的项移动 `path` 到参数所指示的 `destination` 子容器。

在对数据存储进行任何更改之前，你的 [Navigationcmdletprovider 和 Moveitem *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) 方法的实现应调用 [Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) ，并检查其返回值，然后再进行更改。 此方法用于在对系统状态进行更改时（例如，删除文件时）确认操作的执行。
[Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) 发送要更改为用户的资源的名称，Windows PowerShell 运行时在确定应该向用户显示的内容时，会考虑到任何命令行设置或首选项变量。

在对 Cmdletprovider 的调用返回后， [ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) 方法 `true` 应调用 [Navigationcmdletprovider。 Moveitem *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) 方法应调用. Cmdletprovider 方法的 [调用方的](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) 调用程序的调用程序的。 此方法将向用户发送一条消息，以允许反馈以指示是否应继续进行操作。 提供程序应调用 [Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) 作为额外检查来检查是否存在潜在的危险系统修改。

## <a name="attaching-dynamic-parameters-to-the-move-item-cmdlet"></a>将动态参数附加到 Move-Item Cmdlet

有时，该 `Move-Item` cmdlet 需要在运行时动态提供的其他参数。 若要提供这些动态参数，导航提供程序必须实现 [Navigationcmdletprovider. Moveitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters) 方法，以便从所指示的路径处的项获取所需的参数值，并返回一个对象，该对象具有与 cmdlet 类或 [Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) 对象类似的分析特性的属性和字段。

此导航提供程序不实现此方法。 但是，下面的代码是 [Navigationcmdletprovider. Moveitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters)的默认实现。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidermoveitemdynamicparameters](Msh_samplestestcmdlets#testprovidermoveitemdynamicparameters)]  -->

## <a name="normalizing-a-relative-path"></a>规范化相对路径

导航提供程序可实现 [Navigationcmdletprovider. Normalizerelativepath *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) 方法，以将参数中指定的完全限定路径规范化为 `path` 相对于参数指定的路径 `basePath` 。 方法返回规范化路径的字符串表示形式。 如果 `path` 参数指定了不存在的路径，则它会写入错误。

示例导航提供程序不重写此方法。 下面是默认实现。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidernormalizepath](Msh_samplestestcmdlets#testprovidernormalizepath)]  -->

#### <a name="things-to-remember-about-implementing-normalizerelativepath"></a>有关实现 NormalizeRelativePath 的注意事项

[Navigationcmdletprovider. Normalizerelativepath *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath)的实现应分析 `path` 参数，但它不必使用纯粹的语法分析来进行分析。 建议设计此方法，以便使用路径在数据存储中查找路径信息，并创建与大小写和标准化路径语法匹配的路径。

## <a name="code-sample"></a>代码示例

有关完整的示例代码，请参阅 [AccessDbProviderSample05 代码示例](./accessdbprovidersample05-code-sample.md)。

## <a name="defining-object-types-and-formatting"></a>定义对象类型和格式设置

提供程序可以将成员添加到现有对象或定义新的对象。 有关详细信息，请参阅[扩展对象类型和格式](/previous-versions/ms714665(v=vs.85))。

## <a name="building-the-windows-powershell-provider"></a>生成 Windows PowerShell 提供程序

有关详细信息，请参阅 [如何注册 cmdlet、提供程序和主机应用程序](/previous-versions/ms714644(v=vs.85))。

## <a name="testing-the-windows-powershell-provider"></a>测试 Windows PowerShell 提供程序

向 windows powershell 注册 Windows PowerShell 提供程序后，可以通过在命令行上运行支持的 cmdlet （包括派生提供的 cmdlet）来测试 Windows PowerShell 提供程序。 此示例将测试示例导航提供程序。

1. 运行新的 shell，并使用 `Set-Location` cmdlet 来设置用于指示 Access 数据库的路径。

   ```powershell
   Set-Location mydb:
   ```

2. 现在，运行 `Get-Childitem` cmdlet 以检索数据库项的列表，这些项是可用的数据库表。 对于每个表，此 cmdlet 还将检索表行的数目。

   ```powershell
   Get-ChildItem | Format-Table rowcount,name -AutoSize
   ```

   ```Output
   RowCount   Name
   --------   ----
        180   MSysAccessObjects
          0   MSysACEs
          1   MSysCmdbars
          0   MSysIMEXColumns
          0   MSysIMEXSpecs
          0   MSysObjects
          0   MSysQueries
          7   MSysRelationships
          8   Categories
         91   Customers
          9   Employees
       2155   Order Details
        830   Orders
         77   Products
          3   Shippers
         29   Suppliers
   ```

3. 再次使用 `Set-Location` cmdlet 设置 Employees 数据表的位置。

   ```powershell
   Set-Location Employees
   ```

4. 现在，让我们使用 `Get-Location` cmdlet 检索 Employees 表的路径。

   ```powershell
   Get-Location
   ```

   ```Output
   Path
   ----
   mydb:\Employees
   ```

5. 现在使用通过 `Get-Childitem` 管道传递给 cmdlet 的 cmdlet `Format-Table` 。 这组 cmdlet 可检索 Employees 数据表（表行）的项。 它们按 cmdlet 指定的格式进行格式化 `Format-Table` 。

   ```powershell
   Get-ChildItem | Format-Table rownumber,psiscontainer,data -AutoSize
   ```

   ```Output
   RowNumber   PSIsContainer   Data
   ---------   --------------   ----
   0           False            System.Data.DataRow
   1           False            System.Data.DataRow
   2           False            System.Data.DataRow
   3           False            System.Data.DataRow
   4           False            System.Data.DataRow
   5           False            System.Data.DataRow
   6           False            System.Data.DataRow
   7           False            System.Data.DataRow
   8           False            System.Data.DataRow
   ```

6. 你现在可以运行 `Get-Item` cmdlet 来检索 Employees 数据表的第0行的项。

   ```powershell
   Get-Item 0
   ```

   ```Output
   PSPath        : AccessDB::C:\PS\Northwind.mdb\Employees\0
   PSParentPath  : AccessDB::C:\PS\Northwind.mdb\Employees
   PSChildName   : 0
   PSDrive       : mydb
   PSProvider    : System.Management.Automation.ProviderInfo
   PSIsContainer : False
   Data           : System.Data.DataRow
   RowNumber      : 0
   ```

7. 再次使用 `Get-Item` cmdlet 检索第0行中的项的雇员数据。

   ```powershell
   (Get-Item 0).data
   ```

   ```Output
   EmployeeID      : 1
   LastName        : Davis
   FirstName       : Sara
   Title           : Sales Representative
   TitleOfCourtesy : Ms.
   BirthDate       : 12/8/1968 12:00:00 AM
   HireDate        : 5/1/1992 12:00:00 AM
   Address         : 4567 Main Street
                     Apt. 2A
   City            : Buffalo
   Region          : NY
   PostalCode      : 98052
   Country         : USA
   HomePhone       : (206) 555-9857
   Extension       : 5467
   Photo           : EmpID1.bmp
   Notes           : Education includes a BA in psychology from
                     Colorado State University. She also completed "The
                     Art of the Cold Call."  Nancy is a member of
                     Toastmasters International.
   ReportsTo       : 2
   ```

## <a name="see-also"></a>另请参阅

[创建 Windows PowerShell 提供程序](./how-to-create-a-windows-powershell-provider.md)

[设计你的 Windows PowerShell 提供程序](./designing-your-windows-powershell-provider.md)

[扩展对象类型和格式](/previous-versions/ms714665(v=vs.85))

[实现容器 Windows PowerShell 提供程序](./creating-a-windows-powershell-container-provider.md)

[如何注册 Cmdlet、提供程序和主机应用程序](/previous-versions/ms714644(v=vs.85))

[Windows PowerShell 程序员指南](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
