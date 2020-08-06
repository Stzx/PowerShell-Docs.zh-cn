---
title: 提供程序示例 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 9eb8eb64bbe585ebd8024c0215853ff04a5c3e54
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87778437"
---
# <a name="provider-samples"></a>提供程序示例

本部分包含访问 Microsoft Access 数据库的访问接口的示例。 这些示例包括派生自所有基提供程序类的提供程序类。

## <a name="in-this-section"></a>本节内容

本节包括下列主题：

[AccessDBProviderSample01 示例](./accessdbprovidersample01.md)此示例显示了如何声明直接从[Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider)类派生的提供程序类。 仅出于完整性考虑而在此处包含此项。

[AccessDBProviderSample02](./accessdbprovidersample02.md)此示例演示如何覆盖[Newdrive * 和 Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) [*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)方法，以支持对 `New-PSDrive` 和 cmdlet 的调用的情况下出现的情况，请重写。 `Remove-PSDrive` 此示例中的提供程序类派生自[Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)类。

[AccessDBProviderSample03](./accessdbprovidersample03.md)此示例演示如何覆盖[Getitem * 和 Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) [*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)方法，以支持对 `Get-Item` 和 cmdlet 的调用的情况下出现的情况，请重写。 `Set-Item` 此示例中的提供程序类派生自[Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)类。

[AccessDBProviderSample04](./accessdbprovidersample04.md)此示例演示如何覆盖容器方法以支持对 `Copy-Item` 、 `Get-ChildItem` 、 `New-Item` 和 cmdlet 的调用 `Remove-Item` 。 当数据存储区包含属于容器的项时，应实现这些方法。 容器是包含公用父项下的子项的组。 此示例中的提供程序类派生自[Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)类。

[AccessDBProviderSample05](./accessdbprovidersample05.md)此示例演示如何覆盖容器方法以支持调用 `Move-Item` 和 `Join-Path` cmdlet。 当用户需要移动容器中的项时，如果数据存储区包含嵌套的容器，则应实现这些方法。 此示例中的提供程序类派生自[Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)类。

[AccessDBProviderSample06](./accessdbprovidersample06.md)此示例演示如何覆盖内容方法以支持对 `Clear-Content` 、 `Get-Content` 和 cmdlet 的调用 `Set-Content` 。 当用户需要管理数据存储区中的项的内容时，应实现这些方法。 此示例中的提供程序类派生自[Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)类，并且它实现了[Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider)接口的执行程序。）。

## <a name="see-also"></a>另请参阅

[编写 Windows PowerShell 提供程序](./writing-a-windows-powershell-provider.md)
