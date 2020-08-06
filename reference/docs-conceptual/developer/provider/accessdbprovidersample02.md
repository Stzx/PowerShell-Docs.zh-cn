---
title: AccessDBProviderSample02 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e9a0444d17bec230633e1dd1709455f6ba83dd5c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786894"
---
# <a name="accessdbprovidersample02"></a>AccessDBProviderSample02

此示例演示如何覆盖[Newdrive * 和 Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) [*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)方法，以支持对 `New-PSDrive` 和 cmdlet 的调用的情况下出现的情况，请重写。 `Remove-PSDrive` 此示例中的提供程序类派生自[Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)类。

## <a name="demonstrates"></a>演示

> [!IMPORTANT]
> 提供程序类最有可能派生自以下类之一，并可能实现其他提供程序接口：
>
> - " [Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) " 类。 请参阅[AccessDBProviderSample03](./accessdbprovidersample03.md)。
> - " [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) " 类。 请参阅[AccessDBProviderSample04](./accessdbprovidersample04.md)。
> - " [Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) " 类。 请参阅[AccessDBProviderSample05](./accessdbprovidersample05.md)。
>
> 有关根据提供程序功能选择要从哪个提供程序类派生的详细信息，请参阅[设计你的 Windows PowerShell 提供程序](./provider-types.md)。

此示例对下列内容进行了说明：

- 声明 `CmdletProvider` 特性。

- 定义从[Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)类中驱动的提供程序类。

- 覆盖[Drivecmdletprovider. Newdrive *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)方法，以支持创建新驱动器。  (此示例不显示如何将动态参数添加到 `New-PSDrive` cmdlet。 ) 

- 覆盖[Drivecmdletprovider. Removedrive *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)方法，以支持删除现有驱动器。

## <a name="example"></a>示例

此示例演示如何重写 Drivecmdletprovider * 和[Newdrive *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)和[Drivecmdletprovider.. Removedrive *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)方法的操作方式。 对于此示例提供程序，创建驱动器时，其连接信息存储在对象中 `AccessDBPsDriveInfo` 。

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs" range="11-154":::

## <a name="see-also"></a>另请参阅

["Itemcmdletprovider"。](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

["Containercmdletprovider"。](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

["Navigationcmdletprovider"。](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[设计 Windows PowerShell 提供程序](./provider-types.md)
