---
description: 介绍 Windows PowerShell 管理单元，并演示如何使用和管理这些管理单元。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pssnapins?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSSnapins
ms.openlocfilehash: cc22f8de0b9d8a55dcfa12f3b47f3852d891e67b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200096"
---
# <a name="about-pssnapins"></a>关于 PSSnapins

## <a name="short-description"></a>简短说明

介绍 Windows PowerShell 管理单元，并演示如何使用和管理这些管理单元。

## <a name="long-description"></a>详细说明

Windows PowerShell 管理单元是包含 Windows PowerShell 提供程序和或 cmdlet 的 Microsoft .NET Framework 程序集 \/ 。 Windows PowerShell 包括一组基本管理单元，但你可以通过添加包含你所创建的提供程序和 cmdlet 的管理单元来扩展 Windows PowerShell 的功能和价值。

添加管理单元时，它包含的 cmdlet 和提供程序将立即可用于当前会话，但更改仅影响当前会话。

若要将管理单元添加到将来的所有会话中，请将其保存在你的 Windows PowerShell 配置文件中。 你还可以使用 Export-Console cmdlet 将管理单元名称保存到控制台文件中，然后在将来的会话中使用它。 你甚至可以保存多个控制台文件，每个文件都有一组不同的管理单元。

注意： Windows powershell 管理单元 (PSSnapins) 可在 Windows PowerShell 3.0 和 Windows PowerShell 2.0 中使用。 它们可能会在后续版本中更改或不可用。 若要打包 Windows PowerShell cmdlet 和提供程序，请使用模块。 若要了解如何创建模块并将管理单元转换为模块，请参阅 [编写 Windows PowerShell 模块](/powershell/scripting/developer/module/writing-a-windows-powershell-module)。

### <a name="finding-snap-ins"></a>查找管理单元

若要获取计算机上的 Windows PowerShell 管理单元的列表，请键入：

```powershell
Get-PSSnapin
```

若要获取每个 Windows PowerShell 提供程序的管理单元，请键入：

```powershell
Get-PSProvider | Format-List name, pssnapin
```

若要获取 Windows PowerShell 管理单元中的 cmdlet 列表，请键入：

```powershell
Get-Command -Module <snap-in_name>
```

### <a name="installing-a-snap-in"></a>安装管理单元

内置的管理单元在系统中注册，并在启动 Windows PowerShell 时添加到默认会话中。 但是，你必须注册你创建的管理单元或从其他设备获取的管理单元，然后将该管理单元添加到你的会话。

### <a name="registering-a-snap-in"></a>注册管理单元

Windows PowerShell 管理单元是用编译到 .dll 文件的 .NET Framework 语言编写的程序。 若要在管理单元中使用提供程序和 cmdlet，必须先注册管理单元 (将其添加到注册表) 。

大多数管理单元都包含一个安装程序， (为您注册 .dll 文件的 .exe 或 .msi 文件) 。 但是，如果您接收到作为 .dll 文件的管理单元，则可以将其注册到您的系统上。 有关详细信息，请参阅 MSDN library 中的 " [如何注册 cmdlet、提供程序和主机应用程序](https://go.microsoft.com/fwlink/?LinkID=143619) "。

若要获取系统上所有已注册的管理单元，或验证是否注册了管理单元，请键入：

```powershell
Get-PSSnapin -registered
```

### <a name="adding-the-snap-in-to-the-current-session"></a>将管理单元添加到当前会话

若要将已注册的管理单元添加到当前会话中，请使用 Add-PsSnapin cmdlet。 例如，若要将 Microsoft SQL Server 管理单元添加到会话中，请键入：

```powershell
Add-PSSnapin sql
```

完成该命令后，该管理单元中的提供程序和 cmdlet 将在该会话中可用。 但是，它们仅在当前会话中可用，除非您保存它们。

### <a name="saving-the-snap-ins"></a>保存管理单元

若要在将来的 Windows PowerShell 会话中使用管理单元，请将 Add-PsSnapin 命令添加到 Windows PowerShell 配置文件中。 或者将管理单元的名称导出到控制台文件。

如果将 Add-PSSnapin 命令添加到配置文件，则在将来的所有 Windows PowerShell 会话中都可以使用此命令。 如果导出会话中的管理单元的名称，则只能在需要管理单元时使用导出文件。

