---
description: 介绍可用于获取 Windows PowerShell 中的 WMI 对象的 WMI 查询语言 (WQL)。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wql?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WQL
ms.openlocfilehash: c6fd523864d419fb400b7041e92ec8f0733724b7
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200227"
---
# <a name="about-wql"></a>关于 WQL

## <a name="short-description"></a>简短说明

介绍可用于获取 Windows PowerShell 中的 WMI 对象的 WMI 查询语言 (WQL)。

## <a name="long-description"></a>详细说明

WQL 是 Windows Management Instrumentation (WMI) 查询语言，这是用于从 WMI 获取信息的语言。

不需要使用 WQL 在 Windows PowerShell 中执行 WMI 查询。
相反，你可以使用 Get-WmiObject 或 Get-CimInstance cmdlet 的参数。 WQL 查询比标准 Get-WmiObject 命令要快一些，而且在数百个系统上运行命令时，性能得到了改善。 但是，请确保编写成功的 WQL 查询所花费的时间不会提高性能。

需要使用 WQL 的基本 WQL 语句为 Select、Where 和 From。

## <a name="when-to-use-wql"></a>何时使用 WQL

使用 WMI 时，尤其是在使用 WQL 时，请不要忘记你也在使用 Windows PowerShell。 通常，如果 WQL 查询不按预期工作，则使用标准 Windows PowerShell 命令比调试 WQL 查询更容易。

如果要从带宽受限的远程系统返回大量数据，则在有一个完全可接受的 Windows cmdlet 执行相同操作时，花费很多时间来尝试完美的复杂 WQL 查询，这种情况很少。

## <a name="using-the-select-statement"></a>使用 SELECT 语句

典型的 WMI 查询以 Select 语句开始，该语句获取 WMI 类的所有属性或特定属性。 若要选择 WMI 类的所有属性，请使用星号 (\*) 。 From 关键字指定 WMI 类。

Select 语句具有以下格式：

```
Select <property> from <WMI-class>
```

例如，下面的 Select 语句从 Win32_Bios WMI 类的实例中选择 ( * ) 的所有属性。

```
Select * from Win32_Bios
```

若要选择 WMI 类的特定属性，请将属性名称置于 Select 和 From 关键字之间。

下面的查询仅选择 Win32_Bios WMI 类中的 BIOS 的名称。 该命令将查询保存在 $queryName 变量中。

```
Select Name from Win32_Bios
```

若要选择多个属性，请使用逗号分隔属性名称。
以下 WMI 查询选择 Win32_Bios WMI 类的名称和版本。 该命令将查询保存在 $queryNameVersion 变量中。

```
Select name, version from Win32_Bios
```

## <a name="using-the-wql-query"></a>使用 WQL 查询

有三种方法可在 Windows PowerShell 命令中使用 WQL 查询。

- 使用 Get-WmiObject cmdlet
- 使用 Get-CimInstance cmdlet
- 使用 [wmisearcher] 类型加速器。

## <a name="using-the-get-wmiobject-cmdlet"></a>使用 GET-WMIOBJECT CMDLET

使用 WQL 查询的最基本方法是将其括在引号中 (作为字符串) ，然后使用查询字符串作为 Get-WmiObject cmdlet 的 Query 参数的值，如下面的示例中所示。

```powershell
Get-WmiObject -Query "Select * from Win32_Bios"
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

你还可以将 WQL 语句保存在一个变量中，然后将该变量用作 Query 参数的值，如下面的命令中所示。

```powershell
$query = "Select * from Win32_Bios"
Get-WmiObject -Query $query
```

可以在任何 WQL 语句中使用这两种格式。 以下命令使用 $queryName 变量中的查询来仅获取系统 BIOS 的名称和版本属性。

```powershell
$queryNameVersion = "Select Name, Version from Win32_Bios"
Get-WmiObject -Query $queryNameVersion
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
Version          : LENOVO - 1360
```

请记住，可以使用 Get-WmiObject cmdlet 的参数获得相同的结果。 例如，以下命令还获取 Win32_Bios WMI 类的实例的 Name 和 Version 属性的值。

```powershell
Get-WmiObject -Class Win32_Bios -Property Name, Version
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
Version          : LENOVO - 1360
```

## <a name="using-the-get-ciminstance-cmdlet"></a>使用 CIMINSTANCE CMDLET

从 Windows PowerShell 3.0 开始，可以使用 Get-CimInstance cmdlet 来运行 WQL 查询。

Get-CimInstance 获取与 CIM 兼容的类（包括 WMI 类）的实例。 Windows PowerShell 3.0 引入的 CIM cmdlet 执行与 WMI cmdlet 相同的任务。 CIM cmdlet 符合 WS-Management (WSMan) 标准和通用信息模型 (CIM) 标准，这使 cmdlet 能够使用相同的技术来管理运行其他操作系统的 Windows 计算机和计算机。

以下命令使用 Get-CimInstance cmdlet 来运行 WQL 查询。

任何可与 Get-WmiObject 一起使用的 WQL 查询也可用于 CimInstance。

```powershell
Get-CimInstance -Query "Select * from Win32_Bios"
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

