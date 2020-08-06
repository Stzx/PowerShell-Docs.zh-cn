---
title: AccessDBProviderSample04 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 097591528fd12cdf9f134a0fd8a0bd278f216fab
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786860"
---
# <a name="accessdbprovidersample04"></a>AccessDBProviderSample04

此示例演示如何覆盖容器方法以支持对 `Copy-Item` 、 `Get-ChildItem` 、 `New-Item` 和 cmdlet 的调用 `Remove-Item` 。 当数据存储区包含属于容器的项时，应实现这些方法。 容器是包含公用父项下的子项的组。 此示例中的提供程序类派生自[Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)类。

## <a name="demonstrates"></a>演示

> [!IMPORTANT]
> 你的提供程序类最有可能派生自[Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

此示例对下列内容进行了说明：

- 声明 `CmdletProvider` 特性。
- 定义一个派生自[Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)类的提供程序类。
- 覆盖[ContainerCmdletProvider CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)方法以更改 cmdlet 的行为，该行为 `Copy-Item` 允许用户将项从一个位置复制到另一个位置。  (此示例不显示如何将动态参数添加到 `Copy-Item` cmdlet。 ) 
- 覆盖[Getchilditems *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)方法，以更改 ChildItems cmdlet 的行为，该行为允许用户检索父项的子项目。 Containercmdletprovider）的行为。  (此示例不显示如何将动态参数添加到 ChildItems cmdlet。 ) 
- 当指定了 cmdlet 的参数时，覆盖 Getchildnames * 方法，以更改 ChildItems cmdlet 的行为。 [Containercmdletprovider *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames)方法。 `Name`
- 覆盖[Containercmdletprovider. Newitem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)方法，以更改 cmdlet 的行为 `New-Item` ，这允许用户将项添加到数据存储区。  (此示例不显示如何将动态参数添加到 `New-Item` cmdlet。 ) 
- 覆盖[Containercmdletprovider. Removeitem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem)方法，以更改 cmdlet 的行为方式 `Remove-Item` 。  (此示例不显示如何将动态参数添加到 `Remove-Item` cmdlet。 ) 

## <a name="example"></a>示例

此示例演示如何覆盖复制、创建和删除项所需的方法，以及用于获取父项的子项的方法。

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs" range="11-1635":::

## <a name="see-also"></a>另请参阅

["Itemcmdletprovider"。](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

["Containercmdletprovider"。](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

["Navigationcmdletprovider"。](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[设计 Windows PowerShell 提供程序](./provider-types.md)
