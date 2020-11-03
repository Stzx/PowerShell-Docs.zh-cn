---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/add-pssnapin?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-PSSnapin
ms.openlocfilehash: 5adba912d91369250ee9891ee2bb2ca0f8cba796
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197461"
---
# Add-PSSnapin

## 摘要
将一个或多个 Windows PowerShell 管理单元添加到当前会话中。

## SYNTAX

```
Add-PSSnapin [-Name] <String[]> [-PassThru] [<CommonParameters>]
```

## DESCRIPTION

`Add-PSSnapin`Cmdlet 可将已注册的 Windows PowerShell 管理单元添加到当前会话中。 添加了管理单元之后，就可以使用当前会话中的管理单元支持的 cmdlet 和提供程序。

若要将管理单元添加到所有未来的 Windows PowerShell 会话中，请将 `Add-PSSnapin` 命令添加到 Windows powershell 配置文件。 有关详细信息，请参阅 [about_Profiles](about/about_Profiles.md)。

从 Windows PowerShell 3.0 开始，将 Windows PowerShell 中包含的核心命令打包在模块中。 例外情况是 **Microsoft.PowerShell.Core** ，它是一个管理单元 (PSSnapin)。
默认情况下，仅将 **Microsoft.PowerShell.Core** 管理单元添加到会话中。 首次使用时自动导入模块，而且可以使用 Import-Module cmdlet 导入它们。

## 示例

### 示例1：添加管理单元

```powershell
PS C:\> Add-PSSnapIn -Name Microsoft.Exchange, Microsoft.Windows.AD
```

此命令会将 Microsoft Exchange 和 Active Directory 管理单元添加到当前会话中。

### 示例2：添加所有已注册的管理单元

```powershell
PS C:\> Get-PSSnapin -Registered | Add-PSSnapin -Passthru
```

此命令会将所有已注册 Windows PowerShell 管理单元添加到会话中。 它使用带有 **已注册** 参数的 Get-PSSnapin cmdlet 来获取表示每个已注册管理单元的对象。管道运算符 (|) 将结果传递给 `Add-PSSnapin` ，这会将其添加到会话中。 **PassThru** 参数将返回表示每个已添加管理单元的对象。

### 示例3：注册管理单元并添加它

第一个命令将获取已添加到当前会话中的管理单元，其中包括随 Windows PowerShell 一起安装的管理单元。 此示例中，不返回 ManagementFeatures。 这指示尚未将其添加到会话中。

第二个命令获取已在系统上注册的管理单元，包括那些已添加到会话的管理单元。 它不包括随 Windows PowerShell 一起安装的管理单元。 在这种情况下，该命令不返回任何管理单元。这表示未在系统上注册 ManagementFeatures 管理单元。

第三个命令为 .NET Framework 中的 Installutil.exe 工具的路径创建一个别名 installutil.exe。

第四个命令使用 Installutil.exe 工具注册管理单元。 命令指定管理单元的 ManagementCmdlets.dll 路径、文件名或模块名称。

第五个命令与第二个命令相同。 这一次，你可以使用它来验证 ManagementCmdlets 管理单元是否已注册。

第六个命令使用 `Add-PSSnapin` cmdlet 将 ManagementFeatures 管理单元添加到会话中。 该命令指定了管理单元的名称 ManagementFeatures，而不是文件名。

若要验证管理单元是否已添加到会话中，第七个命令使用 Get-Command cmdlet 的 **Module** 参数。 它将显示已由管理单元或模块添加到会话中的项。

你还可以使用 cmdlet 返回的对象的 **add-pssnapin** 属性 `Get-Command` 来查找生成 cmdlet 的管理单元或模块。 第八个命令使用点表示法查找 Set-Alias cmdlet 的 Add-pssnapin 属性的值。

```powershell
PS C:\> Get-PSSnapin
PS C:\> Get-PSSnapin -Registered
PS C:\> Set-Alias installutil $env:windir\Microsoft.NET\Framework\v2.0.50727\installutil.exe
PS C:\> installutil C:\Dev\Management\ManagementCmdlets.dll
PS C:\> Get-PSSnapin -Registered
PS C:\> add-pssnapin ManagementFeatures
PS C:\> Get-Command -Module ManagementFeatures
PS C:\> (Get-Command Set-Alias).pssnapin
```

此示例将演示了在你的系统上注册管理单元，然后再将其添加到会话中的过程。 它使用 ManagementFeatures，它是在名为 ManagementCmdlets.dll 的文件中实现的虚拟管理单元。

## PARAMETERS

### -Name

指定管理单元的名称。 这是名称，而不是 AssemblyName 或 ModuleName。 允许使用通配符。

若要在系统上查找已注册的管理单元的名称，请键入 `Get-PSSnapin -Registered` 。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -PassThru

指示此 cmdlet 返回表示每个已添加管理单元的对象。 默认情况下，此 cmdlet 将不产生任何输出。

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
不能通过管道将对象传递给此 cmdlet。

## 输出

### 无或 System.Management.Automation.PSSnapInInfo

如果指定 **PassThru** 参数，则此 cmdlet 将返回表示该管理单元的 PSSnapInInfo 对象。 否则，此 cmdlet 将不生成任何输出。

## 注释

* 从 Windows PowerShell 3.0 开始，将与 Windows PowerShell 一起安装的核心命令打包在模块中。 在 Windows PowerShell 2.0 和在更高版本的 Windows PowerShell 中创建旧样式会话的主机程序中，核心命令打包在 (PSSnapins) 的管理单元中。 **Microsoft.PowerShell.Core** 是例外情况，它始终是一个管理单元。 此外，远程会话（如 New-PSSession cmdlet 启动的会话）是包括核心管理单元的旧样式会话。

  有关 **CreateDefault2** 方法的详细信息，请参阅 MSDN library 中的 [CreateDefault2 方法](https://msdn.microsoft.com/library/system.management.automation.runspaces.initialsessionstate.createdefault2) 。

* 有关管理单元的详细信息，请参阅 [about_PSSnapins](About/about_PSSnapins.md) 和 [如何创建 Windows PowerShell 管理单元](/powershell/scripting/developer/cmdlet/how-to-create-a-windows-powershell-snap-in)。
* `Add-PSSnapin` 仅将管理单元添加到当前会话。 若要将管理单元添加到所有 Windows PowerShell 会话中，请将该管理单元添加到你的 Windows PowerShell 配置文件中。 有关详细信息，请参阅 about_Profiles。
* 你可以添加已使用 Microsoft .NET Framework 安装实用工具注册的任何管理单元。 有关详细信息，请参阅 [如何注册 cmdlet、提供程序和主机应用程序](/previous-versions//ms714644(v=vs.85))。
* 若要获取在你的计算机上注册的管理单元的列表，请键入 `Get-PSSnapin -Registered` 。
* 在添加管理单元之前， `Add-PSSnapin` 检查管理单元的版本，以验证它是否与 Windows PowerShell 的当前版本兼容。 如果管理单元未通过版本检查，则 Windows PowerShell 将报告错误。

## 相关链接

[Get-PSSnapin](Get-PSSnapin.md)

[Remove-PSSnapin](Remove-PSSnapin.md)
