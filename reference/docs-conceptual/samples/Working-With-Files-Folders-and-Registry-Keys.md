---
ms.date: 07/28/2020
keywords: powershell,cmdlet
title: 使用文件、文件夹和注册表项
description: 本文介绍如何使用 PowerShell 处理注册表项操作任务。
ms.openlocfilehash: 6f653c1fb409a238aa05658e89261a12e96f6fe1
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "92499971"
---
# <a name="working-with-files-folders-and-registry-keys"></a>使用文件、文件夹和注册表项

Windows PowerShell 使用名词 **Item** 来引用在 Windows PowerShell 驱动器上找到的项。
处理 Windows PowerShell FileSystem 提供程序时， **Item** 可能是文件、文件夹或 Windows PowerShell 驱动器。 列出并使用这些项是大部分管理设置中的关键基本任务，因此我们想要详细讨论这些任务。

## <a name="enumerating-files-folders-and-registry-keys-get-childitem"></a>枚举文件、文件夹和注册表项 (Get-ChildItem)

由于从特定位置获取项的集合是很常见的任务，因此 `Get-ChildItem` cmdlet 专门用于返回在容器（例如某个文件夹）中找到的所有项。

如果你希望返回直接包含在文件夹 C:\\Windows 内的所有文件和文件夹，请键入：

```
PS> Get-ChildItem -Path C:\Windows
    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\Windows

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---        2006-05-16   8:10 AM          0 0.log
-a---        2005-11-29   3:16 PM         97 acc1.txt
-a---        2005-10-23  11:21 PM       3848 actsetup.log
...
```

列出操作看起来和你在 Cmd.exe 中输入 `dir` 命令或在 UNIX 命令 shell 中输入 `ls` 命令时类似。

可以通过使用 `Get-ChildItem` cmdlet 的参数来执行非常复杂的列出操作。 接下来，我们将介绍一些方案。 可以通过键入以下内容来查看 `Get-ChildItem` cmdlet 的语法：

```powershell
Get-Command -Name Get-ChildItem -Syntax
```

可以混合并匹配这些参数以获取高度自定义的输出。

### <a name="listing-all-contained-items--recurse"></a>列出所有包含的项 (-Recurse)

若要查看 Windows 文件夹内的项和子文件夹内包含的任何项，请使用 `Get-ChildItem` 的 Recurse 参数。 此列出操作显示 Windows 文件夹内的所有内容及其子文件夹中的项。 例如：

```
PS> Get-ChildItem -Path C:\WINDOWS -Recurse

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\WINDOWS
    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\WINDOWS\AppPatch
Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---        2004-08-04   8:00 AM    1852416 AcGenral.dll
...
```

### <a name="filtering-items-by-name--name"></a>按名称筛选项 (-Name)

若要仅显示项的名称，请使用 `Get-Childitem` 的 Name 参数：

```
PS> Get-ChildItem -Path C:\WINDOWS -Name
addins
AppPatch
assembly
...
```

### <a name="forcibly-listing-hidden-items--force"></a>强制列出隐藏的项 (-Force)

如果项在文件资源管理器或 Cmd.exe 中通常处于隐藏状态，则它们不会在 `Get-ChildItem` 命令的输出中显示。 若要显示隐藏的项，请使用 `Get-ChildItem` 的 Force 参数。
例如：

```powershell
Get-ChildItem -Path C:\Windows -Force
```

此参数的名称为 Force，因为你可以强制替代 `Get-ChildItem` 命令的常态行为。 Force 是一个广泛使用的参数，此参数可强制执行 cmdlet 通常不会执行的操作，尽管它不会执行任何危害系统安全的操作。

### <a name="matching-item-names-with-wildcards"></a>使用通配符匹配项名称

`Get-ChildItem` 命令接受要列出的项路径中的通配符。

