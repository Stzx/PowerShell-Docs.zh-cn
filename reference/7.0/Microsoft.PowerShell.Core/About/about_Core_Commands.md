---
description: 列出旨在与 PowerShell 提供程序一起使用的 cmdlet。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_core_commands?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Core_Commands
ms.openlocfilehash: 5c784518ae30108813d32497f654198e7d10b379
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199613"
---
# <a name="about-core-commands"></a>关于核心命令

## <a name="short-description"></a>简短说明
列出旨在与 PowerShell 提供程序一起使用的 cmdlet。

## <a name="long-description"></a>详细说明

PowerShell 包括一组 cmdlet，这些 cmdlet 专门用于管理 PowerShell 提供程序公开的数据存储中的项。
您可以通过相同的方式使用这些 cmdlet 来管理提供商提供的所有不同类型的数据。 有关提供程序的详细信息，请键入 "get-help about_providers"。

例如，你可以使用 Get-ChildItem cmdlet 来列出文件系统目录中的文件、注册表项下的注册表项或你编写或下载的提供程序公开的项。

下面是专为与提供程序一起使用的 PowerShell cmdlet 列表：

Get-childitem cmdlet

- Get-ChildItem

内容 cmdlet

- Add-Content
- Clear-Content
- Get-Content
- Set-Content

项 cmdlet

- Clear-Item
- Copy-Item
- Get-Item
- Invoke-Item
- Move-Item
- New-Item
- Remove-Item
- Rename-Item
- Set-Item

Set-itemproperty cmdlet

- Clear-ItemProperty
- Copy-ItemProperty
- Get-ItemProperty
- Move-ItemProperty
- New-ItemProperty
- Remove-ItemProperty
- Rename-ItemProperty
- Set-ItemProperty

位置 cmdlet

- Get-Location
- Pop-Location
- Push-Location
- Set-Location

路径 cmdlet

- Join-Path
- Convert-Path
- Split-Path
- Resolve-Path
- Test-Path

New-psdrive cmdlet

- Get-PSDrive
- New-PSDrive
- Remove-PSDrive

PSProvider cmdlet

- Get-PSProvider

有关 cmdlet 的详细信息，请键入 `get-help <cmdlet-name>` 。

## <a name="see-also"></a>另请参阅

[about_Providers](about_Providers.md)
