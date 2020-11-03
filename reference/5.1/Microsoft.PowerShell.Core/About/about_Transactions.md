---
description: 介绍如何在 PowerShell 中管理事务处理操作。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_transactions?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Transactions
ms.openlocfilehash: 522e0f727754b0b0153571039f3bf3966d0abf20
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200050"
---
# <a name="about-transactions"></a>关于事务

## <a name="short-description"></a>简短说明

介绍如何在 PowerShell 中管理事务处理操作。

## <a name="long-description"></a>详细说明

从 PowerShell 2.0 开始，PowerShell 支持事务。 利用此功能，您可以启动事务，指示哪些命令是事务的一部分，以及提交或回滚事务。

## <a name="about-transactions"></a>关于事务

在 PowerShell 中，事务是作为一个逻辑单元进行管理的一个或多个命令的集合。 事务可以 ( "已提交" ) 完成，这将更改受事务影响的数据。 或者，事务可以完全撤消 ( "回滚" ) 以便事务不更改受影响的数据。

由于事务中的命令作为一个单元进行管理，因此要么提交所有命令，要么回滚所有命令。

事务广泛用于数据处理，最值得注意的是数据库操作和财务交易。 当一组命令的最坏情况下，事务不会失败，但某些命令在其他情况下会成功，而其他命令则会失败，使系统处于损坏、误报或 uninterpretable 状态，难于修复。

## <a name="transaction-cmdlets"></a>事务 CMDLET

PowerShell 包含用于管理事务的多个 cmdlet。

- Start-Transaction：启动新的事务。
- 使用事务：向事务中添加命令或表达式。 此命令必须使用启用事务的对象。
- Undo-Transaction：回滚事务，使事务不更改数据。
- Complete-Transaction：提交事务。 更改受事务影响的数据。
- 获取事务：获取有关活动事务的信息。

要获取事务 cmdlet 列表，请键入：

```powershell
get-command *transaction
```

有关 cmdlet 的详细信息，请键入：

```powershell
get-help use-transaction -detailed
```

## <a name="transaction-enabled-elements"></a>启用事务的元素

若要参与事务，cmdlet 和提供程序都必须支持事务。 此功能内置于受事务影响的对象。

PowerShell 注册表提供程序在 Windows Vista 中支持事务。 TransactedString 对象 (TransactedString) 可与运行 PowerShell 的任何操作系统配合使用。

其他 PowerShell 提供程序可以支持事务。 若要在会话中查找支持事务的 PowerShell 提供程序，请使用以下命令在提供程序的功能属性中查找 "事务" 值：

```powershell
get-psprovider | where {$_.Capabilities -like "*transactions*"}
```

有关提供程序的详细信息，请参阅提供程序的帮助。 若要获取提供程序帮助，请键入：

```
get-help <provider-name>
```

例如，若要获取有关 Registry 提供程序的帮助，请键入：

```powershell
get-help registry
```

## <a name="the-usetransaction-parameter"></a>USETRANSACTION 参数

可支持事务的 cmdlet 具有 UseTransaction 参数。 此参数将命令包含在活动事务中。 您可以使用完整参数名或其别名 "usetx"。

参数只能在会话包含活动事务时使用。 如果在没有活动事务时输入带有 UseTransaction 参数的命令，则该命令将失败。

若要查找具有 UseTransaction 参数的 cmdlet，请键入：

```powershell
get-help * -parameter UseTransaction
```

在 PowerShell core 中，所有旨在使用 PowerShell 提供程序的 cmdlet 都支持事务。 因此，你可以使用提供程序 cmdlet 来管理事务。

有关 PowerShell 提供程序的详细信息，请参阅 [about_Providers](about_Providers.md)。

## <a name="the-transaction-object"></a>TRANSACTION 对象

事务在 PowerShell 中通过事务对象的 System.object 表示。

该对象包含以下属性：

- RollbackPreference：包含当前事务的回滚首选项集。 您可以在使用 Start-Transaction 启动事务时设置 rollback 首选项。

  Rollback 首选项确定了自动回滚事务的条件。 有效值为 Error、TerminatingError 和 Never。 默认值为 "错误"。

