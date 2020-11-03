---
description: " (WMI) Windows Management Instrumentation 使用 (通用信息模型来表示新式企业的系统、应用程序、网络、设备和其他可管理组件。"
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wmi?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WMI
ms.openlocfilehash: d24b952ee167e51815d6d9920e95bbc9a6bb9608
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200232"
---
# <a name="about-wmi"></a>关于 WMI

## <a name="short-description"></a>简短说明

 (WMI) Windows Management Instrumentation 使用 (通用信息模型来表示新式企业的系统、应用程序、网络、设备和其他可管理组件。

## <a name="long-description"></a>详细说明

Windows Management Instrumentation (WMI) 是 Microsoft 实现的 Web-Based 企业管理 (WBEM) ，这是行业标准。

经典 WMI 使用 DCOM 与网络设备通信，以管理远程系统。 Windows PowerShell 3.0 引入了一个 CIM 提供程序模型，该模型使用 WinRM 删除对 DCOM 的依赖项。 此 CIM 提供程序模型还使用新的 WMI 提供程序 Api，使开发人员能够在本机代码 (C) 中编写 Windows PowerShell cmdlet \+ \+ 。

不要将 WMI 提供程序与 Windows PowerShell 提供程序混淆。 许多 Windows 功能都有一个关联的 WMI 提供程序，该提供程序公开其管理功能。 若要获取 WMI 提供程序，请运行 WMI 查询以获取 __Provider WMI 类的实例，例如以下查询。

```powershell
Get-WmiObject -Class __Provider
```

## <a name="three-components-of-wmi"></a>WMI 的三个组件

以下三个 WMI 组件与 Windows PowerShell 交互：命名空间、提供程序和类。

WMI 命名空间将 WMI 提供程序和 WMI 类组织到相关组件组中。 通过这种方式，它们类似于 .NET Framework 命名空间。
命名空间不是物理位置，但更像是逻辑数据库。
所有 WMI 命名空间都是 __Namespace 系统类的实例。 由于 Microsoft Windows 2000) ，默认 WMI 命名空间为根 \/ CIMV2 (。 若要使用 Windows PowerShell 来获取当前会话中的 WMI 命名空间，请使用具有以下格式的命令。

```powershell
Get-WmiObject -Class __Namespace
```

若要获取其他命名空间中的 WMI 命名空间，请使用 Namespace 参数更改搜索的位置。 以下命令查找位于 Root/Cimv2/Applications 命名空间中的 WMI 命名空间。

```powershell
Get-WmiObject -Class __Namespace -Namespace root/CIMv2/applications
```

WMI 命名空间是分层的。 因此，若要获取特定系统上所有命名空间的列表，需要执行从根命名空间开始的递归查询。

WMI 提供程序公开有关 Windows 可管理对象的信息。 提供程序从组件中检索数据，并通过 WMI 将该数据传递到管理应用程序，如 Windows PowerShell。 大多数 WMI 提供程序是动态提供程序，这意味着当通过管理应用程序请求数据时，它们会动态地获取数据。

## <a name="finding-wmi-classes"></a>查找 WMI 类

在 Windows 8 的默认安装中，根 Cimv2 中的 WMI 类超过1100个 \/ 。 使用此类 WMI 类，质询将会确定要用于执行特定任务的相应 WMI 类。 Windows PowerShell 3.0 提供了两种方法来查找与特定主题相关的 WMI 类。

例如，若要查找 \\ 与磁盘相关的根 CIMV2 wmi 命名空间中的 WMI 类，可以使用如下所示的查询。

```powershell
Get-WmiObject -List *disk*
```

若要查找与内存相关的 WMI 类，可以使用如下所示的查询。

```powershell
Get-WmiObject -List *memory*
```

CIM cmdlet 还提供了发现 WMI 类的功能。 为此，请使用 Get-CIMClass cmdlet。 此处显示的命令列出了与视频相关的 WMI 类。

```powershell
Get-CimClass *video*
```

选项卡扩展适用于更改 WMI 命名空间，因此使用选项卡扩展使子 WMI 命名空间易于发现。 在下面的示例中，Get-CimClass cmdlet 列出了与电源设置相关的 WMI 类。
若要找到该命名空间，请键入 `root/CIMV2/` 命名空间，然后按若干次 tab 键，直到出现 power 命名空间。 命令如下：

```powershell
Get-CimClass *power* -Namespace root/cimv2/power
```
