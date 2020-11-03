---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/test-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-DscConfiguration
ms.openlocfilehash: 25c8bc61976ce3940e0b9bd949fa3ee60728450d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197824"
---
# Test-DscConfiguration

## 摘要
测试节点上的实际配置是否与所需配置相匹配。

## SYNTAX

### ComputerNameSet（默认值）

```
Test-DscConfiguration [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-AsJob] [-Detailed] [<CommonParameters>]
```

### ComputerNameAndPathSet

```
Test-DscConfiguration [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-AsJob] [-Path] <String> [<CommonParameters>]
```

### ComputerNameAndReferenceConfigurationSet

```
Test-DscConfiguration [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-AsJob] -ReferenceConfiguration <String> [<CommonParameters>]
```

### CimSessionAndPathSet

```
Test-DscConfiguration [-ThrottleLimit <Int32>] -CimSession <CimSession[]> [-AsJob] [-Path] <String>
 [<CommonParameters>]
```

### CimSessionAndReferenceConfigurationSet

```
Test-DscConfiguration [-ThrottleLimit <Int32>] -CimSession <CimSession[]> [-AsJob]
 -ReferenceConfiguration <String> [<CommonParameters>]
```

### CimSessionSet

```
Test-DscConfiguration [-ThrottleLimit <Int32>] -CimSession <CimSession[]> [-AsJob] [-Detailed]
 [<CommonParameters>]
```

## DESCRIPTION
**Test-DscConfiguration** cmdlet 测试节点上的实际配置是否与所需配置相匹配。
通过使用计算机名称或通用信息模型 (CIM) 会话，指定想要测试配置的计算机。
如果不指定目标计算机，则该 cmdlet 将测试本地计算机的配置。

如果所需配置和实际配置匹配，则该 cmdlet 将返回字符串值 "True"。
否则，它将返回字符串值 "False"。

## 示例

### 示例 1：测试本地计算机的配置

```
PS C:\> Test-DscConfiguration
```

此命令将测试本地计算机的配置。

### 示例 2：测试指定计算机的配置

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Test-DscConfiguration -CimSession $Session
```

此示例将测试由 CIM 会话指定的计算机的配置。
该示例为名为 Server01 的计算机创建 CIM 会话，以供与 cmdlet 一起使用。
或者，创建一个 CIM 会话数组以将 cmdlet 应用到多个指定的计算机。

第一个命令通过使用 **New-CimSession** cmdlet 创建 CIM 会话，然后将 **CimSession** 对象存储在 $Session 变量中。
该命令会提示你输入密码。
要了解详情，请键入 `Get-Help New-CimSession`。

第二个命令测试由存储在 $Session 变量中的 **CimSession** 对象标识的计算机（在此示例中，是名为 Server01 的计算机）的配置。

### 示例 3：带有详细结果的配置测试

```
PS C:\> Test-DscConfiguration -ComputerName "Server01", "Server02", "Server03" -Detailed
```

此命令测试由 ComputerName  参数指定的一组计算机的配置，并返回详细信息（包括总体状态、处于所需状态的资源、未处于所需状态的资源以及计算机名称）。

### 示例 4：测试文件夹中指定的配置

```
PS C:\> Test-DscConfiguration -Path "C:\Dsc\Configurations"
```

此命令测试在 Path  参数指定的文件夹中定义的配置。
针对一组计算机测试配置，每台计算机以配置文件的文件名标识。

### 示例 5：测试文件中指定的配置

```
PS C:\> Test-DscConfiguration -ReferenceConfiguration "C:\Dsc\Configurations\WebServer.mof" -ComputerName "Server01", "Server02", "Server03"
```

针对 ComputerName  参数指定的一组计算机，此命令测试文件中定义的配置。

## PARAMETERS

### -AsJob
指示此 cmdlet 将命令作为后台作业运行。

如果指定 AsJob  参数，该命令将返回表示作业的对象，然后显示命令提示符。
作业完成前，可以继续在此会话中工作。
作业在本地计算机上创建，并且来自远程计算机的结果将自动返回本地计算机。
若要管理作业，请使用 Job cmdlet。
若要获取作业结果，请使用 Receive-Job cmdlet。

若要使用此参数，必须为本地计算机和远程计算机配置远程处理，并且在 Windows Vista 以及更高版本的 Windows 操作系统上，还必须使用“以管理员身份运行”选项打开 Windows PowerShell。
有关详细信息，请参阅 [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md)。

有关 Windows PowerShell 后台作业的详细信息，请参阅 [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) 和 [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md)。

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

### -CimSession
在远程会话中或在远程计算机上运行 cmdlet。
输入计算机名或会话对象，例如 [CimSession](/powershell/module/cimcmdlets/new-cimsession) 或 [CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet 的输出。
默认为本地计算机上的当前会话。

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionAndPathSet, CimSessionAndReferenceConfigurationSet, CimSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName
指定此 cmdlet 要测试配置的一批计算机名称。
该 cmdlet 测试由这些计算机的 Path  参数指定的位置中的配置文件。

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet, ComputerNameAndPathSet, ComputerNameAndReferenceConfigurationSet
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Credential
针对目标计算机，指定用户名和密码作为 **PSCredential** 对象。
若要获取 **PSCredential** 对象，请使用 Get-Credential cmdlet。
要了解详情，请键入 `Get-Help Get-Credential`。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameSet, ComputerNameAndPathSet, ComputerNameAndReferenceConfigurationSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Detailed
指示此 cmdlet 返回与节点所需状态进行比较的配置文档的详细结果。
结果中包括总体状态、处于所需状态的资源、未处于所需状态的资源以及计算机名称等信息。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerNameSet, CimSessionSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
指定包含配置文档文件的文件夹路径。
针对由 ComputerName  或 CimSession  参数指定的计算机所需状态，该 cmdlet 测试配置。

```yaml
Type: System.String
Parameter Sets: ComputerNameAndPathSet, CimSessionAndPathSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReferenceConfiguration
指定配置文档文件的路径。
针对由 ComputerName  或 CimSession  参数指定的计算机实际状态，该 cmdlet 测试配置。

```yaml
Type: System.String
Parameter Sets: ComputerNameAndReferenceConfigurationSet, CimSessionAndReferenceConfigurationSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
指定可为运行 cmdlet 而确立的操作的最大数量。
如果省略此参数或输入的值 `0` ，则 Windows PowerShell 会根据计算机上正在运行的 CIM cmdlet 的数目计算该 cmdlet 的最佳限制。
该限制仅适用于当前 cmdlet，不适用于会话或计算机。

```yaml
Type: System.Int32
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

## 输出

## 注释

## 相关链接

[Windows PowerShell Desired State Configuration 概述](/powershell/scripting/dsc/overview/dscforengineers)

[Get-DscConfiguration](Get-DscConfiguration.md)

[Get-DscConfigurationStatus](Get-DscConfigurationStatus.md)

[Restore-DscConfiguration](Restore-DscConfiguration.md)

[Start-DscConfiguration](Start-DscConfiguration.md)
