---
description: Windows PowerShell 会创建一个名为 "Windows PowerShell" 的 Windows 事件日志来记录 Windows PowerShell 事件。 可以事件查看器中查看此日志，也可以使用获取事件的 cmdlet （如 cmdlet）来查看此日志 `Get-EventLog` 。 默认情况下，Windows PowerShell 引擎和提供程序事件记录在事件日志中，但你可以使用事件日志首选项变量来自定义事件日志。 例如，你可以添加有关 Windows PowerShell 命令的事件。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 11/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_eventlogs?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Eventlogs
ms.openlocfilehash: eb92333c6a6e220e287dcbec1441d2d05aa9275b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200307"
---
# <a name="about-eventlogs"></a>关于事件日志

## <a name="short-description"></a>简短说明

Windows PowerShell 会创建一个名为 "Windows PowerShell" 的 Windows 事件日志来记录 Windows PowerShell 事件。 可以事件查看器中查看此日志，也可以使用获取事件的 cmdlet （如 cmdlet）来查看此日志 `Get-EventLog` 。 默认情况下，Windows PowerShell 引擎和提供程序事件记录在事件日志中，但你可以使用事件日志首选项变量来自定义事件日志。 例如，你可以添加有关 Windows PowerShell 命令的事件。

## <a name="long-description"></a>详细说明

Windows PowerShell 事件日志记录 Windows PowerShell 操作的详细信息，例如启动和停止程序引擎，以及启动和停止 Windows PowerShell 提供程序。 你还可以记录有关 Windows PowerShell 命令的详细信息。

Windows PowerShell 事件日志位于 "应用程序和服务日志" 组中。 Windows PowerShell 日志是典型的事件日志，不使用 Windows 事件技术。 若要查看日志，请使用为经典事件日志设计的 cmdlet，例如 `Get-EventLog` 。

## <a name="viewing-the-windows-powershell-event-log"></a>查看 Windows PowerShell 事件日志

可以事件查看器中或使用和 cmdlet 来查看 Windows PowerShell 事件日志 `Get-EventLog` `Get-WmiObject` 。 若要查看 Windows PowerShell 日志的内容，请键入：

```powershell
Get-EventLog -LogName "Windows PowerShell"
```

