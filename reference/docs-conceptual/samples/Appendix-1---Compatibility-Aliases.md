---
ms.date: 08/03/2020
keywords: powershell,cmdlet
title: 附录 1 - 兼容性别名
ms.openlocfilehash: e5bd170fea6b6109d2ef4fd58863d6cc8a0e3ae1
ms.sourcegitcommit: d3f78120bdc9096c72aa0dfdbdd91efaf254c738
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/04/2020
ms.locfileid: "87758493"
---
# <a name="appendix-1---compatibility-aliases"></a>附录 1 - 兼容性别名

PowerShell 具有多个别名，使 UNIX  和 cmd.exe  用户可以使用熟悉的命令。
下表显示了这些命令及其相关的 PowerShell cmdlet 和 PowerShell 别名：

|            cmd.exe命令            | UNIX 命令 | PowerShell Cmdlet | PowerShell 别名 |
| ------------------------------------- | ------------ | ----------------- | ---------------- |
| **cd**、**chdir**                     | **cd**       | `Set-Location`    | `sl`             |
| **cls**                               | **clear**    | `Clear-Host`      | `cls`            |
| **copy**                              | **cp**       | `Copy-Item`       | `cpi`            |
| **del**、**erase**、**rd**、**rmdir** | **rm**       | `Remove-Item`     | `ri`             |
| **dir**                               | **ls**       | `Get-ChildItem`   | `gci`            |
| echo                              | echo     | `Write-Output`    | `write`          |
| **md**                                | **mkdir**    | `New-Item`        | `ni`             |
| **move**                              | **mv**       | `Move-Item`       | `mi`             |
| **popd**                              | **popd**     | `Pop-Location`    | `popd`           |
| **pushd**                             | **pushd**    | `Push-Location`   | `pushd`          |
| **ren**                               | **mv**       | `Rename-Item`     | `rni`            |
| type                              | **cat**      | `Get-Content`     | `gc`             |

若要查找 PowerShell 别名，请使用 [Get-Alias](xref:Microsoft.PowerShell.Utility.Get-Alias) cmdlet。 若要显示 cmdlet 的别名，请使用 Definition**** 参数并指定 cmdlet 名称。
或者，要查找别名的 cmdlet 名称，请使用 name**** 参数并指定别名。

```powershell
Get-Alias -Definition Get-ChildItem
```

```Output
CommandType     Name
-----------     ----
Alias           dir -> Get-ChildItem
Alias           gci -> Get-ChildItem
Alias           ls -> Get-ChildItem
```

```powershell
Get-Alias -Name gci
```

```Output
CommandType     Name
-----------     ----
Alias           gci -> Get-ChildItem
```
