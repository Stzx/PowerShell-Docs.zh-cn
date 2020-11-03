---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/get-packageprovider?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PackageProvider
ms.openlocfilehash: b3414b9f34787cc5285475d9de784fd779bd1431
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197647"
---
# Get-PackageProvider

## 摘要
返回连接到包管理的包提供程序的列表。

## SYNTAX

```
Get-PackageProvider [[-Name] <String[]>] [-ListAvailable] [-Force] [-ForceBootstrap] [<CommonParameters>]
```

## DESCRIPTION

**Install-packageprovider** cmdlet 将返回连接到包管理的包提供程序的列表。
这些提供程序的示例包括 PSModule、NuGet 和 Chocolatey。
你可以根据一个或多个提供程序名称的全部或部分来筛选结果。

## 示例

### 示例1：获取所有当前加载的包提供程序

```
PS C:\> Get-PackageProvider
```

此命令将获取当前在本地计算机上加载的所有包提供程序的列表。

### 示例2：获取所有可用的包提供程序

```
PS C:\> Get-PackageProvider -ListAvailable
```

此命令将获取本地计算机上可用的所有包提供程序的列表。

### 示例3：动态获取包提供程序

```
PS C:\> Get-PackageProvider -Name "Chocolatey" -ForceBootstrap
```

如果你的计算机未安装 Chocolatey 提供程序，则此命令将自动安装 Chocolatey 提供程序。

## PARAMETERS

### -Force

指示此 cmdlet 强制执行可强制执行的所有其他操作。
在 **install-packageprovider** 中，这意味着 *Force* 参数的作用与 *ForceBootstrap* 参数相同。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForceBootstrap

指示此 cmdlet 强制包管理自动安装包提供程序。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ListAvailable

获取所有已安装的提供程序。
**Install-packageprovider** 获取 **PSModulePath** 环境变量中列出的路径中的提供程序，以及包提供程序程序集文件夹：

**$env:P rogramFiles\PackageManagement\ProviderAssemblies * * * * $env： LOCALAPPDATA\PackageManagement\ProviderAssemblies**

如果没有此参数， **install-packageprovider** 仅获取当前会话中加载的提供程序。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

指定一个或多个提供程序名称或部分提供程序名称。
用逗号分隔多个提供程序名称。
此参数的有效值包括已与包一起安装的提供程序的名称;PackageManagement 附带一组默认提供程序，其中包括 **PSModule** 和 **MSI** 提供程序。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

## 输出

### Install-packageprovider []

## 注释

## 相关链接

[about_PackageManagement](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[Get-PackageSource](Get-PackageSource.md)

[Register-PackageSource](Register-PackageSource.md)

[Unregister-PackageSource](Unregister-PackageSource.md)