由于通配符匹配由 Windows PowerShell 引擎处理，因此接受通配符的所有 cmdlet 使用相同的表示法，并具有相同的匹配行为。 Windows PowerShell 通配符表示法包括：

- 星号 (`*`) 匹配零个或多个出现的任何字符。

- 问号 (`?`) 完全匹配一个字符。

- 左括号 (`[`) 字符和右括号 (`]`) 字符括起一组要匹配的字符。

下面是一些通配符规则工作原理的示例。

若要在 Windows 目录中查找带有后缀 `.log` 并且基名称中正好有五个字符的所有文件，请输入以下命令：

```
PS> Get-ChildItem -Path C:\Windows\?????.log

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\Windows
Mode                LastWriteTime     Length Name
----                -------------     ------ ----
...
-a---        2006-05-11   6:31 PM     204276 ocgen.log
-a---        2006-05-11   6:31 PM      22365 ocmsn.log
...
-a---        2005-11-11   4:55 AM         64 setup.log
-a---        2005-12-15   2:24 PM      17719 VxSDM.log
...
```

若要在 Windows 目录中查找以字母 `x` 开头的所有文件，请键入：

```powershell
Get-ChildItem -Path C:\Windows\x*
```

若要查找名称以“x”或“z”开头的所有文件，请键入：

```powershell
Get-ChildItem -Path C:\Windows\[xz]*
```

有关通配符的详细信息，请参阅 [about_Wildcards](/powershell/module/microsoft.powershell.core/about/about_wildcards)。

### <a name="excluding-items--exclude"></a>排除项 (-Exclude)

可以通过使用 `Get-ChildItem` 的 Exclude 参数来排除特定项。 这可让你在单个声明中执行复杂的筛选。

例如，假设你要尝试在 System32 文件夹中查找 Windows 时间服务 DLL，但只记得 DLL 名称以“W”开头并且其中有“32”。

表达式（如 `w*32*.dll`）将查找满足条件的所有 DLL，但建议进一步筛选文件并忽略任何 win32 文件。 可以通过使用模式为 `win*` 的 Exclude 参数来忽略这些文件：

```
PS> Get-ChildItem -Path C:\WINDOWS\System32\w*32*.dll -Exclude win*

    Directory: C:\WINDOWS\System32

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           3/18/2019  9:43 PM         495616 w32time.dll
-a---           3/18/2019  9:44 PM          35328 w32topl.dll
-a---           1/24/2020  5:44 PM         401920 Wldap32.dll
-a---          10/10/2019  5:40 PM         442704 ws2_32.dll
-a---           3/18/2019  9:44 PM          66048 wsnmp32.dll
-a---           3/18/2019  9:44 PM          18944 wsock32.dll
-a---           3/18/2019  9:44 PM          64792 wtsapi32.dll
```

### <a name="mixing-get-childitem-parameters"></a>混合使用 Get-ChildItem 参数

可以在同一命令中使用 `Get-ChildItem` cmdlet 的多个参数。 在混合使用参数之前，请确保你了解通配符匹配。 例如，以下命令不会返回任何结果：

```powershell
Get-ChildItem -Path C:\Windows\*.dll -Recurse -Exclude [a-y]*.dll
```

即使 Windows 文件夹中有两个以字母“z”开头的 DLL，也没有结果。

由于我们已将通配符指定为路径的一部分，因此未返回任何结果。 即使命令是递归的，`Get-ChildItem` cmdlet 也会将项限制为 Windows 文件夹中名称以 `.dll` 结尾的项。

若要指定名称匹配特殊模式的文件的递归搜索，请使用 **Include** 参数。

```
PS> Get-ChildItem -Path C:\Windows -Include *.dll -Recurse -Exclude [a-y]*.dll

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\Windows\System32\Setup

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---        2004-08-04   8:00 AM       8261 zoneoc.dll

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\Windows\System32

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---        2004-08-04   8:00 AM     337920 zipfldr.dll
```
