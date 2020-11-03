---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 09/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/foreach-object?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ForEach-Object
ms.openlocfilehash: 327add884077083d37e1f58ab8f78b784a870362
ms.sourcegitcommit: e0f9fe6335be1e0f94bedaa0e8baec2acaeaa076
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "93199400"
---
# ForEach-Object

## 摘要
针对输入对象集合中的每个项执行操作。

## 语法

### ScriptBlockSet（默认值）

```
ForEach-Object [-InputObject <PSObject>] [-Begin <ScriptBlock>] [-Process] <ScriptBlock[]>
 [-End <ScriptBlock>] [-RemainingScripts <ScriptBlock[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### PropertyAndMethodSet

```
ForEach-Object [-InputObject <PSObject>] [-MemberName] <String> [-ArgumentList <Object[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## 说明

`ForEach-Object`Cmdlet 对输入对象集合中的每个项执行操作。 可以通过管道将输入对象传递给 cmdlet，或使用 **InputObject** 参数指定。

从 Windows PowerShell 3.0 开始，可以使用两种不同的方法来构造 `ForEach-Object` 命令。

- **脚本块** 。 你可以使用某个脚本块来指定操作。 在脚本块中，使用 `$_` 变量来表示当前对象。 脚本块是 **Process** 参数的值。 脚本块可以包含任何 PowerShell 脚本。

  例如，以下命令将获取计算机上每个进程的 **ProcessName** 属性值。

  `Get-Process | ForEach-Object {$_.ProcessName}`

  `ForEach-Object` 支持 `begin` 、 `process` 和块， `end` 如 [about_functions](about/about_functions.md#piping-objects-to-functions)中所述。

  > [!NOTE]
  > 脚本块在调用方的作用域中运行。 因此，这些块有权访问该范围内的变量，并且可以创建在 cmdlet 完成后在该范围内持久保留的新变量。

- **操作语句** 。 你还可以编写操作语句，它更像自然语言。 你可以使用该操作语句来指定属性值或调用方法。 Windows PowerShell 3.0 中引入了操作语句。

  例如，以下命令还将获取计算机上每个进程的 **ProcessName** 属性值。

  `Get-Process | ForEach-Object ProcessName`

## 示例

### 示例1：分割数组中的整数

此示例使用一个包含三个整数的数组，并将每个整数除以1024。

```powershell
30000, 56798, 12432 | ForEach-Object -Process {$_/1024}
```

```Output
29.296875
55.466796875
12.140625
```

### 示例2：获取目录中所有文件的长度

此示例处理 PowerShell 安装目录中的文件和目录 `$PSHOME` 。

```powershell
Get-ChildItem $PSHOME |
  ForEach-Object -Process {if (!$_.PSIsContainer) {$_.Name; $_.Length / 1024; " " }}
```

如果该对象不是一个目录，则脚本块将获取该文件的名称，将其 **Length** 属性的值除以1024，并添加一个空格 ( "" ) 以便将它与下一项隔开。 Cmdlet 使用 **PSISContainer** 属性来确定对象是否为目录。

### 示例3：对最新系统事件进行操作

此示例将系统事件日志中的最新1000事件写入文本文件。 当前时间在处理事件之前和之后显示。

```powershell
$Events = Get-EventLog -LogName System -Newest 1000
$events | ForEach-Object -Begin {Get-Date} -Process {Out-File -FilePath Events.txt -Append -InputObject $_.Message} -End {Get-Date}
```

`Get-EventLog` 获取系统事件日志中的最新事件1000，并将其存储在 `$Events` 变量中。 `$Events` 然后，将管道传递给 `ForEach-Object` cmdlet。 **Begin** 参数将显示当前日期和时间。 接下来， **Process** 参数使用 `Out-File` cmdlet 创建一个名为 events.txt 的文本文件，并将每个事件的消息属性存储在该文件中。 最后，在完成所有处理之后，使用 **End** 参数显示日期和时间。

### 示例4：更改注册表项的值

此示例将 "密钥" 下的所有子项中的 **RemotePath** 注册表项的值更改 `HKCU:\Network` 为大写文本。

```powershell
Get-ItemProperty -Path HKCU:\Network\* |
  ForEach-Object {Set-ItemProperty -Path $_.PSPath -Name RemotePath -Value $_.RemotePath.ToUpper();}
```

可以使用此格式更改注册表条目值的形式或内容。

**Network** 项中的每个子项都表示将在登录时重新连接的映射网络驱动器。
**RemotePath** 项包含连接的驱动器的 UNC 路径。 例如，如果将 E：驱动器映射到，则 `\\Server\Share` 会有一个 **e** 子项， `HKCU:\Network` 并且 **e** 子项中的 **RemotePath** 注册表项的值为 `\\Server\Share` 。

该命令使用 `Get-ItemProperty` cmdlet 来获取 **网络** 密钥的所有子项，并使用 `Set-ItemProperty` cmdlet 来更改每个密钥中的 **RemotePath** 注册表项的值。
在 `Set-ItemProperty` 命令中，路径是注册表项的 **PSPath** 属性的值。 这是表示注册表项的 Microsoft .NET Framework 对象的属性，而不是注册表项。 该命令使用 **RemotePath** 值的 **ToUpper ( # B1** 方法，这是 REG_SZ)  (字符串。

由于 `Set-ItemProperty` 正在更改每个键的属性，因此 `ForEach-Object` 需要使用 cmdlet 来访问属性。

### 示例5：使用 $Null 自动变量

此示例演示如何通过管道将 `$Null` 自动变量传递给 `ForEach-Object` cmdlet。

```powershell
1, 2, $null, 4 | ForEach-Object {"Hello"}
```

```Output
Hello
Hello
Hello
Hello
```

因为 PowerShell 将 null 视为显式占位符，所以该 `ForEach-Object` cmdlet 会生成一个值 `$Null` ，就像对管道传递给它的其他对象一样。

### 示例6：获取属性值

此示例通过使用 cmdlet 的 **成员名称** 参数获取所有已安装的 PowerShell 模块的 **Path** 属性的值 `ForEach-Object` 。

```powershell
Get-Module -ListAvailable | ForEach-Object -MemberName Path
Get-Module -ListAvailable | Foreach Path
```

第二个命令等效于第一个命令。 它使用 `Foreach` cmdlet 的别名， `ForEach-Object` 并忽略 **成员** 名称参数的名称，此参数是可选的。

`ForEach-Object`Cmdlet 对于获取属性值非常有用，因为它在不更改类型的情况下获取值，而不 **Format** 是更改 `Select-Object` 属性值类型。

### 示例7：将模块名称拆分为组件名称

此示例显示了将两个以句点分隔的模块名称拆分为其组件名称的三种方法。

```powershell
"Microsoft.PowerShell.Core", "Microsoft.PowerShell.Host" | ForEach-Object {$_.Split(".")}
"Microsoft.PowerShell.Core", "Microsoft.PowerShell.Host" | ForEach-Object -MemberName Split -ArgumentList "."
"Microsoft.PowerShell.Core", "Microsoft.PowerShell.Host" | Foreach Split "."
```

```Output
Microsoft
PowerShell
Core
Microsoft
PowerShell
Host
```

这些命令调用字符串的 **Split** 方法。 这三个命令使用不同的语法，但它们是等效且可互换的。

第一个命令使用传统语法，包括脚本块和当前的对象运算符 `$_` 。 它使用句点语法来指定该方法，并使用括号将分隔符参数括起来。

第二个命令使用 **MemberName** 参数来指定 **Split** 方法，并使用 **ArgumentName** 参数将句点 (".") 标识为拆分分隔符。

第三个命令使用 cmdlet 的 **Foreach** 别名， `ForEach-Object` 并省略 **成员** 名称和 **ArgumentList** 参数的名称，这些参数是可选的。

### 示例8：将 ForEach-Object 用于两个脚本块

在此示例中，我们传递了两个脚本块按位置。 所有脚本块都绑定到 **Process** 参数。 但是，它们被视为已传递到 **Begin** 和 **Process** 参数。

```powershell
1..2 | ForEach-Object { 'begin' } { 'process' }
```

```Output
begin
process
process
```

### 示例9：使用包含两个以上脚本块的 ForEach-Object

在此示例中，我们传递了两个脚本块按位置。 所有脚本块都绑定到 **Process** 参数。 但是，它们被视为已传递到 **Begin** 、 **Process** 和 **End** 参数。

```powershell
1..2 | ForEach-Object { 'begin' } { 'process A' }  { 'process B' }  { 'end' }
```

```Output
begin
process A
process B
process A
process B
end
```

> [!NOTE]
> 第一个脚本块始终映射到 `begin` 块，最后一个块映射到 `end` 块，中间的块全部映射到 `process` 块。

### 示例10：运行每个管道项的多个脚本块

如前面的示例所示，使用 **Process** 参数传递的多个脚本块将映射到 **Begin** 和 **End** 参数。 若要避免此映射，必须为 **Begin** 和 **End** 参数提供显式值。

```powershell
1..2 | ForEach-Object -Begin $null -Process { 'one' }, { 'two' }, { 'three' } -End $null
```

```Output
one
two
three
one
two
three
```

## parameters

### -ArgumentList

指定方法调用的参数数组。 有关 **ArgumentList** 行为的详细信息，请参阅 [about_Splatting](about/about_Splatting.md#splatting-with-arrays)。

已在 Windows PowerShell 3.0 中引入了此参数。

```yaml
Type: System.Object[]
Parameter Sets: PropertyAndMethodSet
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Begin

指定在此 cmdlet 处理任何输入对象之前运行的脚本块。 此脚本块仅对整个管道运行一次。 有关块的详细信息 `begin` ，请参阅 [about_Functions](about/about_functions.md#piping-objects-to-functions)。

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlockSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -End

指定在此 cmdlet 处理所有输入对象之后运行的脚本块。 此脚本块仅对整个管道运行一次。 有关块的详细信息 `end` ，请参阅 [about_Functions](about/about_functions.md#piping-objects-to-functions)。

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlockSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

指定输入对象。 `ForEach-Object` 在每个输入对象上运行脚本块或操作语句。 输入一个包含对象的变量，或键入可获取对象的命令或表达式。

当你将 **inputobject** 参数与一起使用时 `ForEach-Object` ， `ForEach-Object` **inputobject** 值将被视为单个对象，而不是管道将命令结果传递给。 即使该值是作为命令结果的集合（如），也是如此 `-InputObject (Get-Process)` 。
由于 **InputObject** 无法从数组或对象的集合返回各个属性，因此，如果您使用在 `ForEach-Object` 已定义的属性中具有特定值的那些对象的对象集合上执行操作，则建议您 `ForEach-Object` 在管道中使用，如本主题的示例中所示。

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MemberName

指定要获取的属性或要调用的方法。

允许使用通配符，但仅在生成的字符串解析为唯一值时才有效。
例如，如果运行的 `Get-Process | ForEach -MemberName *Name` 是，并且存在多个具有包含字符串名称（如 **ProcessName** 和 **name** 属性）的名称的成员，则该命令将失败。

已在 Windows PowerShell 3.0 中引入了此参数。

```yaml
Type: System.String
Parameter Sets: PropertyAndMethodSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Process

指定对每个输入对象所执行的操作。 为管道中的每个对象运行此脚本块。 有关块的详细信息 `process` ，请参阅 [about_Functions](about/about_functions.md#piping-objects-to-functions)。

向 **Process** 参数提供多个脚本块时，第一个脚本块将始终映射到 `begin` 块。 如果只有两个脚本块，则第二个块映射到 `process` 块。 如果有三个或更多脚本块，则第一个脚本块始终映射到 `begin` 块，最后一个块映射到块 `end` ，而介于之间的块全部映射到 `process` 块。

```yaml
Type: System.Management.Automation.ScriptBlock[]
Parameter Sets: ScriptBlockSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemainingScripts

指定 **进程** 参数不会使用的所有脚本块。

已在 Windows PowerShell 3.0 中引入了此参数。

```yaml
Type: System.Management.Automation.ScriptBlock[]
Parameter Sets: ScriptBlockSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

提示你在运行 cmdlet 之前进行确认。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

显示运行该 cmdlet 时会发生什么情况。 此 cmdlet 未运行。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### System.Management.Automation.PSObject

你可以通过管道将任何对象传递给此 cmdlet。

## Outputs

### System.Management.Automation.PSObject

此 cmdlet 将返回由输入确定的对象。

## 注释

- 此 `ForEach-Object` cmdlet 的工作方式与 **foreach** 语句非常相似，不同之处在于你不能通过管道将输入传递给 **foreach** 语句。 有关 **Foreach** 语句的详细信息，请参阅 [about_Foreach](./About/about_Foreach.md)。

- 从 PowerShell 4.0 开始， `Where` `ForEach` 添加了方法以与集合一起使用。 可在此处阅读有关这些新方法的详细信息 [about_arrays](./About/about_Arrays.md)

## 相关链接

[Compare-Object](../Microsoft.PowerShell.Utility/Compare-Object.md)

[Where-Object](Where-Object.md)

[Group-Object](../Microsoft.PowerShell.Utility/Group-Object.md)

[Measure-Object](../Microsoft.PowerShell.Utility/Measure-Object.md)

[New-Object](../Microsoft.PowerShell.Utility/New-Object.md)

[Select-Object](../Microsoft.PowerShell.Utility/Select-Object.md)

[Sort-Object](../Microsoft.PowerShell.Utility/Sort-Object.md)

[Tee-Object](../Microsoft.PowerShell.Utility/Tee-Object.md)