Get-CimInstance 返回 CimInstance 对象，而不是 Get-WmiObject 返回的 System.management.managementobject，但对象非常类似。

```
(Get-CimInstance -Query "Select * from Win32_Bios").GetType().FullName
Microsoft.Management.Infrastructure.CimInstance
(Get-WmiObject -Query "Select * from Win32_Bios").GetType().FullName
System.Management.ManagementObject
```

## <a name="using-the-wmisearcher-type-accelerator"></a>使用 [wmisearcher] 类型加速器

[Wmisearcher] 类型加速器从 WQL 语句字符串创建 ManagementObjectSearcher 对象。 ManagementObjectSearcher 对象具有多个属性和方法，但最基本的方法是 Get 方法，该方法调用指定的 WMI 查询并返回生成的对象。

通过使用 [wmisearcher]，可轻松访问 ManagementObjectSearcher .NET Framework 类。 这使你能够查询 WMI 并配置执行查询的方式。

使用 [wmisearcher] 类型加速器：

1. 将 WQL 字符串强制转换为 ManagementObjectSearcher 对象。
2. 调用 ManagementObjectSearcher 对象的 Get 方法。

例如，以下命令强制转换 "全选" 查询，将结果保存在 $bios 变量中，然后调用 $bios 变量中 ManagementObjectSearcher 对象的 Get 方法。

```powershell
$bios = [wmisearcher]"Select * from Win32_Bios"
$bios.Get()
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

注意：默认情况下，仅显示所选的对象属性。 这些属性是在 Types.ps1xml 文件中定义的。

可以使用 [wmisearcher] 类型加速器来转换查询或变量。 在下面的示例中，将使用 [wmisearcher] 类型加速器来转换变量。 结果是相同的。

```powershell
[wmisearcher]$bios = "Select * from Win32_Bios"
$bios.Get()
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

使用 [wmisearcher] 类型加速器时，它会将查询字符串更改为 ManagementObjectSearcher 对象，如以下命令中所示。

```
$a = "Select * from Win32_Bios"
$a.GetType().FullName
System.String

$a = [wmisearcher]"Select * from Win32_Bios"
$a.GetType().FullName
System.Management.ManagementObjectSearcher
```

此命令格式适用于任何查询。 下面的命令获取 Win32_Bios WMI 类的 Name 属性的值。

```powershell
$biosname = [wmisearcher]"Select Name from Win32_Bios"
$biosname.Get()
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
```

可以在单个命令中执行此操作，尽管命令更难解释。

