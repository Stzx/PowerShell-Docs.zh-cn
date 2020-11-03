---
description: 提供有关 Windows Management Instrumentation (WMI) 和 Windows PowerShell 的背景信息。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wmi_cmdlets?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WMI_Cmdlets
ms.openlocfilehash: c2099c005cedf64e9621d66d6757419320c9b43e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200228"
---
# <a name="about-wmi-cmdlets"></a>关于 WMI Cmdlet

## <a name="short-description"></a>简短说明

提供有关 Windows Management Instrumentation (WMI) 和 Windows PowerShell 的背景信息。

## <a name="long-description"></a>详细说明

本主题提供有关 WMI 技术、适用于 Windows PowerShell 的 WMI cmdlet、基于 WMI 的远程处理、WMI 加速器和 WMI 疑难解答的信息。 本主题还提供了有关 WMI 的详细信息的链接。

### <a name="about-wmi"></a>关于 WMI

Windows Management Instrumentation (WMI) 是 Microsoft 对基于 Web 的企业管理 (WBEM) 的实现，WBEM 是一项业界倡议，用于为访问企业环境中的管理信息开发一项标准技术。 WMI 使用通用信息模型 (CIM) 行业标准来表示系统、应用程序、网络、设备和其他托管组件。 CIM 由分布式管理任务组 (DMTF) 进行开发和维护。 您可以使用 WMI 来管理本地和远程计算机。 例如，可以使用 WMI 来执行以下操作：

- 启动远程计算机上的进程。
- 远程重新启动计算机。
- 获取本地或远程计算机上安装的应用程序的列表。
- 查询本地或远程计算机上的 Windows 事件日志。

### <a name="the-wmi-cmdlets-for-windows-powershell"></a>适用于 WINDOWS POWERSHELL 的 WMI CMDLET

Windows PowerShell 在默认情况下，通过 Windows PowerShell 中提供的一组 cmdlet 来实现 WMI 功能。 你可以使用这些 cmdlet 来完成管理本地和远程计算机所需的端到端任务。

包含以下 WMI cmdlet。

|Cmdlet           |说明                                   |
|-----------------|----------------------------------------------|
|Get-WmiObject    |获取 WMI 类或信息的实例  |
|                 |关于可用的类。                  |
|Invoke-WmiMethod |调用 WMI 方法。                            |
|Register-WmiEvent|订阅 WMI 事件。                    |
|Remove-WmiObject |删除 WMI 类和实例。            |
|Set-WmiInstance  |创建或修改 WMI 类的实例。 |

### <a name="sample-commands"></a>示例命令
以下命令显示本地计算机的 BIOS 信息。

```powershell
C:\PS> get-wmiobject win32_bios | format-list *
```

以下命令显示有关三台远程计算机的 WinRM 服务的信息。

```powershell
$wql = "select * from win32_service where name='WinRM'"
get-wmiobject -query $wql -computername server01, server01, server03
```

下面更复杂的命令退出程序的所有实例。

```powershell
C:\PS> notepad.exe
C:\PS> $wql = "select * from win32_process where name='notepad.exe'"
C:\PS> $np = get-wmiobject -query $wql
C:\PS> $np | remove-wmiobject
```

### <a name="wmi-based-remoting"></a>基于 WMI 的远程处理

尽管通过 WMI 管理本地系统的功能非常有用，但它还是使 WMI 成为一项功能强大的管理工具的远程处理功能。 WMI 使用 Microsoft 的分布式组件对象模型 (DCOM) 连接和管理系统。 你可能需要将一些系统配置为允许 DCOM 连接。
防火墙设置和锁定 DCOM 权限会阻止 WMI 远程管理系统的能力。

### <a name="wmi-type-accelerators"></a>WMI 类型加速器

Windows PowerShell 包括 WMI 类型加速器。 这些 WMI 类型加速器 (快捷方式) 允许比非类型加速器方法更好地访问 WMI 对象。

WMI 支持以下类型加速器：

[WMISEARCHER]-搜索 WMI 对象的快捷方式。

[WMICLASS]-访问类的静态属性和方法的快捷方式。

[WMI]-获取类的单个实例的快捷方式。