- Status：包含事务的当前状态。 有效值为 "活动"、"已提交" 和 "RolledBack"。

- SubscriberCount：包含事务的订阅服务器的数目。 当你在另一个事务正在进行时启动事务时，将向事务中添加一个订阅服务器。 订阅服务器提交事务时，订阅服务器计数将减少。

## <a name="active-transactions"></a>活动事务

在 PowerShell 中，一次只能有一个事务处于活动状态，并且只能管理活动事务。 同一会话中可能正在进行多个事务，但只有最新启动的事务处于活动状态。

因此，在使用事务 cmdlet 时，不能指定特定的事务。 命令始终应用于活动事务。

在 Get-Transaction cmdlet 的行为中，这是最明显的。 输入 Get-Transaction 命令时，Get-Transaction 始终只获取一个 transaction 对象。 此对象是表示活动事务的对象。

若要管理不同的事务，必须先通过提交或回滚活动事务来完成该事务。 执行此操作时，前一个事务会自动变为活动状态。 事务会按照它们的启动顺序处于活动状态，因此，最新启动的事务始终处于活动状态。

## <a name="subscribers-and-independent-transactions"></a>订阅服务器和独立事务

如果在另一个事务正在进行时启动事务，则默认情况下，PowerShell 不会启动新的事务。 相反，它会将 "订阅服务器" 添加到当前事务中。

当某个事务有多个订阅服务器时，在任何时候都有单个 Undo-Transaction 命令将回滚所有订阅服务器的整个事务。 但是，若要提交事务，你必须为每个订阅服务器输入 Complete-Transaction 命令。

若要查找事务的订阅服务器数，请检查 transaction 对象的 SubscriberCount 属性。 例如，以下命令使用 Get-Transaction cmdlet 获取活动事务的 SubscriberCount 属性的值：

```powershell
(Get-Transaction).SubscriberCount
```

添加订阅服务器是默认行为，因为当另一个事务正在进行时，大多数已启动的事务与原始事务相关。 在典型模型中，包含事务的脚本将调用包含其自己的事务的帮助器脚本。 由于事务是相关的，因此应将它们回滚或作为一个单元提交。

但是，可以使用 Start-Transaction cmdlet 的独立参数启动与当前事务无关的事务。

启动独立事务时，Start-Transaction 会创建一个新的 transaction 对象，而新事务将成为活动事务。
独立事务可以提交或回滚，而不会影响原始事务。

当独立事务 (提交或回滚) 时，原来的事务将再次成为活动事务。

## <a name="changing-data"></a>更改数据

当使用事务更改数据时，在提交事务之前，不会更改事务影响的数据。 但是，不属于事务的命令可以更改相同的数据。

使用事务来管理共享数据时，请记住这一点。
通常，数据库具有在处理数据时锁定数据的机制，阻止其他用户以及其他命令、脚本和函数更改。

但是，该锁是数据库的一项功能。 它与事务无关。 如果正在启用事务的文件系统或其他数据存储中工作，则可以在事务进行过程中更改数据。

## <a name="examples"></a>示例

本部分中的示例使用 PowerShell 注册表提供程序，并假定你熟悉它。 有关注册表提供程序的信息，请键入 "get-help Registry"。

### <a name="example-1-committing-a-transaction"></a>示例1：提交事务

若要创建事务，请使用 Start-Transaction cmdlet。 以下命令使用默认设置启动一个事务。

```powershell
start-transaction
```

若要在事务中包含命令，请使用 cmdlet 的 UseTransaction 参数。 默认情况下，不会将命令包含在事务中，

例如，以下命令（用于设置 HKCU：驱动器的软件密钥中的当前位置）不包含在事务中。

```powershell
cd hkcu:\Software
```

以下用于创建 MyCompany 密钥的命令使用 New-Item cmdlet 的 UseTransaction 参数将该命令包含在活动事务中。

```powershell
new-item MyCompany -UseTransaction
```