采用这种格式时，请使用 [wmisearcher] 类型加速器将 WQL 查询字符串转换为 ManagementObjectSearcher，然后对对象调用 Get 方法，只需要在单个命令中调用 Get 方法。 圆括号 ( # A1，用来在调用方法之前，将强制转换字符串 direct Windows PowerShell 强制转换为字符串。

```powershell
([wmisearcher]"Select name from Win32_Bios").Get()
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
```

## <a name="using-the-basic-wql-where-statement"></a>使用基本 WQL WHERE 语句

Where 语句为 Select 语句返回的数据建立条件。

Where 语句具有以下格式：

```
where <property> <operator> <value>
```

例如：

```
where Name = 'Notepad.exe'
```

Where 语句用于 Select 语句，如下面的示例中所示。

```
Select * from Win32_Process where Name = 'Notepad.exe'
```

使用 Where 语句时，属性名称和值必须准确。

例如，以下命令将获取本地计算机上的记事本进程。

```powershell
Get-WmiObject -Query "Select * from Win32_Process where name='Notepad.exe'"
```

但是，下面的命令将失败，因为进程名称包含 ".exe" 文件扩展名。

```powershell
Get-WmiObject -Query "Select * from Win32_Process where name='Notepad'"
```

## <a name="where-statement-comparison-operators"></a>WHERE 语句比较运算符

以下运算符在 WQL Where 语句中有效。

```
Operator    Description
-----------------------
=           Equal
!=          Not equal
<>          Not equal
<           Less than
>           Greater than
<=          Less than or equal
>=          Greater than or equal
LIKE        Wildcard match
IS          Evaluates null
ISNOT       Evaluates not null
ISA         Evaluates a member of a WMI class
```

还有其他运算符，但这些运算符用于进行比较。

例如，下面的查询从 Win32_Process 类中的进程选择进程优先级大于或等于11的进程的名称和优先级属性。 Get-WmiObject cmdlet 将运行查询。

```powershell
$highPriority = "Select Name, Priority from Win32_Process " +
  "where Priority >= 11"
Get-WmiObject -Query $highPriority
```

## <a name="using-the-wql-operators-in-the-filter-parameter"></a>在 FILTER 参数中使用 WQL 运算符

WQL 运算符还可用于 Get-WmiObject 或 Get-CimInstance cmdlet 的 Filter 参数的值，以及这些 cmdlet 的查询参数值中。

例如，以下命令将获取 ProcessID 值大于1004的最后五个进程的 Name 和 ProcessID 属性。 该命令使用筛选器参数来指定 ProcessID 条件。

```powershell
Get-WmiObject -Class Win32_Process `
-Property Name, ProcessID -Filter "ProcessID >= 1004" |
Sort ProcessID | Select Name, ProcessID -Last 5
```

```output
Name                                 ProcessID
----                                 ---------
SROSVC.exe                                4220
WINWORD.EXE                               4664
TscHelp.exe                               4744
SnagIt32.exe                              4748
WmiPrvSE.exe                              5056
```

## <a name="using-the-like-operator"></a>使用 LIKE 运算符

Like 运算符使你可以使用通配符来筛选 WQL 查询的结果。

```
Like Operator  Description
--------------------------------------------------
[]             Character in a range [a-f] or a set
               of characters [abcdef]. The items in
               a set do not need to be consecutive or
               listed in alphabetical order.

^              Character not in a range [^a-f] or
               not in a set [^abcdef]. The items in
               a set do not need to be consecutive or
               listed in alphabetical order.

%              A string of zero or more characters

_              One character.
(underscore)   NOTE: To use a literal underscore
               in a query string, enclose it in
               square brackets [_].
```

当使用 Like 运算符时，如果不使用任何通配符或范围运算符，则该运算符的行为类似于相等运算符 (=) 并仅在它们与模式完全匹配时才返回对象。

可以将范围操作与百分号通配符组合在一起，以创建简单但功能强大的筛选器。

### <a name="like-operator-examples"></a>LIKE 运算符示例

#### <a name="example-1-range"></a>示例1： [ \<range> ]

以下命令将启动 "记事本"，然后搜索 Win32_Process 类的实例，该实例的名称以字母 "H" 和 "N" （ (不区分大小写的) ）开头。

查询应返回从 Hotpad.exe 到 Notepad.exe 的任何进程。

```powershell
Notepad   # Starts Notepad
$query = "Select * from win32_Process where Name LIKE '[H-N]otepad.exe'"
Get-WmiObject -Query $query | Select Name, ProcessID
```

```output
Name                                ProcessID
----                                ---------
notepad.exe                              1740
```

#### <a name="example-2-range-and-"></a>示例2： [ \<range> ] 和%

以下命令选择名称以字母开头且不区分大小写的所有进程 (不区分大小写的) 后跟任何组合中的零个或多个字母。

Get-WmiObject cmdlet 运行查询，Select-Object cmdlet 获取名称和 ProcessID 属性，Sort-Object cmdlet 按名称的字母顺序对结果进行排序。

```powershell
$query = "Select * from win32_Process where name LIKE '[A-P]%'"
Get-WmiObject -Query $query |
Select-Object -Property Name, ProcessID |
Sort-Object -Property Name
```

#### <a name="example-3-not-in-range-"></a>示例3：不在范围 (^) 

以下命令将获取名称不以以下任何字母开头的进程： A、S、W、P、R、C、U、N

并遵循零个或多个字母。

```powershell
$query = "Select * from win32_Process where name LIKE '[^ASWPRCUN]%'"
Get-WmiObject -Query $query |
Select-Object -Property Name, ProcessID |
Sort-Object -Property Name
```

#### <a name="example-4-any-characters----or-none-"></a>示例4：任何字符--或 none (% ) 

以下命令将获取名称以 "calc" 开头的进程。
WQL 中的% 符号等效于 \* 正则表达式中的星号 () 符号。

```powershell
$query = "Select * from win32_Process where Name LIKE 'calc%'"
Get-WmiObject -Query $query | Select-Object -Property Name, ProcessID
```

```output
Name                               ProcessID
----                               ---------
calc.exe                                4424
```

#### <a name="example-5-one-character-_"></a>示例5：一个字符 (_) 

以下命令将获取名称具有以下模式的进程： "c_lc.exe"，其中的下划线字符表示任意一个字符。 此模式将 calc.exe 中的任何名称与 czlc.exe 或 c9lc.exe 匹配，但不匹配 "c" 和 "l" 之间用多个字符分隔的名称。

```powershell
$query = "Select * from Win32_Process where Name LIKE 'c_lc.exe'"
Get-WmiObject -Query $query | Select-Object -Property Name, ProcessID
```

```output
Name                                 ProcessID
----                                 ---------
calc.exe                                  4424
```

#### <a name="example-6-exact-match"></a>示例6：完全匹配

以下命令将获取名为 WLIDSVC.exe 的进程。 即使查询使用 Like 关键字，它也需要完全匹配，因为该值不包含任何通配符。

```powershell
$query = "Select * from win32_Process where name LIKE 'WLIDSVC.exe'"
Get-WmiObject -Query $query | Select-Object -Property Name, ProcessID
```powershell

```output
Name                                 ProcessID
----                                 ---------
WLIDSVC.exe                                84
```

## <a name="using-the-or-operator"></a>使用 OR 运算符

若要指定多个独立条件，请使用或关键字。 或关键字显示在 Where 子句中。 它对两个 (或多个) 条件执行包含或运算，并返回满足任何条件的项。

Or 运算符具有以下格式：

```
Where <property> <operator> <value> or <property> <operator> <value> ...
```

例如，下面的命令获取 Win32_Process WMI 类的所有实例，但仅当进程名称为 winword.exe 或 excel.exe 时才返回它们。

```powershell
$q = "Select * from Win32_Process where Name='winword.exe'" +
  " or Name='excel.exe'"
Get-WmiObject -Query $q
```

或语句可用于两个以上的条件。 在下面的查询中，或语句获取 Winword.exe、Excel.exe 或 Powershell.exe。

```powershell
$q = "Select * from Win32_Process where Name='winword.exe'" +
  " or Name='excel.exe' or Name='powershell.exe'"
```

## <a name="using-the-and-operator"></a>使用 AND 运算符

若要指定多个相关条件，请使用和关键字。 和关键字显示在 Where 子句中。 它将返回满足所有条件的项。

和运算符具有以下格式：

```
Where <property> <operator> <value> and <property> <operator> <value> ...
```

例如，以下命令将获取名称为 "Winword.exe"，进程 ID 为6512的进程。

请注意，这些命令使用 Get-CimInstance cmdlet。

```powershell
$q = "Select * from Win32_Process where Name = 'winword.exe' " +
  "and ProcessID =6512"
Get-CimInstance -Query $q
```

```output
ProcessId   Name             HandleCount      WorkingSetSize   VirtualSize
---------   ----             -----------      --------------   -----------
# 6512      WINWORD.EXE      768              117170176        633028608
```

所有运算符，包括 Like 运算符都适用于或和和运算符。 而且，你可以在单个查询中将 Or 和 And 运算符与指示 Windows PowerShell 首先处理的子句的括号组合在一起。

此命令使用 Windows PowerShell 继续符 (") 将命令分为两行。

```powershell
$q = "Select * from Win32_Process `
where (Name = 'winword.exe' or Name = 'excel.exe') and HandleCount > 700"
Get-CimInstance -Query $q
```

```output
ProcessId    Name             HandleCount      WorkingSetSize   VirtualSize
---------    ----             -----------      --------------   -----------
     6512    WINWORD.EXE      797              117268480        634425344
     9610    EXCEL.EXE        727               38858752        323227648
```

## <a name="searching-for-null-values"></a>搜索 NULL 值

在 WMI 中搜索 null 值非常困难，因为这可能导致不可预知的结果。 Null 不为零，且不等同于或为空字符串。 一些 WMI 类属性已初始化，而其他属性不会进行初始化，因此对于所有属性，搜索 null 可能不起作用。

若要搜索 null 值，请使用值为 "null" 的 Is 运算符。

例如，以下命令将获取 IntallDate 属性的值为 null 的进程。 命令返回多个进程。

```powershell
$q = "Select * from Win32_Process where InstallDate is null"
Get-WmiObject -Query $q
```

相反，下面的命令获取 Description 属性的 null 值的用户帐户。 此命令不会返回任何用户帐户，即使大多数用户帐户没有 "说明" 属性的任何值。

```powershell
$q = "Select * from Win32_UserAccount where Description is null"
Get-WmiObject -Query $q
```

若要查找 "Description" 属性没有值的用户帐户，请使用相等运算符获取空字符串。 若要表示空字符串，请使用两个连续的单引号。

```powershell
$q = "Select * from Win32_UserAccount where Description = '' "
```

## <a name="using-true-or-false"></a>使用 TRUE 或 FALSE

若要在 WMI 对象的属性中获取布尔值，请使用 True 和 False。
不区分大小写。

以下 WQL 查询仅返回已加入域的计算机中的本地用户帐户。

```powershell
$q = "Select * from Win32_UserAccount where LocalAccount = True"
Get-CimInstance -Query $q
```

若要查找域帐户，请使用值 False，如下面的示例中所示。

```powershell
$q = "Select * from Win32_UserAccount where LocalAccount = False"
Get-CimInstance -Query $q
```

## <a name="using-the-escape-character"></a>使用转义符

WQL 使用反斜杠 (\) 作为其转义字符。 这不同于 Windows PowerShell，后者使用反撇号字符 (") 。

引号以及用引号引起来的字符通常需要转义，以便不会被误解。

若要查找名称中包含单引号的用户，请使用反斜杠来转义单引号，如以下命令中所示。

```powershell
$q = "Select * from Win32_UserAccount where Name = 'Tim O\'Brian'"
Get-CimInstance -Query $q
```

```output
Name             Caption          AccountType      SID              Domain
----             -------          -----------      ---              ------
Tim O'Brian      FABRIKAM\TimO    512              S-1-5-21-1457... FABRIKAM
```

在某些情况下，还需要转义反斜杠。 例如，以下命令将生成无效的查询错误，因为标题值中有反斜杠。

```powershell
$q = "Select * from Win32_UserAccount where Caption = 'Fabrikam\TimO'"
Get-CimInstance -Query $q
```

```output
Get-CimInstance : Invalid query
At line:1 char:1
+ Get-CimInstance -Query $q
+ ~~~~~~~~~~~
  + CategoryInfo          : InvalidArgument: (:) [Get-CimInstance], CimExcep
  + FullyQualifiedErrorId : HRESULT 0x80041017,Microsoft.Management.Infrastr
```

若要对反斜杠进行转义，请使用第二个反斜杠字符，如下面的命令中所示。

```powershell
$q = "Select * from Win32_UserAccount where Caption = 'Fabrikam\\TimO'"
Get-CimInstance -Query $q
```

## <a name="see-also"></a>另请参阅

[about_Special_Characters](about_Special_Characters.md)

[about_Quoting_Rules](about_Quoting_Rules.md)

[about_WMI](about_WMI.md)

[about_WMI_Cmdlets](about_WMI_Cmdlets.md)
