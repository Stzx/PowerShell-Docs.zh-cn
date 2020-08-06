---
title: AccessDBProviderSample05 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 67a10d9192350b339da1b82d9eb367ee4af6ef86
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786843"
---
# <a name="accessdbprovidersample05"></a>AccessDBProviderSample05

此示例演示如何覆盖容器方法以支持调用 `Move-Item` 和 `Join-Path` cmdlet。 当用户需要移动容器中的项时，如果数据存储区包含嵌套的容器，则应实现这些方法。 此示例中的提供程序类派生自[Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)类。

## <a name="demonstrates"></a>演示

> [!IMPORTANT]
> 提供程序类最有可能派生自以下类之一，并可能实现其他提供程序接口：
>
> - " [Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) " 类。 请参阅[AccessDBProviderSample03](./accessdbprovidersample03.md)。
> - " [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) " 类。 请参阅[AccessDBProviderSample04](./accessdbprovidersample04.md)。
> - " [Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) " 类。
>
> 有关根据提供程序功能选择要从哪个提供程序类派生的详细信息，请参阅[设计你的 Windows PowerShell 提供程序](./provider-types.md)。

此示例对下列内容进行了说明：

- 声明 `CmdletProvider` 特性。

- 定义一个派生自[Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)类的提供程序类。

- 覆盖[Navigationcmdletprovider. Moveitem *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem)方法以更改 cmdlet 的行为 `Move-Item` ，允许用户将项从一个位置移到另一个位置。  (此示例不显示如何将动态参数添加到 `Move-Item` cmdlet。 ) 

- 覆盖[Navigationcmdletprovider. Makepath *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath)方法，以更改 cmdlet 的行为方式 `Join-Path` 。

- 正在重写[Navigationcmdletprovider. Isitemcontainer *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer)方法。

- 正在重写[Navigationcmdletprovider. Getchildname *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName)方法。

- 正在重写[Navigationcmdletprovider. Getparentpath *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath)方法。

- 正在重写[Navigationcmdletprovider. Normalizerelativepath *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath)方法。

## <a name="example"></a>示例

此示例演示如何覆盖在 Microsoft Access 数据库中移动项所需的方法。

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample05/AccessDBProviderSample05.cs" range="11-1960":::

## <a name="see-also"></a>另请参阅

["Itemcmdletprovider"。](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

["Containercmdletprovider"。](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

["Navigationcmdletprovider"。](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[设计 Windows PowerShell 提供程序](./provider-types.md)
