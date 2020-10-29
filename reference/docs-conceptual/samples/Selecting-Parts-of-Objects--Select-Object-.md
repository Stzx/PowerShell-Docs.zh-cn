---
ms.date: 12/23/2019
keywords: powershell,cmdlet
title: 选择对象部件 (Select Objec)
description: 可以使用 `Select-Object` cmdlet 创建新的自定义 PowerShell 对象（包含从管道上的对象中选择的属性）。
ms.openlocfilehash: 92635ac54ea1469739bcb228c5e9a0a8dbfc648b
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501025"
---
# <a name="selecting-parts-of-objects-select-object"></a>选择对象部件 (Select-Object)

可以使用 `Select-Object` cmdlet 创建新的自定义 PowerShell 对象（包含从用于创建它们的对象中选择的属性）。 键入下面的命令以创建仅包括 Win32_LogicalDisk WMI 类的 Name 和 FreeSpace 属性的新对象： 

```powershell
Get-CimInstance -Class Win32_LogicalDisk | Select-Object -Property Name,FreeSpace
```

```Output
Name      FreeSpace
----      ---------
C:      50664845312
```

可以使用 `Select-Object` 创建计算属性。 这样即可以以十亿字节为单位显示 FreeSpace，而非以字节为单位。 

```powershell
Get-CimInstance -Class Win32_LogicalDisk |
  Select-Object -Property Name, @{
    label='FreeSpace'
    expression={($_.FreeSpace/1GB).ToString('F2')}
  }
```

```Output
Name    FreeSpace
----    ---------
C:      47.18
```
