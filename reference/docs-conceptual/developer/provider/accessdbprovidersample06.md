---
ms.date: 09/13/2016
ms.topic: reference
title: AccessDBProviderSample06
description: AccessDBProviderSample06
ms.openlocfilehash: a2037c6f13ba24ba2dcb4ffecbd802566452d64e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92656938"
---
# <a name="accessdbprovidersample06"></a>AccessDBProviderSample06

此示例演示如何覆盖内容方法以支持对 `Clear-Content` 、 `Get-Content` 和 cmdlet 的调用 `Set-Content` 。 当用户需要管理数据存储区中的项的内容时，应实现这些方法。 此示例中的提供程序类派生自 [Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) 类，并且它实现了 [Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) 接口的执行程序。）。

## <a name="demonstrates"></a>演示

> [!IMPORTANT]
> 提供程序类最有可能派生自以下类之一，并可能实现其他提供程序接口：
>
> - " [Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) " 类。 请参阅 [AccessDBProviderSample03](./accessdbprovidersample03.md)。
> - " [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) " 类。 请参阅 [AccessDBProviderSample04](./accessdbprovidersample04.md)。
> - " [Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) " 类。
>
> 有关根据提供程序功能选择要从哪个提供程序类派生的详细信息，请参阅 [设计你的 Windows PowerShell 提供程序](./provider-types.md)。

此示例对下列内容进行了说明：

- 声明 `CmdletProvider` 特性。
- 定义一个派生自 [Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) 类的提供程序类，并声明一个声明 [Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) 接口的提供程序类。
- 覆盖 [Clearcontent *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) 方法以更改 cmdlet 的行为 `Clear-Content` ，从而使用户能够从项中删除内容。 Icontentcmdletprovider * 方法。  (此示例不显示如何将动态参数添加到 `Clear-Content` cmdlet。 ) 
- 覆盖 Getcontentreader * 方法以更改 cmdlet 的行为，使用户能够检索项的内容。 [Icontentcmdletprovider. *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) 方法用于更改 `Get-Content` 项的内容。  (此示例不显示如何将动态参数添加到 `Get-Content` cmdlet。 ) 。
- 覆盖 [Getcontentwriter *](/dotnet/api/Microsoft.PowerShell.Commands.FileSystemProvider.GetContentWriter) 方法，以更改 cmdlet 的行为 `Set-Content` ，从而使用户能够更新项的内容。 Filesystemprovider。  (此示例不显示如何将动态参数添加到 `Set-Content` cmdlet。 ) 

## <a name="example"></a>示例

此示例演示如何覆盖清除、获取和设置 Microsoft Access 数据库中项的内容所需的方法。

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs" range="11-2399":::

## <a name="see-also"></a>另请参阅

["Itemcmdletprovider"。](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

["Containercmdletprovider"。](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

["Navigationcmdletprovider"。](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[设计 Windows PowerShell 提供程序](./provider-types.md)
