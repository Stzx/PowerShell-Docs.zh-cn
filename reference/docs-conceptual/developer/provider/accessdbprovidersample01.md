---
ms.date: 09/13/2016
ms.topic: reference
title: AccessDBProviderSample01
description: AccessDBProviderSample01
ms.openlocfilehash: 8bdfa3ad492935a22ce06846294c02961cab2c65
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653757"
---
# <a name="accessdbprovidersample01"></a>AccessDBProviderSample01

此示例演示如何声明一个直接从 [Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) 类派生的提供程序类。 仅出于完整性考虑而在此处包含此项。

## <a name="demonstrates"></a>演示

> [!IMPORTANT]
> 提供程序类最有可能派生自以下类之一，并可能实现其他提供程序接口：
>
> - " [Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) " 类。 请参阅 [AccessDBProviderSample03](./accessdbprovidersample03.md)。
> - " [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) " 类。 请参阅 [AccessDBProviderSample04](./accessdbprovidersample04.md)。
> - " [Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) " 类。 请参阅 [AccessDBProviderSample05](./accessdbprovidersample05.md)。
>
> 有关根据提供程序功能选择要从哪个提供程序类派生的详细信息，请参阅 [设计你的 Windows PowerShell 提供程序](./provider-types.md)。

此示例对下列内容进行了说明：

- 声明 `CmdletProvider` 特性。

- 定义直接从 [Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) 类中派生的提供程序类。

## <a name="example"></a>示例

此示例演示如何定义提供程序类以及如何声明 `CmdletProvider` 特性。

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample01/AccessDBProviderSample01.cs" range="11-30":::

## <a name="see-also"></a>另请参阅

["Itemcmdletprovider"。](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

["Containercmdletprovider"。](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

["Navigationcmdletprovider"。](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[设计 Windows PowerShell 提供程序](./provider-types.md)
