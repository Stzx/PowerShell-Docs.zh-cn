---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssnapin?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSnapin
ms.openlocfilehash: 472a4c8fbb9eb0d37827aff4fcfd6bb9a67f4743
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197430"
---
# Get-PSSnapin

## 摘要
获取计算机上的 Windows PowerShell 管理单元。

## SYNTAX

```
Get-PSSnapin [[-Name] <String[]>] [-Registered] [<CommonParameters>]
```

## DESCRIPTION
**Add-pssnapin** cmdlet 将获取已添加到当前会话中或已在系统上注册的 Windows PowerShell 管理单元。
此 cmdlet 按照检测到的顺序列出这些管理单元。

**Add-pssnapin** 仅获取已注册的管理单元。若要注册 Windows PowerShell 管理单元，请使用 Microsoft .NET Framework 2.0 附带的 Installutil.exe 工具。
有关详细信息，请参阅 MSDN library 中的 " [如何注册 cmdlet、提供程序和主机应用程序](https://go.microsoft.com/fwlink/?LinkID=143619) "。

从 Windows PowerShell 3.0 开始，Windows PowerShell 中包含的核心命令打包在模块中。
例外情况是 **Microsoft.PowerShell.Core** ，它是一个管理单元 (PSSnapin)。
默认情况下，仅将 **Microsoft.PowerShell.Core** 管理单元添加到会话中。
首次使用时自动导入模块，而且可以使用 Import-Module cmdlet 导入它们。

## 示例

### 示例1：获取当前加载的管理单元

```
PS C:\> Get-PSSnapIn
```

此命令获取当前在会话中加载的 Windows PowerShell 管理单元。
这包括与 Windows PowerShell 一起安装的以及添加到此会话的那些管理单元。

### 示例2：获取已注册的管理单元

```
PS C:\> get-PSSnapIn -Registered
```

此命令获取已在计算机上注册的 Windows PowerShell 管理单元，包括那些已添加到会话的管理单元。
输出不包括与 Windows PowerShell 或 Windows PowerShell 管理单元动态链接库 (DLL) 一起安装的管理单元，它们尚未在系统上注册。

### 示例3：获取与字符串匹配的当前管理单元

```
PS C:\> Get-PSSnapIn -Name smp*
```

此命令将获取当前会话中名称以 smp 开头的 Windows PowerShell 管理单元。

## PARAMETERS

### -Name
指定管理单元名称的数组。
此 cmdlet 仅获取指定的 Windows PowerShell 管理单元。允许使用通配符。

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

### -Registered
指示此 cmdlet 获取已在系统上注册的 Windows PowerShell 管理单元，即使尚未将它们添加到会话中也是如此。

与 Windows PowerShell 一起安装的管理单元不会出现在此列表中。

如果没有此参数， **add-pssnapin** 将获取已添加到会话中的 Windows PowerShell 管理单元。

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

### CommonParameters
此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### 无
不能通过管道将输入传递给此 cmdlet。

## 输出

### System.Management.Automation.PSSnapInInfo
Get-PSSnapin 将返回它所获取的每个管理单元的对象。

## 注释

* 从 Windows PowerShell 3.0 开始，随 Windows PowerShell 一起安装的核心命令打包在模块中。 在 Windows PowerShell 2.0 和在更高版本的 Windows PowerShell 中创建旧样式会话的主机程序中，核心命令打包在 ( **add-pssnapin** ) 的管理单元中。 **Microsoft.PowerShell.Core** 是例外情况，它始终是一个管理单元。 此外，远程会话（如 New-PSSession cmdlet 启动的会话）是包括核心管理单元的旧样式会话。

  有关 **CreateDefault2** 方法的详细信息，请参阅 MSDN library 中的 [CreateDefault2 方法](https://msdn.microsoft.com/library/system.management.automation.runspaces.initialsessionstate.createdefault2) 。

## 相关链接

[Add-PSSnapin](Add-PSSnapin.md)

[Remove-PSSnapin](Remove-PSSnapin.md)
