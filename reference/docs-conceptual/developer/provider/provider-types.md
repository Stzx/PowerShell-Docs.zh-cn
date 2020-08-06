---
title: 提供程序类型 |Microsoft Docs
ms.date: 08/21/2019
ms.openlocfilehash: 03b6b2d02d603632399ea455c2832742e0964d62
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87778251"
---
# <a name="provider-types"></a>提供程序类型

提供程序通过更改 PowerShell 提供的提供程序 cmdlet 的执行操作来定义其基本功能。 例如，提供程序可以使用 cmdlet 的默认功能 `Get-Item` ，也可以在从数据存储区中检索项时更改该 cmdlet 的操作方式。 本文档中所述的提供程序功能包括通过覆盖特定提供程序基类和接口中的方法定义的功能。

> [!NOTE]
> 有关 PowerShell 预定义的提供程序功能，请参阅[提供程序功能](/previous-versions//ee126189(v=vs.85))。

## <a name="drive-enabled-providers"></a>支持驱动器的提供程序

启用驱动器的提供程序指定用户可用的默认驱动器，并允许用户添加或删除驱动器。 在大多数情况下，提供程序是支持驱动器的提供程序，因为它们需要某些默认驱动器来访问数据存储。 但是，在编写您自己的提供程序时，您可能会或可能不希望允许用户创建和删除驱动器。

若要创建启用驱动器的提供程序，提供程序类必须派生自[DriveCmdletProvider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)类或派生自该类的另一个类。 **DriveCmdletProvider**类定义以下用于实现提供程序的默认驱动器并支持和 cmdlet 的方法： `New-PSDrive` `Remove-PSDrive` 。 在大多数情况下，若要支持提供程序 cmdlet，必须覆盖 PowerShell 引擎调用的方法来调用 cmdlet，例如 `NewDrive` cmdlet 的方法， `New-PSDrive` 还可以覆盖第二种方法（如 `NewDriveDynamicParameters` ），以便将动态参数添加到 cmdlet。

- 当使用提供程序时， [System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives)方法将定义可供用户使用的默认驱动器。

- [DriveCmdletProvider 和 NewDrive](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)方法定义了提供程序如何支持提供程序 cmdlet 的方式，即为和[DriveCmdletProvider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters)方法。 `New-PSDrive` 此 cmdlet 允许用户创建驱动器以访问数据存储。

- [DriveCmdletProvider. RemoveDrive](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)方法定义提供程序如何支持 `Remove-PSDrive` 提供程序 cmdlet。 此 cmdlet 允许用户从数据存储中删除驱动器。

## <a name="item-enabled-providers"></a>启用了项目的提供程序

启用项的提供程序允许用户获取、设置或清除数据存储区中的项。 "项" 是用户可以单独访问或管理的数据存储的元素。 若要创建支持项的提供程序，提供程序类必须派生自[ItemCmdletProvider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)类或派生自该类的另一个类。

**ItemCmdletProvider**类定义以下用于实现特定提供程序 cmdlet 的方法。 在大多数情况下，若要支持提供程序 cmdlet，必须覆盖 PowerShell 引擎调用的方法来调用 cmdlet，例如 `ClearItem` cmdlet 的方法， `Clear-Item` 还可以覆盖第二种方法（如 `ClearItemDynamicParameters` ），以便将动态参数添加到 cmdlet。

- [ItemCmdletProvider 和 ClearItem](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem)方法定义了提供程序如何支持提供程序 cmdlet 的方式和[功能](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters)的方法的定义方法。 `Clear-Item` 此 cmdlet 允许用户删除数据存储中某个项的值。

- [ItemCmdletProvider 和 GetItem](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem)方法定义了提供程序如何支持提供程序 cmdlet 的方式和[功能](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters)的方法的定义方法。 `Get-Item` 此 cmdlet 允许用户从数据存储中检索数据。

- [ItemCmdletProvider 和 SetItem](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)方法定义了提供程序如何支持提供程序 cmdlet 的方式和[功能](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters)的方法的定义方法。 `Set-Item` 此 cmdlet 允许用户更新数据存储区中的项的值。

- [Itemcmdletprovider 和 InvokeDefaultAction](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction)方法定义了提供程序如何支持提供程序 cmdlet 的方式和[功能](/dotnet/api/system.management.automation.provider.itemcmdletprovider.invokedefaultactiondynamicparameters)的方法的定义方法。 `Invoke-Item` 此 cmdlet 允许用户执行项指定的默认操作。

- [ItemCmdletProvider 和 ItemExists](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists)方法定义了提供程序如何支持提供程序 cmdlet 的方式和[功能](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExistsDynamicParameters)的方法的定义方法。 `Test-Path` 此 cmdlet 允许用户确定路径的所有元素是否存在。

除了用于实现提供程序 cmdlet 的方法以外， **ItemCmdletProvider**类还定义了以下方法：

- [ItemCmdletProvider. ExpandPath](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ExpandPath)方法允许用户在指定提供程序路径时使用通配符（）。

- [ItemCmdletProvider. IsValidPath](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath)用于确定路径对于提供程序是否在语法和语义上是有效的。

## <a name="container-enabled-providers"></a>启用容器的提供程序

启用容器的提供程序允许用户管理容器中的项。 容器是包含公用父项下的子项的组。 若要创建启用容器的提供程序，提供程序类必须派生自[ContainerCmdletProvider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)类或派生自该类的另一个类。

> [!IMPORTANT]
> 启用容器的访问接口无法访问包含嵌套容器的数据存储区。 如果容器的子项是另一个容器，则必须实现启用导航的提供程序。

**ContainerCmdletProvider**类定义以下用于实现特定提供程序 cmdlet 的方法。 在大多数情况下，若要支持提供程序 cmdlet，必须覆盖 PowerShell 引擎调用的方法来调用 cmdlet，例如 `CopyItem` cmdlet 的方法， `Copy-Item` 还可以覆盖第二种方法（如 `CopyItemDynamicParameters` ），以便将动态参数添加到 cmdlet。

- [ContainerCmdletProvider 和 CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)方法定义了提供程序如何支持提供程序 cmdlet 的方式和[功能](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters)的方法的定义方法。 `Copy-Item` 此 cmdlet 允许用户将项从一个位置复制到另一个位置。

- [ContainerCmdletProvider 和 GetChildItems](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)方法定义了提供程序如何支持提供程序 cmdlet 的方式和[功能](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters)的方法的定义方法。 `Get-ChildItem` 此 cmdlet 允许用户检索父项的子项。

- 如果指定了 ContainerCmdletProvider 方法的参数，则[GetChildNames](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames)和[ContainerCmdletProvider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters)方法定义提供程序如何支持该提供程序 `Get-ChildItem` cmdlet 的操作方式的方法。 `Name`

- [ContainerCmdletProvider 和 NewItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)方法定义了提供程序如何支持提供程序 cmdlet 的方式和[功能](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItemDynamicParameters)的方法的定义方法。 `New-Item` 此 cmdlet 允许用户在数据存储中创建新项。

- [ContainerCmdletProvider 和 RemoveItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem)方法定义了提供程序如何支持提供程序 cmdlet 的方式和[功能](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters)的方法的定义方法。 `Remove-Item` 此 cmdlet 允许用户从数据存储中删除项。

- [ContainerCmdletProvider 和 RenameItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem)方法定义了提供程序如何支持提供程序 cmdlet 的方式和[功能](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters)的方法的定义方法。 `Rename-Item` 此 cmdlet 允许用户重命名数据存储区中的项。

除了用于实现提供程序 cmdlet 的方法以外， **ContainerCmdletProvider**类还定义了以下方法：

- 提供程序类可以使用[ContainerCmdletProvider. HasChildItems](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems)方法来确定某一项是否具有子项。

- 提供程序类可以使用[ContainerCmdletProvider. ConvertPath](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.ConvertPath)方法从指定的路径创建新的特定于提供程序的路径。

## <a name="navigation-enabled-providers"></a>启用导航的提供程序

启用导航的提供程序允许用户在数据存储中移动项。 若要创建启用导航的提供程序，提供程序类必须派生自[NavigationCmdletProvider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)类。

**NavigationCmdletProvider**类定义以下用于实现特定提供程序 cmdlet 的方法。 在大多数情况下，若要支持提供程序 cmdlet，必须覆盖 PowerShell 引擎调用的方法来调用 cmdlet，例如 `MoveItem` cmdlet 的方法， `Move-Item` 还可以覆盖第二种方法（如 `MoveItemDynamicParameters` ），以便将动态参数添加到 cmdlet。

- [NavigationCmdletProvider 和 MoveItem](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem)方法定义了提供程序如何支持提供程序 cmdlet 的方式和[功能](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters)的方法的定义方法。 `Move-Item` 此 cmdlet 允许用户将项从存储区中的一个位置移到另一个位置。

- [NavigationCmdletProvider. MakePath](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath)方法定义提供程序如何支持 `Join-Path` 提供程序 cmdlet。 此 cmdlet 允许用户合并父路径段和子路径段以创建提供程序内部路径。

除了用于实现提供程序 cmdlet 的方法以外， **NavigationCmdletProvider**类还定义了以下方法：

- [NavigationCmdletProvider. GetChildName](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName)方法提取路径的子节点的名称（& e）。

- [NavigationCmdletProvider. GetParentPath](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath)方法会提取路径的父部分，而不是。

- [NavigationCmdletProvider. IsItemContainer](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer)方法决定项是否为容器项。）。 在此上下文中，容器是公共父项下的一组子项。

- [NavigationCmdletProvider. NormalizeRelativePath](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath)方法将返回相对于指定基路径的项的路径，该路径为。

## <a name="content-enabled-providers"></a>启用内容的提供程序

启用内容的提供程序允许用户在数据存储中清除、获取或设置项的内容。
例如，FileSystem 提供程序允许清除、获取和设置文件系统中的文件的内容。 若要创建启用内容的提供程序，提供程序类必须实现[IContentCmdletProvider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider)接口的方法。

**IContentCmdletProvider**接口定义以下用于实现特定提供程序 cmdlet 的方法。 在大多数情况下，若要支持提供程序 cmdlet，必须覆盖 PowerShell 引擎调用的方法来调用 cmdlet，例如 `ClearContent` cmdlet 的方法， `Clear-Content` 还可以覆盖第二种方法（如 `ClearContentDynamicParameters` ），以便将动态参数添加到 cmdlet。

- [IContentCmdletProvider 和 ClearContent](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent)方法定义了提供程序如何支持提供程序 cmdlet 的方式和[功能](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters)的方法的定义方法。 `Clear-Content` 此 cmdlet 允许用户删除项的内容，而不会删除该项。

- [IContentCmdletProvider 和 GetContentReader](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader)方法定义了提供程序如何支持提供程序 cmdlet 的方式和[功能](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters)的方法的定义方法。 `Get-Content` 此 cmdlet 允许用户检索项的内容。 `System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader`方法返回一个[IContentReader](/dotnet/api/System.Management.Automation.Provider.IContentReader)接口，该接口定义用于读取内容的方法。

- [IContentCmdletProvider 和 GetContentWriter](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter)方法定义了提供程序如何支持提供程序 cmdlet 的方式和[功能](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters)的方法的定义方法。 `Set-Content` 此 cmdlet 允许用户更新项的内容。 `System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter`方法返回一个[IContentWriter](/dotnet/api/System.Management.Automation.Provider.IContentWriter)接口，该接口定义用于写入内容的方法。

## <a name="property-enabled-providers"></a>启用了属性的提供程序

启用了属性的提供程序允许用户管理数据存储中项的属性。
若要创建一个启用了属性的提供程序，提供程序类必须实现[IPropertyCmdletProvider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider)和[IDynamicPropertyCmdletProvider](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider)接口的方法的实现方法。 在大多数情况下，若要支持提供程序 cmdlet，必须覆盖 PowerShell 引擎调用的方法来调用 cmdlet，如 `ClearProperty` Clear 属性 cmdlet 的方法，还可以覆盖第二种方法（如 `ClearPropertyDynamicParameters` ），以便将动态参数添加到 cmdlet。

**IPropertyCmdletProvider**接口定义以下用于实现特定提供程序 cmdlet 的方法：

- [IPropertyCmdletProvider 和 ClearProperty](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty)方法定义了提供程序如何支持提供程序 cmdlet 的方式和[功能](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters)的方法的定义方法。 `Clear-ItemProperty` 此 cmdlet 允许用户删除属性的值。

- [IPropertyCmdletProvider 和 GetProperty](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty)方法定义了提供程序如何支持提供程序 cmdlet 的方式和[功能](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters)的方法的定义方法。 `Get-ItemProperty` 此 cmdlet 允许用户检索项的属性。

- [IPropertyCmdletProvider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty)和[IPropertyCmdletProvider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters)方法定义了提供程序支持 `Set-ItemProperty` 提供程序 cmdlet 的方式的方式，该方法定义了提供程序。 此 cmdlet 允许用户更新项的属性。

  **IDynamicPropertyCmdletProvider**接口定义以下用于实现特定提供程序 cmdlet 的方法：

- [IDynamicPropertyCmdletProvider 和 CopyProperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.CopyProperty)方法定义了提供程序如何支持提供程序 cmdlet 的方式和[功能](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.CopyPropertyDynamicParameters)的方法的定义方法。 `Copy-ItemProperty` 此 cmdlet 允许用户将属性及其值从一个位置复制到另一个位置。

- [IDynamicPropertyCmdletProvider 和 MoveProperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.MoveProperty)方法定义了提供程序如何支持提供程序 cmdlet 的方式和[功能](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.MovePropertyDynamicParameters)的方法的定义方法。 `Move-ItemProperty` 此 cmdlet 允许用户将属性及其值从一个位置移动到另一个位置。

- [IDynamicPropertyCmdletProvider 和 NewProperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewProperty)方法定义了提供程序如何支持提供程序 cmdlet 的方式和[功能](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewPropertyDynamicParameters)的方法的定义方法。 `New-ItemProperty` 此 cmdlet 允许用户创建新属性并设置其值。

- [IDynamicPropertyCmdletProvider 和 RemoveProperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemoveProperty)方法定义你的提供程序如何支持 cmdlet 的方式，即 "" 和 " [IDynamicPropertyCmdletProvider](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemovePropertyDynamicParameters) "。 `Remove-ItemProperty` 此 cmdlet 允许用户删除属性及其值。

- [IDynamicPropertyCmdletProvider 和 RenameProperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenameProperty)方法定义你的提供程序如何支持 cmdlet 的方式，即 "" 和 " [IDynamicPropertyCmdletProvider](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenamePropertyDynamicParameters) "。 `Rename-ItemProperty` 此 cmdlet 允许用户更改属性的名称。

## <a name="see-also"></a>请参阅

[about_Providers](/powershell/module/microsoft.powershell.core/about/about_providers)

[编写 Windows PowerShell 提供程序](./writing-a-windows-powershell-provider.md)
