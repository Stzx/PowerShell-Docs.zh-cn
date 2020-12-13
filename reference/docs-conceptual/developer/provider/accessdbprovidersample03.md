---
ms.date: 09/13/2016
ms.topic: reference
title: AccessDBProviderSample03
description: AccessDBProviderSample03
ms.openlocfilehash: bfd402903a9023b58dec8865663e3d649a50e1e1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667396"
---
# <a name="accessdbprovidersample03"></a>AccessDBProviderSample03

此示例演示如何覆盖[Getitem * 和 Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) [*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)方法，以支持对 `Get-Item` 和 cmdlet 的调用的情况下出现的情况，请重写。 `Set-Item` 此示例中的提供程序类派生自 [Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) 类。

## <a name="demonstrates"></a>演示

> [!IMPORTANT]
> 提供程序类最有可能派生自以下类之一，并可能实现其他提供程序接口：
>
> - " [Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) " 类。
> - " [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) " 类。 请参阅 [AccessDBProviderSample04](./accessdbprovidersample04.md)。
> - " [Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) " 类。 请参阅 [AccessDBProviderSample05](./accessdbprovidersample05.md)。
>
> 有关根据提供程序功能选择要从哪个提供程序类派生的详细信息，请参阅 [设计你的 Windows PowerShell 提供程序](./provider-types.md)。

此示例对下列内容进行了说明：

- 声明 `CmdletProvider` 特性。
- 定义一个派生自 [Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) 类的提供程序类。
- 覆盖 [Drivecmdletprovider. Newdrive *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) 方法，以更改 cmdlet 的行为 `New-PSDrive` ，从而允许用户创建新的驱动器。
   (此示例不显示如何将动态参数添加到 `New-PSDrive` cmdlet。 ) 
- 覆盖 [Drivecmdletprovider. Removedrive *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) 方法，以支持删除现有驱动器。
- 覆盖 [Itemcmdletprovider. Getitem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) 方法，以更改 cmdlet 的行为 `Get-Item` ，从而允许用户从数据存储中检索项。  (此示例不显示如何将动态参数添加到 `Get-Item` cmdlet。 ) 
- 覆盖 [Setitem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) 方法以更改 cmdlet 的行为 `Set-Item` ，使用户能够更新数据存储区中的项，从而使其 Itemcmdletprovider。  (此示例不显示如何将动态参数添加到 `Get-Item` cmdlet。 ) 
- 覆盖 [Itemcmdletprovider. Itemexists *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) 方法，以更改 cmdlet 的行为方式 `Test-Path` 。  (此示例不显示如何将动态参数添加到 `Test-Path` cmdlet。 ) 
- 覆盖 [Itemcmdletprovider. Isvalidpath *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) 方法，以确定提供的路径是否有效。

## <a name="example"></a>示例

此示例演示如何覆盖获取和设置 Microsoft Access 数据库中的项所需的方法。

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample03/AccessDBProviderSample03.cs" range="11-976":::

## <a name="see-also"></a>另请参阅

["Itemcmdletprovider"。](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

["Containercmdletprovider"。](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

["Navigationcmdletprovider"。](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[设计 Windows PowerShell 提供程序](./provider-types.md)