命令返回一个表示新键的对象，但由于该命令是事务的一部分，因此注册表尚未更改。

```
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
  0   0 MyCompany                      {}
```

若要提交事务，请使用 Complete-Transaction cmdlet。 由于它始终影响活动事务，因此不能指定事务。

```powershell
complete-transaction
```

因此，会将 MyCompany 项添加到注册表中。

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

### <a name="example-2-rolling-back-a-transaction"></a>示例2：回滚事务

若要创建事务，请使用 Start-Transaction cmdlet。 以下命令使用默认设置启动一个事务。

```powershell
start-transaction
```

以下用于创建 MyOtherCompany 密钥的命令使用 New-Item cmdlet 的 UseTransaction 参数将该命令包含在活动事务中。

```powershell
new-item MyOtherCompany -UseTransaction
```

命令返回一个表示新键的对象，但由于该命令是事务的一部分，因此注册表尚未更改。

```
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
  0   0 MyOtherCompany                 {}
```

若要回滚事务，请使用 Undo-Transaction cmdlet。 由于它始终影响活动事务，因此您不能指定事务。

```powershell
Undo-transaction
```

结果是不会将 MyOtherCompany 键添加到注册表中。

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

### <a name="example-3-previewing-a-transaction"></a>示例3：预览事务

通常，在事务中使用的命令将更改数据。 但是，获取数据的命令也会在事务中使用，因为它们会在事务中获取数据。 这会提供提交事务的更改的预览。

下面的示例演示如何使用 Get-ChildItem 命令 (别名为 "dir" ) 预览事务中的更改。

下面的命令启动一个事务。

```powershell
start-transaction
```

以下命令使用 New-ItemProperty cmdlet 将 MyKey 注册表条目添加到 MyCompany 项。 该命令使用 UseTransaction 参数将命令包含在事务中。

```powershell
new-itemproperty -path MyCompany -Name MyKey -value 123 -UseTransaction
```

该命令将返回一个表示新注册表项的对象，但不会更改注册表项。

```
MyKey
-----
123
```

若要获取注册表中的当前项，请使用 Get-ChildItem 命令 ( "dir" ) ，而不使用 UseTransaction 参数。 以下命令将获取以 "M" 开头的项。

```powershell
dir m*
```

结果显示尚未将任何条目添加到 MyCompany 项。

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

若要预览提交事务的效果，请使用 UseTransaction 参数输入 Get-ChildItem ( "dir" ) 命令。 此命令从事务内查看数据。

```powershell
dir m* -useTransaction
```

结果显示，如果提交事务，MyKey 条目将添加到 MyCompany 键。

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   1 MyCompany                      {MyKey}
```

### <a name="example-4-combining-transacted-and-non-transacted-commands"></a>示例4：合并事务和非事务处理命令

可以在事务中输入非事务性命令。 非事务性命令会立即影响数据，但不会影响事务。
以下命令在 HKCU： \ Software 注册表项中启动一个事务。

```powershell
start-transaction
```

接下来的三个命令使用 New-Item cmdlet 向注册表中添加项。
第一条和第三条命令使用 UseTransaction 参数将命令包含在事务中。 第二个命令省略了该参数。 由于第二个命令未包含在事务中，因此它会立即生效。

```powershell
new-item MyCompany1 -UseTransaction
new-item MyCompany2
new-item MyCompany3 -UseTransaction
```

若要查看注册表的当前状态，请使用不带 UseTransaction 参数的 Get-ChildItem ( "dir" ) 命令。 此命令获取以 "M" 开头的项。

```powershell
dir m*
```

结果显示，MyCompany2 项已添加到注册表中，但不会添加 MyCompany1 和 MyCompany3 键，这是事务的一部分。

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0    0 MyCompany2                     {}
```

以下命令将提交事务。

```powershell
complete-transaction
```

