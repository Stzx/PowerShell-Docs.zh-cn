---
description: 允许你指示在会话中使用的命名空间。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/29/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_using?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Using
ms.openlocfilehash: 6001f2f4495490c9f2b9dbfbeac2e1f4298febd8
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "93200674"
---
# <a name="about-using"></a>关于使用

## <a name="short-description"></a>简短说明
允许你指示在会话中使用的命名空间。

## <a name="long-description"></a>详细说明

`using`语句允许您指定在会话中使用的命名空间。 添加命名空间可简化 .NET 类和成员的使用，并允许你从脚本模块和程序集导入类。

`using`语句必须位于脚本中的任何其他语句之前。

`using`语句不应与 `using:` 变量的作用域修饰符混淆。 有关详细信息，请参阅 [about_Remote_Variables](about_Remote_Variables.md)。

## <a name="syntax"></a>语法

指定要从中解析类型的 .NET 命名空间：

```
using namespace <.NET-namespace>
```

从 PowerShell 模块加载类：

```
using module <module-name>
```

若要预加载 .NET 程序集中的类型：

```
using assembly <.NET-assembly-path>
```

通过指定命名空间，可以更容易地按简称引用类型。

加载程序集时，将从该程序集将 .NET 类型预加载到脚本中的分析时。 这允许你创建新的 PowerShell 类，它们使用预先加载的程序集中的类型。

如果未创建新的 PowerShell 类，请改用 `Add-Type` cmdlet。 有关详细信息，请参阅 [添加类型](xref:Microsoft.PowerShell.Utility.Add-Type)。

## <a name="examples"></a>示例

### <a name="example-1---add-namespaces-for-typename-resolution"></a>示例 1-为 typename 解析添加命名空间

下面的脚本获取 "Hello World" 字符串的加密哈希。

请注意 `using namespace System.Text` 和如何 `using namespace System.IO` 简化对中 `[UnicodeEncoding]` `System.Text` 和和的引用 `[Stream]` `[MemoryStream]` `System.IO` 。

```powershell
using namespace System.Text
using namespace System.IO

[string]$string = "Hello World"
## Valid values are "SHA1", "SHA256", "SHA384", "SHA512", "MD5"
[string]$algorithm = "SHA256"

[byte[]]$stringbytes = [UnicodeEncoding]::Unicode.GetBytes($string)

[Stream]$memorystream = [MemoryStream]::new($stringbytes)
$hashfromstream = Get-FileHash -InputStream $memorystream `
  -Algorithm $algorithm
$hashfromstream.Hash.ToString()
```

### <a name="example-2---load-classes-from-a-script-module"></a>示例 2-从脚本模块加载类

在此示例中，有一个名为 **CardGames** 的 PowerShell 脚本模块，用于定义以下类：

- **CardGames**
- **CardGames 卡**

`Import-Module``#requires`语句仅导入模块定义的模块函数、别名和变量。 不导入类。 `using module`命令导入模块，同时加载类定义。

```powershell
using module CardGames
using namespace CardGames

[Deck]$deck = [Deck]::new()
$deck.Shuffle()
[Card[]]$hand1 = $deck.Deal(5)
[Card[]]$hand2 = $deck.Deal(5)
[Card[]]$hand3 = $deck.Deal(5)
```

### <a name="example-3---load-classes-from-an-assembly"></a>示例 3-从程序集加载类

此示例将加载一个程序集，以便可以使用该程序集的类来创建新的 PowerShell 类。 下面的脚本创建一个派生自 **DirectoryContext** 类的新 PowerShell 类。

```powershell
using assembly 'C:\Program Files\PowerShell\7\System.DirectoryServices.dll'
using namespace System.DirectoryServices.ActiveDirectory

class myDirectoryClass : System.DirectoryServices.ActiveDirectory.DirectoryContext
{

  [DirectoryContext]$domain

  myDirectoryClass([DirectoryContextType]$ctx) : base($ctx)
  {
    $this.domain = [DirectoryContext]::new([DirectoryContextType]$ctx)
  }

}

$myDomain = [myDirectoryClass]::new([DirectoryContextType]::Domain)
$myDomain
```

```Output
domain                                                    Name UserName ContextType
------                                                    ---- -------- -----------
System.DirectoryServices.ActiveDirectory.DirectoryContext                    Domain
```