若要将 Add-PsSnapin 命令添加到 Windows PowerShell 配置文件中，请打开配置文件，粘贴或键入命令，然后保存该配置文件。 有关详细信息，请参阅 about_Profiles。

若要从控制台文件 () 中的会话保存管理单元，请使用 Export-Console cmdlet。 例如，要将当前会话配置中的管理单元保存到当前目录中的 Newconsole.psc1 文件，请键入：

```powershell
Export-Console NewConsole
```

有关详细信息，请参阅导出-控制台。

### <a name="opening-windows-powershell-with-a-console-file"></a>使用控制台文件打开 WINDOWS POWERSHELL

若要使用包含管理单元的控制台文件，请从 Cmd.exe 或其他 Windows PowerShell 会话的命令提示符下启动 Windows PowerShell ( # A0) 。 使用 PsConsoleFile 参数指定包含管理单元的控制台文件。 例如，以下命令将启动带有 .psc1 控制台文件的 Windows PowerShell Newconsole.psc1：

```powershell
PowerShell.exe -psconsolefile NewConsole.psc1
```

管理单元中的提供程序和 cmdlet 现在可在会话中使用。

### <a name="removing-a-snap-in"></a>删除管理单元

若要从当前会话中删除 Windows PowerShell 管理单元，请使用 Remove-PsSnapin cmdlet。 例如，若要从当前会话中删除 SQL Server 管理单元，请键入：

```powershell
Remove-PSSnapin sql
```

此 cmdlet 将从会话中删除管理单元。 仍加载管理单元，但它支持的提供程序和 cmdlet 不再可用。

### <a name="built-in-commands"></a>内置命令

在 Windows PowerShell 2.0 和 windows powershell 3.0 及更高版本的旧式主机程序中，随 Windows PowerShell 一起安装的内置命令会打包在自动添加到每个 Windows PowerShell 会话的管理单元中。

从 Windows PowerShell 3.0 开始，在更新样式的主机程序中（使用 InitialSessionState. CreateDefault2 方法启动会话的程序），内置命令打包在模块中。 异常是 Microsoft. Core，它始终显示为管理单元。 默认情况下，每个会话中都包含 "核心" 管理单元。 内置模块将在首次使用时自动加载。

注意：远程会话（包括使用 New-PSSession cmdlet 启动的会话）是旧样式的会话，其中内置命令打包在管理单元中。

以下管理单元 (或模块) 随 Windows PowerShell 一起安装。

- Microsoft. Core-包含用于管理 Windows PowerShell 的基本功能的提供程序和 cmdlet。 它包括文件系统、注册表、别名、环境、函数、变量提供程序和基本 cmdlet，如 Get-help、Get 命令和获取历史记录。

- Microsoft 包含 Windows PowerShell 主机使用的 cmdlet，例如 Start-Transcript 和停止脚本。

- -包含用于管理基于 Windows 的功能的 cmdlet，例如 Get-Service 和 Get-ChildItem。

- Get-authenticodesignature-包含用于管理 Windows PowerShell 安全的证书提供程序和 cmdlet，例如获取 Acl、和 Convertto-html-SecureString。

- Microsoft PowerShell-包含用于操作对象和数据的 cmdlet，如获取成员、写入主机和格式列表。

- Enable-wsmancredssp-包含用于管理 Windows 远程管理服务的 WSMan 提供程序和 cmdlet，如 Connect-WSMan 和。

## <a name="logging-snap-in-events"></a>记录管理单元事件

从 Windows PowerShell 3.0 开始，可以通过将模块和管理单元的 LogPipelineExecutionDetails 属性设置为 TRUE，在 Windows PowerShell 模块和管理单元中记录 cmdlet 的执行事件。 有关详细信息，请参阅 [about_EventLogs](about_EventLogs.md)。

## <a name="see-also"></a>另请参阅

[Add-pssnapin](xref:Microsoft.PowerShell.Core.Add-PSSnapin)

[Add-pssnapin](xref:Microsoft.PowerShell.Core.Get-PSSnapin)

[Add-pssnapin](xref:Microsoft.PowerShell.Core.Remove-PSSnapin)

[Export-Console](xref:Microsoft.PowerShell.Core.Export-Console)

[Get-Command](xref:Microsoft.PowerShell.Core.Get-Command)

[about_Profiles](about_Profiles.md)

[about_Modules](about_Modules.md)

## <a name="keywords"></a>字

about_Snapins、about_Snap_ins、about_Snap
