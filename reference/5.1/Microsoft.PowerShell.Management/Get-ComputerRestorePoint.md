---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/13/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-computerrestorepoint?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ComputerRestorePoint
ms.openlocfilehash: 73819aafee9ed1911354daf9af23eedff0a3e14c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198300"
---
# Get-ComputerRestorePoint

## 摘要
获取本地计算机上的还原点。

## SYNTAX

### ID（默认值）

```
Get-ComputerRestorePoint [[-RestorePoint] <Int32[]>] [<CommonParameters>]
```

### LastStatus

```
Get-ComputerRestorePoint -LastStatus [<CommonParameters>]
```

## DESCRIPTION

`Get-ComputerRestorePoint`Cmdlet 将获取本地计算机的系统还原点。 而且，它还可以显示最近一次尝试还原计算机的状态。

你可以使用中的信息 `Get-ComputerRestorePoint` 来选择还原点。 例如，使用序列号来标识 cmdlet 的还原点 `Restore-Computer` 。

`Get-ComputerRestorePoint`仅在客户端操作系统（例如 windows 10、windows 7、Windows Vista 和 WINDOWS XP）上支持系统还原点和 cmdlet。

## 示例

### 示例1：获取所有系统还原点

在此示例中， `Get-ComputerRestorePoint` 获取本地计算机的所有系统还原点。

```powershell
Get-ComputerRestorePoint
```

```Output
CreationTime           Description                    SequenceNumber    EventType         RestorePointType
------------           -----------                    --------------    ---------         ----------------
7/30/2019 09:17:24     Windows Update                 4                 BEGIN_SYSTEM_C... 17
8/5/2019  08:15:37     Installed PowerShell 7-prev... 5                 BEGIN_SYSTEM_C... APPLICATION_INSTALL
8/7/2019  12:56:45     Installed PowerShell 6-x64     6                 BEGIN_SYSTEM_C... APPLICATION_INSTALL
```

### 示例2：获取特定序列号

此示例获取特定序列号的系统还原点。

```powershell
Get-ComputerRestorePoint -RestorePoint 4, 5
```

```Output
CreationTime           Description                    SequenceNumber    EventType         RestorePointType
------------           -----------                    --------------    ---------         ----------------
7/30/2019 09:17:24     Windows Update                 4                 BEGIN_SYSTEM_C... 17
8/5/2019  08:15:37     Installed PowerShell 7-prev... 5                 BEGIN_SYSTEM_C... APPLICATION_INSTALL
```

`Get-ComputerRestorePoint` 使用 **RestorePoint** 参数来指定序列号的逗号分隔数组。

### 示例3：显示系统还原的状态

此示例显示本地计算机上最近的系统还原的状态。

```powershell
Get-ComputerRestorePoint -LastStatus
```

```Output
The last attempt to restore the computer failed.
```

`Get-ComputerRestorePoint` 使用 **LastStatus** 参数显示最近的系统还原的结果。

### 示例4：使用表达式转换 CreationTime

`Get-ComputerRestorePoint` 将 **CreationTime** 作为 (WMI) 日期和时间字符串的 Windows Management Instrumentation 输出。

在此示例中，变量存储了一个表达式，该表达式将 **CreationTime** 字符串转换为 **DateTime** 对象。 若要在转换前查看 **CreationTime** 字符串，请使用命令（如） `((Get-ComputerRestorePoint).CreationTime)` 。 有关 WMI 日期和时间字符串的详细信息，请参阅 [CIM_DATETIME](/windows/win32/wmisdk/cim-datetime)。

```powershell
$date = @{Label="Date"; Expression={$_.ConvertToDateTime($_.CreationTime)}}
Get-ComputerRestorePoint | Select-Object -Property SequenceNumber, $date, Description
```

```Output
SequenceNumber   Date                 Description
--------------   ----                 -----------
             4   7/30/2019 09:17:24   Windows Update
             5   8/5/2019  08:15:37   Installed PowerShell 7-preview-x64
             6   8/7/2019  12:56:45   Installed PowerShell 6-x64
```

`$date`变量使用 **ConvertToDateTime** 方法的表达式存储哈希表。 表达式将 **CreationTime** 属性的值从 WMI 字符串转换为 **DateTime** 对象。

`Get-ComputerRestorePoint` 沿管道向下发送系统还原点对象。 `Select-Object` 使用 **Property** 参数来指定要显示的属性。 对于管道中的每个对象，中的表达式 `$date` 转换 **CreationTime** 并在 **Date** 属性中输出结果。

### 示例5：使用属性获取序列号

此示例通过使用 **SequenceNumber** 属性和数组索引来获取序列号。 输出只包含序列号。

```powershell
((Get-ComputerRestorePoint).SequenceNumber)[-1]
```

```Output
6
```

`Get-ComputerRestorePoint` 使用带有数组索引的 **SequenceNumber** 属性。 的数组索引 `-1` 获取数组中的最新序列号。

## PARAMETERS

### -LastStatus

指示 `Get-ComputerRestorePoint` 获取最近的系统还原操作的状态。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LastStatus
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestorePoint

指定系统还原点的序列号。 您可以指定单个序列号或逗号分隔的序列号数组。

如果未指定 **RestorePoint** 参数，则 `Get-ComputerRestorePoint` 返回所有本地计算机的系统还原点。

```yaml
Type: System.Int32[]
Parameter Sets: ID
Aliases:

Required: False
Position: 0
Default value: All restore points
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### 无

不能将对象向下发送到 `Get-ComputerRestorePoint` 。

## 输出

### System.management.managementobject # root\default\SystemRestore 或 String

`Get-ComputerRestorePoint` 返回一个 **SystemRestore** 对象，该对象是 WINDOWS MANAGEMENT INSTRUMENTATION (WMI) **SystemRestore** 类的实例。

当你使用 **LastStatus** 参数时，将 `Get-ComputerRestorePoint` 返回一个字符串。

## 注释

若要 `Get-ComputerRestorePoint` 在 Windows Vista 和更高版本的 windows 上运行命令，请使用 "以 **管理员身份运行** " 选项打开 PowerShell。

`Get-ComputerRestorePoint` 使用 WMI **SystemRestore** 类。

## 相关链接

[about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[about_Arrays](../Microsoft.PowerShell.Core/About/about_Arrays.md)

[Checkpoint-Computer](Checkpoint-Computer.md)

[Disable-ComputerRestore](Disable-ComputerRestore.md)

[Enable-ComputerRestore](Enable-ComputerRestore.md)

[Restart-Computer](Restart-Computer.md)

[Restore-Computer](Restore-Computer.md)

[SystemRestore](/windows/win32/sr/systemrestore)