若要检查事件及其属性，请使用 cmdlet `Sort-Object` 、cmdlet 以及 `Group-Object` 包含 `Format` cmdlet)  (谓词的 cmdlet `Format` 。

例如，若要查看日志中按事件 ID 分组的事件，请键入：

```powershell
Get-EventLog "Windows PowerShell" | Format-Table -GroupBy EventID
```

或者键入：

```powershell
Get-EventLog "Windows PowerShell" |
  Sort-Object EventID |
  Group-Object EventID
```

若要查看所有经典事件日志，请键入：

```powershell
Get-EventLog -List
```

你还可以使用 `Get-WmiObject` cmdlet 来使用与事件相关的 Windows Management Instrumentation (WMI) 类来检查事件日志。 例如，若要查看事件日志文件的所有属性，请键入：

```powershell
Get-WmiObject Win32_NTEventlogFile |
  where LogFileName -EQ "Windows PowerShell" |
  Format-List -Property *
```

若要查找与 Win32 事件相关的 WMI 类，请键入：

```powershell
Get-WmiObject -List | where Name -Like "win32*event*"
```

有关详细信息，请键入 "Get-help Get-help" 和 "Get-help Get-wmiobject"。

## <a name="selecting-events-for-the-windows-powershell-event-log"></a>为 Windows PowerShell 事件日志选择事件

您可以使用事件日志首选项变量来确定哪些事件记录在 Windows PowerShell 事件日志中。

有六个事件日志首选项变量;这三个日志记录组件中的每个组件都有两个变量：引擎 (Windows PowerShell 程序) 、提供程序和命令。 LifeCycleEvent 变量记录正常的启动和停止事件。 运行状况变量记录错误事件。

下表列出了事件日志首选项变量。

|变量                  |说明                                    |
|--------------------------|-----------------------------------------------|
|$LogEngineLifeCycleEvent  |记录 PowerShell 的启动和停止          |
|$LogEngineHealthEvent     |记录 PowerShell 程序错误                 |
|$LogProviderLifeCycleEvent|记录 PowerShell 提供程序的启动和停止|
|$LogProviderHealthEvent   |记录 PowerShell 提供程序错误                |
|$LogCommandLifeCycleEvent |记录命令的启动和完成   |
|$LogCommandHealthEvent    |记录命令错误                            |

 (有关 Windows PowerShell 提供程序的信息，请参阅 [about_Providers](about_Providers.md)。 ) 

默认情况下，只启用以下事件类型：

* $LogEngineLifeCycleEvent
* $LogEngineHealthEvent
* $LogProviderLifeCycleEvent
* $LogProviderHealthEvent

若要启用某个事件类型，请将该事件类型的首选项变量设置为 $true。 例如，若要启用命令生命周期事件，请键入：

```powershell
$LogCommandLifeCycleEvent
```

或者键入：

```powershell
$LogCommandLifeCycleEvent = $true
```

若要禁用事件类型，请将该事件类型的首选项变量设置为 $false。 例如，若要禁用命令生命周期事件，请键入：

```powershell
$LogProviderLifeCycleEvent = $false
```

您可以禁用任何事件，但表明 Windows PowerShell 引擎和核心提供程序已启动的事件除外。 这些事件是在运行 Windows PowerShell 配置文件之前、主机程序准备接受命令之前生成的。

变量设置仅适用于当前的 Windows PowerShell 会话。
若要将其应用到所有 Windows PowerShell 会话，请将其添加到 Windows PowerShell 配置文件。

## <a name="logging-module-events"></a>记录模块事件

从 Windows PowerShell 3.0 开始，可以通过将模块和管理单元的 LogPipelineExecutionDetails 属性设置为 TRUE，在 Windows PowerShell 模块和管理单元中记录 cmdlet 和函数的执行事件。 在 Windows PowerShell 2.0 中，此功能仅适用于管理单元。

当 LogPipelineExecutionDetails 属性值为 TRUE 时 (`$true`) ，Windows powershell 会将会话中的 cmdlet 和函数执行事件写入事件查看器的 Windows powershell 日志中。 此设置仅在当前会话中有效。

若要对某个模块中的 cmdlet 和函数的执行事件进行日志记录，请使用以下命令序列。

```powershell
Import-Module <ModuleName>
$m = Get-Module <ModuleName>
$m.LogPipelineExecutionDetails = $true
```

若要在管理单元中启用 cmdlet 的执行事件日志记录，请使用以下命令序列。

```powershell
$m = Get-PSSnapin <SnapInName> [-Registered]
$m.LogPipelineExecutionDetails = $True
```

若要禁用日志记录，请使用相同的命令序列将属性值设置为 FALSE (`$false`) 。

你还可以使用 "打开模块日志记录" 组策略设置来启用和禁用模块和管理单元日志记录。 策略值包括模块和管理单元名称的列表。 支持通配符。

为模块设置 "打开模块日志记录" 时，模块的 LogPipelineExecutionDetails 属性的值在所有会话中都为 TRUE，并且无法更改。

"打开模块日志记录" 组策略设置位于以下组策略路径中：

```
Computer Configuration\
  Administrative Templates\
    Windows Components\
     Windows PowerShell

User Configuration\
  Administrative Templates\
    Windows Components\
      Windows PowerShell
```

用户配置策略优先于计算机配置策略，并且两个策略优先于模块和管理单元的 LogPipelineExecutionDetails 属性的值。

有关此组策略设置的详细信息，请参阅 [about_Group_Policy_Settings](about_Group_Policy_Settings.md)。

## <a name="security-and-auditing"></a>安全和审核

Windows PowerShell 事件日志旨在指示活动，并提供操作详细信息以进行故障排除。

但是，与大多数基于 Windows 的应用程序事件日志类似，Windows PowerShell 事件日志并未设计为安全。 它不应用于审核安全或记录机密信息或专有信息。

事件日志旨在供用户阅读和理解。 用户可以读取和写入日志。 恶意用户可能会读取本地或远程计算机上的事件日志，记录虚假数据，然后阻止日志记录其活动。

## <a name="notes"></a>注释

模块作者的作者可以向其模块中添加日志记录功能。 有关详细信息，请参阅 [编写 Windows PowerShell 模块](/powershell/scripting/developer/module/writing-a-windows-powershell-module)。

## <a name="see-also"></a>另请参阅

[Get-EventLog](xref:Microsoft.PowerShell.Management.Get-EventLog)

[Get-WmiObject](xref:Microsoft.PowerShell.Management.Get-WmiObject)

[about_Group_Policy_Settings](about_Group_Policy_Settings.md)

[about_Preference_Variables](about_Preference_Variables.md)