现在，作为事务一部分添加的密钥显示在注册表中。

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
83   1 Microsoft                      {(default)}
0    0 MyCompany1                     {}
0    0 MyCompany2                     {}
0    0 MyCompany3                     {}
```

### <a name="example-5-using-automatic-rollback"></a>示例5：使用自动回滚

当事务中的命令生成任意类型的错误时，将自动回滚该事务。

此默认行为是针对运行事务的脚本而设计的。 脚本通常经过良好的测试并包含错误处理逻辑，因此错误不是预期的，应终止事务。

第一个命令在 HKCU： \ Software 注册表项中启动一个事务。

```powershell
start-transaction
```

以下命令使用 New-Item cmdlet 将 MyCompany 项添加到注册表。 该命令使用 UseTransaction 参数 (别名为 "usetx" ) ，以将命令包含在事务中。

```powershell
New-Item MyCompany -UseTX
```

由于注册表中已经存在 MyCompany 项，因此该命令将失败，并且将回滚该事务。

```output
New-Item : A key at this path already exists
At line:1 char:9
+ new-item <<<<  MyCompany -usetx
```

Get-Transaction 命令确认事务已回滚并且 SubscriberCount 为0。

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                0                 RolledBack
```

### <a name="example-6-changing-the-rollback-preference"></a>示例6：更改 ROLLBACK 首选项

如果希望事务更容错，可以使用 Start-Transaction 的 RollbackPreference 参数来更改首选项。

下面的命令启动一个事务，该事务的 rollback 首选项为 "Never"。

```powershell
start-transaction -rollbackpreference Never
```

在这种情况下，当命令失败时，不会自动回滚事务。

```powershell
New-Item MyCompany -UseTX
```

```output
New-Item : A key at this path already exists
At line:1 char:9
+ new-item <<<<  MyCompany -usetx
```

由于事务仍处于活动状态，因此你可以在事务中重新提交此命令。

```powershell
New-Item MyOtherCompany -UseTX
```

### <a name="example-7-using-the-use-transaction-cmdlet"></a>示例7：使用使用事务 CMDLET

Use-Transaction cmdlet 可让你针对启用事务的 Microsoft .NET 框架对象执行直接脚本编写。 Use-Transaction 采用一个脚本块，该脚本块只能包含使用启用事务的 .NET Framework 对象（如 TransactedString 类的实例）的命令和表达式。

下面的命令启动一个事务。

```powershell
start-transaction
```

下面的 New-Object 命令创建 TransactedString 类的一个实例，并将其保存在 $t 变量中。

```powershell
$t = New-Object Microsoft.PowerShell.Commands.Management.TransactedString
```

下面的命令使用 TransactedString 对象的 Append 方法将文本添加到字符串。 由于该命令不是事务的一部分，因此更改将立即生效。

```powershell
$t.append("Windows")
```

以下命令使用相同的 Append 方法来添加文本，但会将文本添加为事务的一部分。 命令括在大括号内，并将其设置为使用事务的 ScriptBlock 参数的值。 需要 UseTransaction 参数 (UseTx) 。

```powershell
use-transaction {$t.append(" PowerShell")} -usetx
```

若要查看 $t 中的事务处理字符串的当前内容，请使用 TransactedString 对象的 ToString 方法。

```powershell
$t.tostring()
```

输出显示只有非事务性更改才有效。

```output
Windows
```

若要查看事务内 $t 中的事务处理字符串的当前内容，请在 Use-Transaction 命令中嵌入表达式。

```powershell
use-transaction {$s.tostring()} -usetx
```

输出显示事务视图。

```output
PowerShell
```

以下命令将提交事务。

```powershell
complete-transaction
```

若要查看最终字符串：

```
$t.tostring()
PowerShell
```

### <a name="example-8-managing-multi-subscriber-transactions"></a>示例8：管理多订户事务

当在另一个事务正在进行时启动事务时，默认情况下，PowerShell 不会创建第二个事务。 相反，它会将订阅者添加到当前事务中。

此示例演示如何查看和管理多订户事务。

首先，在 HKCU： \ Software 密钥中启动一个事务。

```powershell
start-transaction
```

以下命令使用 Get-Transaction 命令获取活动事务。

```powershell
get-transaction
```

结果显示表示活动事务的对象。

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