[WMISEARCHER] 是 ManagementObjectSearcher 的类型加速器。 它可以使用字符串构造函数创建一个搜索程序，然后在上执行 GET ( # A1。

例如：

```powershell
PS> $s = [WmiSearcher]'Select * from Win32_Process where Handlecount > 1000'
PS> $s.Get() |sort handlecount |ft handlecount,__path,name -auto

count  __PATH                                              name
-----  ------                                              ----
1105   \\SERVER01\root\cimv2:Win32_Process.Handle="3724"   PowerShell...
1132   \\SERVER01\root\cimv2:Win32_Process.Handle="1388"   winlogon.exe
1495   \\SERVER01\root\cimv2:Win32_Process.Handle="2852"   iexplore.exe
1699   \\SERVER01\root\cimv2:Win32_Process.Handle="1204"   OUTLOOK.EXE
1719   \\SERVER01\root\cimv2:Win32_Process.Handle="1912"   iexplore.exe
2579   \\SERVER01\root\cimv2:Win32_Process.Handle="1768"   svchost.exe
```

[WMICLASS] 是 ManagementClass 的类型加速器。 这包含一个字符串构造函数，该构造函数采用 WMI 类的本地或绝对 WMI 路径，并返回绑定到该类的对象。

例如：

```powershell
PS> $c = [WMICLASS]"root\cimv2:WIn32_Process"
PS> $c |fl *
Name             : Win32_Process
__GENUS          : 1
__CLASS          : Win32_Process
__SUPERCLASS     : CIM_Process
__DYNASTY        : CIM_ManagedSystemElement
__RELPATH        : Win32_Process
__PROPERTY_COUNT : 45
__DERIVATION     : {CIM_Process, CIM_LogicalElement,
                   CIM_ManagedSystemElement}
__SERVER         : SERVER01
__NAMESPACE      : ROOT\cimv2
__PATH           : \\SERVER01\ROOT\cimv2:Win32_Process
```

[WMI] 是 System.management.managementobject 的类型加速器。 这包含一个字符串构造函数，该构造函数采用到 WMI 实例的本地或绝对 WMI 路径，并返回绑定到该实例的对象。

例如：

```powershell
PS> $p = [WMI]'\\SERVER01\root\cimv2:Win32_Process.Handle="1204"'
PS> $p.Name
OUTLOOK.EXE
```

### <a name="wmi-troubleshooting"></a>WMI 故障排除

以下问题是尝试连接到远程计算机时可能出现的最常见问题。

问题1：远程计算机未联机。

如果计算机处于脱机状态，你将无法使用 WMI 连接到该计算机。
可能会收到以下错误消息：

```
Remote server machine does not exist or is unavailable
```

如果收到此错误消息，请验证计算机是否处于联机状态。 尝试 ping 远程计算机。

问题2：你没有远程计算机上的本地管理员权限。

若要远程使用 WMI，你必须拥有远程计算机上的本地管理员权限。 否则，将拒绝对该计算机的访问。

验证命名空间安全性：

1. 单击 "开始"，右键单击我的电脑，然后单击 "管理"。
2. 在 "计算机管理" 中，展开 "服务和应用程序"，右键单击 "WMI 控制"，然后单击 "属性"。
3. 在 "WMI 控制属性" 对话框中，单击 "安全" 选项卡。

问题3：防火墙阻止了对远程计算机的访问。

WMI 使用 DCOM (分布式 COM) 和 RPC (远程过程调用) 协议来遍历网络。 默认情况下，很多防火墙会阻止 DCOM 和 RPC 通信。 如果防火墙阻止了这些协议，则连接将失败。 例如，Microsoft Windows XP Service Pack 2 中的 Windows 防火墙配置为自动阻止所有未经请求的网络通信，包括 DCOM 和 WMI。 在默认配置中，Windows 防火墙拒绝传入的 WMI 请求，并收到以下错误消息：

```
Remote server machine does not exist or is unavailable
```

## <a name="see-also"></a>另请参阅

[关于 WMI](/windows/win32/wmisdk/about-wmi)

[WMI 故障排除](/windows/win32/wmisdk/wmi-troubleshooting)

[Get-WmiObject](xref:Microsoft.PowerShell.Management.Get-WmiObject)

[Invoke-WmiMethod](xref:Microsoft.PowerShell.Management.Invoke-WmiMethod)

[Register-WmiEvent](xref:Microsoft.PowerShell.Management.Register-WmiEvent)

[Remove-WmiObject](xref:Microsoft.PowerShell.Management.Remove-WmiObject)

[Set-WmiInstance](xref:Microsoft.PowerShell.Management.Set-WmiInstance)
