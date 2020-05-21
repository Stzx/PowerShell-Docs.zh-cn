---
title: 提供程序 cmdlet 参数 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3d09eaa-924f-4e2b-adfb-14bb729090dd
caps.latest.revision: 8
ms.openlocfilehash: 8ce13032a55d164121a073ef94086dc1de09b902
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83564200"
---
# <a name="provider-cmdlet-parameters"></a>提供程序 cmdlet 参数

提供程序 cmdlet 附带一组静态参数，这些参数可用于支持 cmdlet 的所有提供程序，以及在用户为提供程序 cmdlet 的某些静态参数指定特定值时添加的动态参数。

## <a name="provider-cmdlet-static-parameters"></a>提供程序 Cmdlet 静态参数

静态参数由 Windows PowerShell 定义。 许多参数由 Windows PowerShell 实现，以在所有提供程序之间提供一致性，并提供更简单的开发体验。 这些参数的示例包括 `literalPath` cmdlet 的、 `exclude` 和 `include` 参数 `Get-Item` 。 可以覆盖这些参数的较小集，以提供特定于提供程序的操作。 这些参数的示例包括 `Path` cmdlet 的和 `Value` 参数 `Set-Item` 。 下面是可为提供程序 cmdlet 覆盖的参数的列表。

`Clear-Content`cmdlet 可以通过实现 Icontentcmdletprovider，定义提供程序将如何使用传递给 cmdlet 的参数的值的方式 `Path` `Clear-Content` ： [Clearcontent *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent)方法。

`Clear-Item`cmdlet 可以通过实现 Itemcmdletprovider，定义提供程序将如何使用传递给 cmdlet 的参数的值的方式 `Path` `Clear-Item` ： [Clearitem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem)方法。

`Clear-ItemProperty`cmdlet 可以 `Path` `Name` `Clear-ItemProperty` 通过实现[Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) ，定义提供程序将如何使用传递给 cmdlet 的和参数的值，方法是实现。

`Copy-Item`cmdlet 可以通过实现 ContainerCmdletProvider，定义提供程序如何使用传递到 `Path` cmdlet 的、和参数的值，以及如何 `Destination` `Recurse` `Copy-Item` 实现[CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)方法。

ChildItems cmdlet 可通过实现 Containercmdletprovider 和 Getchilditems * 方法，定义提供程序将如何使用传递给 cmdlet 的和参数的值的方式 `Path` `Recurse` `Get-ChildItem` 。 [* 和](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) [*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames)方法的实现方法。

`Get-Content`cmdlet 可以通过实现 Icontentcmdletprovider，定义提供程序将如何使用传递给 cmdlet 的参数的值的方式 `Path` `Get-Content` ： [Getcontentreader *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader)方法。

`Get-Item`cmdlet 可以通过实现 Itemcmdletprovider，定义提供程序将如何使用传递给 cmdlet 的参数的值的方式 `Path` `Get-Item` ： [Getitem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem)方法。

`Get-ItemProperty`cmdlet 可以 `Path` `Name` `Get-ItemProperty` 通过实现[Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) ，定义提供程序将如何使用传递给 cmdlet 的和参数的值，方法是实现。

`Invoke-Item`cmdlet 可以通过实现 Itemcmdletprovider，定义提供程序将如何使用传递给 cmdlet 的参数的值的方式 `Path` `Invoke-Item` ： [Invokedefaultaction *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction)方法。

`Move-Item`cmdlet 可以 `Path` `Destination` `Move-Item` 通过实现[Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) ，定义提供程序将如何使用传递给 cmdlet 的和参数的值，方法是实现。

`New-Item`cmdlet 可以通过实现 Containercmdletprovider，定义提供程序如何使用传递到 `Path` cmdlet 的、和参数的值，以及如何 `ItemType` `Value` `New-Item` 实现[Newitem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)方法。

`New-ItemProperty`cmdlet 可以通过实现 Registryprovider，定义提供程序将如何使用传递给 `Path` cmdlet 的、、和参数的值， `Name` `PropertyType` 并 `Value` `New-ItemProperty` 实现[Microsoft.PowerShell.Commands.Registryprovider.Newproperty*](/dotnet/api/Microsoft.PowerShell.Commands.RegistryProvider.NewProperty)此方法。

`Remove-Item`你可以通过实现 Containercmdletprovider，定义提供程序将如何使用传递给 cmdlet 的和参数的值的方式 `Path` `Recurse` `Remove-Item` ： [Removeitem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem)方法。

`Remove-ItemProperty`你可以通过实现 Idynamicpropertycmdletprovider，定义提供程序将如何使用传递给 cmdlet 的和参数的值的方式 `Path` `Name` `Remove-ItemProperty` ： [Removeproperty *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemoveProperty)方法。

`Rename-Item`cmdlet 可以 `Path` `NewName` `Rename-Item` 通过实现[Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) ，定义提供程序将如何使用传递给 cmdlet 的和参数的值，方法是实现。

`Rename-ItemProperty`你可以通过实现 Idynamicpropertycmdletprovider，定义提供程序如何使用传递给 `Path` cmdlet 的、和参数的值， `NewName` 并 `Name` `Rename-ItemProperty` 实现此[功能](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenameProperty)。

`Set-Content`cmdlet 可以通过实现 Icontentcmdletprovider，定义提供程序将如何使用传递给 cmdlet 的参数的值的方式 `Path` `Set-Content` ： [Getcontentwriter *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter)方法。

`Set-Item`cmdlet 可以 `Path` `Value` `Set-Item` 通过实现[Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) ，定义提供程序将如何使用传递给 cmdlet 的和参数的值，方法是实现。

`Set-ItemProperty`cmdlet 可以 `Path` `Value` `Set-Item` 通过实现[Ipropertycmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty)方法，定义提供程序将如何使用传递给 cmdlet 的和参数的值的方式。

`Test-Path`cmdlet 可以通过实现 Itemcmdletprovider，定义提供程序将如何使用传递给 cmdlet 的参数的值的方式 `Path` `Test-Path` ： [Invokedefaultaction *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction)方法。

此外，不能指定这些参数的特征，例如它们是否是可选的或必需的，也不能为这些参数指定别名或指定任何验证属性。 与此相反，你可以通过使用属性（如属性）在独立 cmdlet 中指定参数特征 `Parameters` 。

## <a name="provider-cmdlet-dynamic-parameters"></a>提供程序 Cmdlet 动态参数

Cmdlet 提供程序的动态参数类似于独立 cmdlet 的动态提供程序。 在这两种情况下，当用户为一个默认参数（如参数）指定某个值时，将参数添加到 cmdlet `path` 。 但是，并非所有静态参数都可用于触发动态参数的添加。 有关动态参数的详细信息，请参阅[提供程序 Cmdlet 动态参数](./provider-cmdlet-dynamic-parameters.md)。

## <a name="see-also"></a>另请参阅

[提供程序 Cmdlet 动态参数](./provider-cmdlet-dynamic-parameters.md)

[编写 Windows PowerShell 提供程序](./writing-a-windows-powershell-provider.md)