以下命令将 MyCompany 键添加到注册表。 该命令使用 UseTransaction 参数将命令包含在事务中。

```powershell
new-item MyCompany -UseTransaction
```

以下命令使用 Start-Transaction 命令启动事务。 尽管此命令在命令提示符下键入，但当你运行包含事务的脚本时，可能会出现这种情况。

```powershell
start-transaction
```

Get-Transaction 的命令显示，事务对象上的订阅服务器计数是递增的。 值现在为2。

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                2                 Active
```

下一个命令使用 New-ItemProperty cmdlet 将 MyKey 注册表条目添加到 MyCompany 项。 它使用 UseTransaction 参数将命令包含在事务中。

```powershell
new-itemproperty -path MyCompany -name MyKey -UseTransaction
```

注册表中不存在 MyCompany 项，但此命令成功，因为这两个命令是同一事务的一部分。

以下命令将提交事务。 如果回滚事务，则会为所有订阅服务器回滚该事务。

```powershell
complete-transaction
```

Get-Transaction 命令显示事务对象上的订阅服务器计数为1，但状态的值仍处于活动状态， (未提交的) 。

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

若要完成事务提交，请输入第二个完整事务命令。 若要提交多订户事务，你必须为每个 Start-Transaction 命令输入一个 Complete-Transaction 命令。

```powershell
complete-transaction
```

另一个 Get-Transaction 命令显示事务已提交。

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                0                 Committed
```

### <a name="example-9-managing-independent-transactions"></a>示例9：管理独立事务

当在另一个事务正在进行时启动事务时，可以使用 Start-Transaction 的独立参数，使新事务独立于原始事务。

执行此操作时，Start-Transaction 会创建一个新的 transaction 对象，并使新事务成为活动事务。

首先，在 HKCU： Software 密钥中启动一个事务 \\ 。

```powershell
start-transaction
```

以下命令使用 Get-Transaction 命令获取活动事务。

```powershell
get-transaction
```

结果显示表示活动事务的对象。

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

以下命令将 MyCompany 注册表项作为事务的一部分添加。 它使用 UseTransaction 参数 (UseTx) 将命令包含在活动事务中。

```powershell
new-item MyCompany -use
```

以下命令将启动新事务。 该命令使用独立参数指示此事务不是活动事务的订阅服务器。

```powershell
start-transaction -independent
```

创建独立事务时，最近创建的新 () 事务将成为活动事务。 您可以使用 Get-Transaction 命令获取活动事务。

```powershell
get-transaction
```

请注意，事务的 SubscriberCount 为1，表示没有其他订阅服务器，并且该事务是新的。

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

必须先提交或回滚) 新事务，然后才能管理原始事务 (。

以下命令将 MyOtherCompany 键添加到注册表。 它使用 UseTransaction 参数 (UseTx) 将命令包含在活动事务中。

```powershell
new-item MyOtherCompany -usetx
```

现在，回滚事务。 如果有两个订阅服务器的单个事务，回滚事务会回滚所有订阅服务器的整个事务。

但是，因为这些事务是独立的，所以回滚最新的事务会取消注册表更改，并使原始事务成为活动事务。

```powershell
undo-transaction
```

Get-Transaction 命令确认原始事务在会话中是否仍处于活动状态。

```powershell
get-transaction
```

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

以下命令将提交活动事务。

```powershell
complete-transaction
```

Get-ChildItem 命令显示注册表已更改。

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

## <a name="see-also"></a>另请参阅

[Start-Transaction](xref:Microsoft.PowerShell.Management.Start-Transaction)

[Get-Transaction](xref:Microsoft.PowerShell.Management.Get-Transaction)

[Complete-Transaction](xref:Microsoft.PowerShell.Management.Complete-Transaction)

[Undo-Transaction](xref:Microsoft.PowerShell.Management.Undo-Transaction)

[Use-Transaction](xref:Microsoft.PowerShell.Management.Use-Transaction)

[Get-PSProvider](xref:Microsoft.PowerShell.Management.Get-PSProvider)

[Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

[about_Providers](about_Providers.md)
