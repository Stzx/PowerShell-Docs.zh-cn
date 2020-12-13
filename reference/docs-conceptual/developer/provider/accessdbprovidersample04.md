---
ms.date: 09/13/2016
ms.topic: reference
title: AccessDBProviderSample04
description: AccessDBProviderSample04
ms.openlocfilehash: 962d0ab673ff797a60b56ccae7a16a810cc43c58
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649036"
---
# <a name="accessdbprovidersample04"></a>AccessDBProviderSample04

此示例演示如何覆盖容器方法以支持对 `Copy-Item` 、 `Get-ChildItem` 、 `New-Item` 和 cmdlet 的调用 `Remove-Item` 。 当数据存储区包含属于容器的项时，应实现这些方法。 容器是包含公用父项下的子项的组。 此示例中的提供程序类派生自 [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) 类。

## <a name="demonstrates"></a>演示

> [!IMPORTANT]
> 你的提供程序类最有可能派生自 [Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

此示例对下列内容进行了说明：

- 声明 `CmdletProvider` 特性。
- 定义一个派生自 [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) 类的提供程序类。
- 覆盖 [ContainerCmdletProvider CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) 方法以更改 cmdlet 的行为，该行为 `Copy-Item` 允许用户将项从一个位置复制到另一个位置。  (此示例不显示如何将动态参数添加到 `Copy-Item` cmdlet。 ) 
- 覆盖 [Containercmdletprovider. Getchilditems *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) 方法，以更改 Get-ChildItems cmdlet 的行为，该行为允许用户检索父项的子项目。）  (此示例不显示如何将动态参数添加到 Get-ChildItems cmdlet。 ) 
- 当指定 cmdlet 的参数时，覆盖[Containercmdletprovider 的 Getchildnames *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames)方法，以更改 Get-ChildItems cmdlet 的行为方式。 `Name`
- 覆盖 [Containercmdletprovider. Newitem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) 方法，以更改 cmdlet 的行为 `New-Item` ，这允许用户将项添加到数据存储区。  (此示例不显示如何将动态参数添加到 `New-Item` cmdlet。 ) 
- 覆盖 [Containercmdletprovider. Removeitem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) 方法，以更改 cmdlet 的行为方式 `Remove-Item` 。  (此示例不显示如何将动态参数添加到 `Remove-Item` cmdlet。 ) 

## <a name="example"></a>示例

此示例演示如何覆盖复制、创建和删除项所需的方法，以及用于获取父项的子项的方法。

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs" range="11-1635":::

## <a name="see-also"></a>另请参阅

["Itemcmdletprovider"。](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

["Containercmdletprovider"。](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

["Navigationcmdletprovider"。](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[设计 Windows PowerShell 提供程序](./provider-types.md)
