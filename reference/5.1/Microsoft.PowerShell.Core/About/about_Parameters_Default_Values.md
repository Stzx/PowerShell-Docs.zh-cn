---
description: 描述如何为 cmdlet 参数和高级函数设置自定义默认值。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 5/31/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_parameters_default_values?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Parameters_Default_Values
ms.openlocfilehash: 286ffff28a88dbb29ce3ce83cea02b403eafd992
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200273"
---
# <a name="about-parameters-default-values"></a><span data-ttu-id="a0e78-104">关于参数默认值</span><span class="sxs-lookup"><span data-stu-id="a0e78-104">About Parameters Default Values</span></span>

## <a name="short-description"></a><span data-ttu-id="a0e78-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="a0e78-105">Short description</span></span>

<span data-ttu-id="a0e78-106">描述如何为 cmdlet 参数和高级函数设置自定义默认值。</span><span class="sxs-lookup"><span data-stu-id="a0e78-106">Describes how to set custom default values for cmdlet parameters and advanced functions.</span></span>

## <a name="long-description"></a><span data-ttu-id="a0e78-107">长说明</span><span class="sxs-lookup"><span data-stu-id="a0e78-107">Long description</span></span>

<span data-ttu-id="a0e78-108">`$PSDefaultParameterValues`首选项变量使你能够为任何 cmdlet 或高级函数指定自定义默认值。</span><span class="sxs-lookup"><span data-stu-id="a0e78-108">The `$PSDefaultParameterValues` preference variable lets you specify custom default values for any cmdlet or advanced function.</span></span> <span data-ttu-id="a0e78-109">Cmdlet 和高级函数使用自定义默认值，除非在命令中指定另一个值。</span><span class="sxs-lookup"><span data-stu-id="a0e78-109">Cmdlets and advanced functions use the custom default value unless you specify another value in the command.</span></span>

<span data-ttu-id="a0e78-110">Cmdlet 和高级函数的作者为其参数设置标准默认值。</span><span class="sxs-lookup"><span data-stu-id="a0e78-110">The authors of cmdlets and advanced functions set standard default values for their parameters.</span></span> <span data-ttu-id="a0e78-111">通常，标准默认值非常有用，但它们可能不适用于所有环境。</span><span class="sxs-lookup"><span data-stu-id="a0e78-111">Typically, the standard default values are useful, but they might not be appropriate for all environments.</span></span>

<span data-ttu-id="a0e78-112">当你在每次使用该命令时或者当某个特定参数值难以记住时，此功能特别有用，例如电子邮件服务器名称或项目 GUID。</span><span class="sxs-lookup"><span data-stu-id="a0e78-112">This feature is especially useful when you must specify the same alternate parameter value nearly every time you use the command or when a particular parameter value is difficult to remember, such as an email server name or project GUID.</span></span>

<span data-ttu-id="a0e78-113">如果所需的默认值因情况而异，则可以指定在不同条件下为参数提供不同默认值的脚本块。</span><span class="sxs-lookup"><span data-stu-id="a0e78-113">If the desired default value varies predictably, you can specify a script block that provides different default values for a parameter under different conditions.</span></span>

<span data-ttu-id="a0e78-114">`$PSDefaultParameterValues` 是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="a0e78-114">`$PSDefaultParameterValues` was introduced in PowerShell 3.0.</span></span>

## <a name="syntax"></a><span data-ttu-id="a0e78-115">语法</span><span class="sxs-lookup"><span data-stu-id="a0e78-115">Syntax</span></span>

<span data-ttu-id="a0e78-116">`$PSDefaultParameterValues`变量是一个哈希表，它将键的格式作为 **DefaultParameterDictionary** 的对象类型进行验证。</span><span class="sxs-lookup"><span data-stu-id="a0e78-116">The `$PSDefaultParameterValues` variable is a hash table that validates the format of keys as an object type of **System.Management.Automation.DefaultParameterDictionary** .</span></span> <span data-ttu-id="a0e78-117">哈希表包含 **键/值** 对。</span><span class="sxs-lookup"><span data-stu-id="a0e78-117">The hash table contains **Key/Value** pairs.</span></span> <span data-ttu-id="a0e78-118">**键** 的格式为 `CmdletName:ParameterName` 。</span><span class="sxs-lookup"><span data-stu-id="a0e78-118">A **Key** is in the format `CmdletName:ParameterName`.</span></span> <span data-ttu-id="a0e78-119">**值** 是分配给该键的 **DefaultValue** 或 **ScriptBlock** 。</span><span class="sxs-lookup"><span data-stu-id="a0e78-119">A **Value** is the **DefaultValue** or **ScriptBlock** assigned to the key.</span></span>

<span data-ttu-id="a0e78-120">`$PSDefaultParameterValues`首选项变量的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="a0e78-120">The syntax of the `$PSDefaultParameterValues` preference variable is as follows:</span></span>

```
$PSDefaultParameterValues=@{"CmdletName:ParameterName"="DefaultValue"}

$PSDefaultParameterValues=@{ "CmdletName:ParameterName"={{ScriptBlock}} }

$PSDefaultParameterValues["Disabled"]=$True | $False
```

<span data-ttu-id="a0e78-121">**CmdletName** 和 **ParameterName** 值中允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="a0e78-121">Wildcard characters are permitted in the **CmdletName** and **ParameterName** values.</span></span>

<span data-ttu-id="a0e78-122">若要从设置、更改、添加或删除特定的 **键/值** 对 `$PSDefaultParameterValues` ，请使用方法编辑标准哈希表。</span><span class="sxs-lookup"><span data-stu-id="a0e78-122">To set, change, add, or remove a specific **Key/Value** pair from `$PSDefaultParameterValues`, use the methods to edit a standard hash table.</span></span> <span data-ttu-id="a0e78-123">例如，" **添加** " 和 " **移除** " 方法。</span><span class="sxs-lookup"><span data-stu-id="a0e78-123">For example, the **Add** and **Remove** methods.</span></span> <span data-ttu-id="a0e78-124">这些方法不会覆盖哈希表中的其他值。</span><span class="sxs-lookup"><span data-stu-id="a0e78-124">These methods don't overwrite other values in the hash table.</span></span>

<span data-ttu-id="a0e78-125">还有另一个不覆盖现有 `$PSDefaultParameterValues` 哈希表的语法。</span><span class="sxs-lookup"><span data-stu-id="a0e78-125">There's another syntax that doesn't overwrite an existing `$PSDefaultParameterValues` hash table.</span></span> <span data-ttu-id="a0e78-126">若要添加或更改特定的 **键/值** 对，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="a0e78-126">To add or change a specific **Key/Value** pair, use the following syntax:</span></span>

```
$PSDefaultParameterValues["CmdletName:ParameterName"]="DefaultValue"
```

<span data-ttu-id="a0e78-127">**CmdletName** 必须是 cmdlet 的名称或使用 **CmdletBinding** 属性的高级函数的名称。</span><span class="sxs-lookup"><span data-stu-id="a0e78-127">The **CmdletName** must be the name of a cmdlet or the name of an advanced function that uses the **CmdletBinding** attribute.</span></span> <span data-ttu-id="a0e78-128">不能使用 `$PSDefaultParameterValues` 来指定脚本或简单函数的默认值。</span><span class="sxs-lookup"><span data-stu-id="a0e78-128">You can't use `$PSDefaultParameterValues` to specify default values for scripts or simple functions.</span></span>

<span data-ttu-id="a0e78-129">**DefaultValue** 可以是对象或脚本块。</span><span class="sxs-lookup"><span data-stu-id="a0e78-129">The **DefaultValue** can be an object or a script block.</span></span> <span data-ttu-id="a0e78-130">如果值是脚本块，则 PowerShell 将计算脚本块，并将结果用作参数值。</span><span class="sxs-lookup"><span data-stu-id="a0e78-130">If the value is a script block, PowerShell evaluates the script block and uses the result as the parameter value.</span></span> <span data-ttu-id="a0e78-131">当指定的参数接受脚本块值时，将脚本块值括在另一组大括号中，例如：</span><span class="sxs-lookup"><span data-stu-id="a0e78-131">When the specified parameter accepts a script block value, enclose the script block value in a second set of braces, such as:</span></span>

```powershell
$PSDefaultParameterValues=@{ "Invoke-Command:ScriptBlock"={{Get-Process}} }
```

<span data-ttu-id="a0e78-132">有关详细信息，请参阅以下文档：</span><span class="sxs-lookup"><span data-stu-id="a0e78-132">For more information, see the following documents:</span></span>

- [<span data-ttu-id="a0e78-133">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="a0e78-133">about_Hash_Tables</span></span>](about_Hash_Tables.md)
- [<span data-ttu-id="a0e78-134">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="a0e78-134">about_Script_Blocks</span></span>](about_Script_Blocks.md)
- [<span data-ttu-id="a0e78-135">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="a0e78-135">about_Preference_Variables</span></span>](about_Preference_Variables.md)

## <a name="examples"></a><span data-ttu-id="a0e78-136">示例</span><span class="sxs-lookup"><span data-stu-id="a0e78-136">Examples</span></span>

### <a name="how-to-set-psdefaultparametervalues"></a><span data-ttu-id="a0e78-137">如何设置 \$ PSDefaultParameterValues</span><span class="sxs-lookup"><span data-stu-id="a0e78-137">How to set \$PSDefaultParameterValues</span></span>

<span data-ttu-id="a0e78-138">`$PSDefaultParameterValues` 是一个首选项变量，因此它只存在于其设置的会话中。</span><span class="sxs-lookup"><span data-stu-id="a0e78-138">`$PSDefaultParameterValues` is a preference variable, so it exists only in the session in which it's set.</span></span> <span data-ttu-id="a0e78-139">它没有默认值。</span><span class="sxs-lookup"><span data-stu-id="a0e78-139">It has no default value.</span></span>

<span data-ttu-id="a0e78-140">若要设置 `$PSDefaultParameterValues` ，请键入变量名称以及一个或多个 **键/值** 对。</span><span class="sxs-lookup"><span data-stu-id="a0e78-140">To set `$PSDefaultParameterValues`, type the variable name and one or more **Key/Value** pairs.</span></span> <span data-ttu-id="a0e78-141">如果运行另一个 `$PSDefaultParameterValues` 命令，它将覆盖现有的哈希表。</span><span class="sxs-lookup"><span data-stu-id="a0e78-141">If you run another `$PSDefaultParameterValues` command, it overwrites the existing hash table.</span></span>

<span data-ttu-id="a0e78-142">有关如何更改 **键/值** 对而不覆盖现有哈希表值的示例，请参阅 [如何在 \$ PSDefaultParameterValues 中添加值](#how-to-add-values-to-psdefaultparametervalues) 或 [如何在 \$ PSDefaultParameterValues 中更改值](#how-to-change-values-in-psdefaultparametervalues)。</span><span class="sxs-lookup"><span data-stu-id="a0e78-142">For examples about how to change **Key/Value** pairs without overwriting existing hash table values, see [How to add values to \$PSDefaultParameterValues](#how-to-add-values-to-psdefaultparametervalues) or [How to change values in \$PSDefaultParameterValues](#how-to-change-values-in-psdefaultparametervalues).</span></span>

<span data-ttu-id="a0e78-143">若要保存以 `$PSDefaultParameterValues` 供将来会话使用，请将 `$PSDefaultParameterValues` 命令添加到 PowerShell 配置文件。</span><span class="sxs-lookup"><span data-stu-id="a0e78-143">To save `$PSDefaultParameterValues` for future sessions, add a `$PSDefaultParameterValues` command to your PowerShell profile.</span></span> <span data-ttu-id="a0e78-144">有关详细信息，请参阅 [about_Profiles](about_Profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="a0e78-144">For more information, see [about_Profiles](about_Profiles.md).</span></span>

#### <a name="set-a-custom-default-value"></a><span data-ttu-id="a0e78-145">设置自定义默认值</span><span class="sxs-lookup"><span data-stu-id="a0e78-145">Set a custom default value</span></span>

<span data-ttu-id="a0e78-146">**键/值** 对将密钥设置 `Send-MailMessage:SmtpServer` 为自定义默认值 **Server123** 。</span><span class="sxs-lookup"><span data-stu-id="a0e78-146">The **Key/Value** pair sets the `Send-MailMessage:SmtpServer` key to a custom default value of **Server123** .</span></span>

```powershell
$PSDefaultParameterValues = @{
  "Send-MailMessage:SmtpServer"="Server123"
}
```

#### <a name="set-default-values-for-multiple-parameters"></a><span data-ttu-id="a0e78-147">为多个参数设置默认值</span><span class="sxs-lookup"><span data-stu-id="a0e78-147">Set default values for multiple parameters</span></span>

<span data-ttu-id="a0e78-148">若要为多个参数设置默认值，请用分号分隔每个 **键/值** 对 (`;`) 。</span><span class="sxs-lookup"><span data-stu-id="a0e78-148">To set default values for multiple parameters, separate each **Key/Value** pair with a semicolon (`;`).</span></span> <span data-ttu-id="a0e78-149">`Send-MailMessage:SmtpServer`和 `Get-WinEvent:LogName` 键设置为自定义默认值。</span><span class="sxs-lookup"><span data-stu-id="a0e78-149">The `Send-MailMessage:SmtpServer` and `Get-WinEvent:LogName` keys are set to custom default values.</span></span>

```powershell
$PSDefaultParameterValues = @{
  "Send-MailMessage:SmtpServer"="Server123";
  "Get-WinEvent:LogName"="Microsoft-Windows-PrintService/Operational"
}
```

#### <a name="use-wildcards-and-switch-parameters"></a><span data-ttu-id="a0e78-150">使用通配符和开关参数</span><span class="sxs-lookup"><span data-stu-id="a0e78-150">Use wildcards and switch parameters</span></span>

<span data-ttu-id="a0e78-151">Cmdlet 和参数名称可以包含通配符。</span><span class="sxs-lookup"><span data-stu-id="a0e78-151">The cmdlet and parameter names can contain wildcard characters.</span></span> <span data-ttu-id="a0e78-152">使用 `$True` 和 `$False` 设置开关参数的值，例如 " **详细** "。</span><span class="sxs-lookup"><span data-stu-id="a0e78-152">Use `$True` and `$False` to set values for switch parameters, such as **Verbose** .</span></span> <span data-ttu-id="a0e78-153">对于所有命令，通用参数的 **Verbose** 参数均设置为 `$True` 。</span><span class="sxs-lookup"><span data-stu-id="a0e78-153">The common parameter's **Verbose** parameter is set to `$True` for all commands.</span></span>

```powershell
$PSDefaultParameterValues = @{"*:Verbose"=$True}
```

#### <a name="use-an-array-for-the-default-value"></a><span data-ttu-id="a0e78-154">使用数组作为默认值</span><span class="sxs-lookup"><span data-stu-id="a0e78-154">Use an array for the default value</span></span>

<span data-ttu-id="a0e78-155">如果参数可以接受多个值，则可以将多个值设置为默认值。</span><span class="sxs-lookup"><span data-stu-id="a0e78-155">If a parameter can accept multiple values, an array, you can set multiple values as the default values.</span></span> <span data-ttu-id="a0e78-156">该键的默认值 `Invoke-Command:ComputerName` 设置为 **Server01** 和 **Server02** 的数组值。</span><span class="sxs-lookup"><span data-stu-id="a0e78-156">The default value of the `Invoke-Command:ComputerName` key is set to an array value of **Server01** and **Server02** .</span></span>

```powershell
$PSDefaultParameterValues = @{
  "Invoke-Command:ComputerName"="Server01","Server02"
}
```

#### <a name="use-a-script-block"></a><span data-ttu-id="a0e78-157">使用脚本块</span><span class="sxs-lookup"><span data-stu-id="a0e78-157">Use a script block</span></span>

<span data-ttu-id="a0e78-158">您可以使用脚本块在不同条件下为参数指定不同的默认值。</span><span class="sxs-lookup"><span data-stu-id="a0e78-158">You can use a script block to specify different default values for a parameter under different conditions.</span></span> <span data-ttu-id="a0e78-159">PowerShell 将计算脚本块，并将结果用作默认参数值。</span><span class="sxs-lookup"><span data-stu-id="a0e78-159">PowerShell evaluates the script block and uses the result as the default parameter value.</span></span>

<span data-ttu-id="a0e78-160">`Format-Table:AutoSize`键将参数切换为默认值 **True** 。</span><span class="sxs-lookup"><span data-stu-id="a0e78-160">The `Format-Table:AutoSize` key sets that switch parameter to a default value of **True** .</span></span> <span data-ttu-id="a0e78-161">`If`语句包含的条件 `$host.Name` 必须是 PowerShell 控制台 **ConsoleHost** 。</span><span class="sxs-lookup"><span data-stu-id="a0e78-161">The `If` statement contains a condition that the `$host.Name` must be the PowerShell console, **ConsoleHost** .</span></span>

```powershell
$PSDefaultParameterValues=@{
  "Format-Table:AutoSize"={if ($host.Name -eq "ConsoleHost"){$True}}
}
```

<span data-ttu-id="a0e78-162">如果参数接受脚本块值，请将脚本块括在一组额外的大括号中。</span><span class="sxs-lookup"><span data-stu-id="a0e78-162">If a parameter accepts a script block value, enclose the script block in an extra set of braces.</span></span> <span data-ttu-id="a0e78-163">当 PowerShell 评估外部脚本块时，结果为内部脚本块，并设置为默认参数值。</span><span class="sxs-lookup"><span data-stu-id="a0e78-163">When PowerShell evaluates the outer script block, the result is the inner script block, and that is set as the default parameter value.</span></span>

<span data-ttu-id="a0e78-164">`Invoke-Command:ScriptBlock`由于脚本块包含在另一组大括号中，因此设置为 **系统事件日志** 的默认值的键。</span><span class="sxs-lookup"><span data-stu-id="a0e78-164">The `Invoke-Command:ScriptBlock` key set to a default value of the **System event log** because the script block is enclosed in a second set of braces.</span></span> <span data-ttu-id="a0e78-165">脚本块的结果传递给 `Invoke-Command` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a0e78-165">The result of the script block is passed to the `Invoke-Command` cmdlet.</span></span>

```powershell
$PSDefaultParameterValues=@{
  "Invoke-Command:ScriptBlock"={{Get-EventLog -Log System}}
}
```

### <a name="how-to-get-psdefaultparametervalues"></a><span data-ttu-id="a0e78-166">如何获取 \$ PSDefaultParameterValues</span><span class="sxs-lookup"><span data-stu-id="a0e78-166">How to get \$PSDefaultParameterValues</span></span>

<span data-ttu-id="a0e78-167">通过在 PowerShell 提示符下输入来显示哈希表的值 `$PSDefaultParameterValues` 。</span><span class="sxs-lookup"><span data-stu-id="a0e78-167">The hash table values are displayed by entering `$PSDefaultParameterValues` at the PowerShell prompt.</span></span>

<span data-ttu-id="a0e78-168">`$PSDefaultParameterValues`哈希表是使用三个 **键/值** 对设置的。</span><span class="sxs-lookup"><span data-stu-id="a0e78-168">A `$PSDefaultParameterValues` hash table is set with three **Key/Value** pairs.</span></span>
<span data-ttu-id="a0e78-169">下面的示例使用此哈希表，其中介绍了如何添加、更改和删除中的值 `$PSDefaultParameterValues` 。</span><span class="sxs-lookup"><span data-stu-id="a0e78-169">This hash table is used in the following examples that describe how to add, change, and remove values from `$PSDefaultParameterValues`.</span></span>

```
PS> $PSDefaultParameterValues = @{
  "Send-MailMessage:SmtpServer"="Server123"
  "Get-WinEvent:LogName"="Microsoft-Windows-PrintService/Operational"
  "Get-*:Verbose"=$True
}

PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    Server123
```

<span data-ttu-id="a0e78-170">若要获取特定键的值 `CmdletName:ParameterName` ，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="a0e78-170">To get the value of a specific `CmdletName:ParameterName` key, use the following syntax:</span></span>

```
$PSDefaultParameterValues["CmdletName:ParameterName"]
```

<span data-ttu-id="a0e78-171">例如，若要获取键的值，则为 `Send-MailMessage:SmtpServer` 。</span><span class="sxs-lookup"><span data-stu-id="a0e78-171">For example, to get the value for the `Send-MailMessage:SmtpServer` key.</span></span>

```
PS> $PSDefaultParameterValues["Send-MailMessage:SmtpServer"]
Server123
```

### <a name="how-to-add-values-to-psdefaultparametervalues"></a><span data-ttu-id="a0e78-172">如何向 PSDefaultParameterValues 添加值 \$</span><span class="sxs-lookup"><span data-stu-id="a0e78-172">How to add values to \$PSDefaultParameterValues</span></span>

<span data-ttu-id="a0e78-173">若要向添加值 `$PSDefaultParameterValues` ，请使用 **add** 方法。</span><span class="sxs-lookup"><span data-stu-id="a0e78-173">To add a value to `$PSDefaultParameterValues`, use the **Add** method.</span></span> <span data-ttu-id="a0e78-174">添加值并不会影响哈希表的现有值。</span><span class="sxs-lookup"><span data-stu-id="a0e78-174">Adding a value doesn't affect the hash table's existing values.</span></span>

<span data-ttu-id="a0e78-175">使用逗号 (`,`) 将 **键** 与 **值** 分隔开。</span><span class="sxs-lookup"><span data-stu-id="a0e78-175">Use a comma (`,`) to separate the **Key** from the **Value** .</span></span> <span data-ttu-id="a0e78-176">下面的语法演示如何对使用 **Add** 方法 `$PSDefaultParameterValues` 。</span><span class="sxs-lookup"><span data-stu-id="a0e78-176">The following syntax shows how to use the **Add** method for `$PSDefaultParameterValues`.</span></span>

```
PS> $PSDefaultParameterValues.Add("CmdletName:ParameterName", "DefaultValue")
```

<span data-ttu-id="a0e78-177">使用新的 **键/值** 对来更新在上一个示例中创建的哈希表。</span><span class="sxs-lookup"><span data-stu-id="a0e78-177">The hash table created in the prior example is updated with a new **Key/Value** pair.</span></span> <span data-ttu-id="a0e78-178">**Add** 方法将密钥设置 `Get-Process:Name` 为值 **PowerShell** 。</span><span class="sxs-lookup"><span data-stu-id="a0e78-178">The **Add** method sets the `Get-Process:Name` key to the value **PowerShell** .</span></span>

```powershell
$PSDefaultParameterValues.Add("Get-Process:Name", "PowerShell")
```

<span data-ttu-id="a0e78-179">下面的语法实现相同的结果。</span><span class="sxs-lookup"><span data-stu-id="a0e78-179">The following syntax accomplishes the same result.</span></span>

```powershell
$PSDefaultParameterValues["Get-Process:Name"]="PowerShell"
```

<span data-ttu-id="a0e78-180">`$PSDefaultParameterValues`变量显示已更新的哈希表。</span><span class="sxs-lookup"><span data-stu-id="a0e78-180">The `$PSDefaultParameterValues` variable displays the updated hash table.</span></span> <span data-ttu-id="a0e78-181">已 `Get-Process:Name` 添加密钥。</span><span class="sxs-lookup"><span data-stu-id="a0e78-181">The `Get-Process:Name` key was added.</span></span>

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-Process:Name               PowerShell
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    Server123
```

### <a name="how-to-remove-values-from-psdefaultparametervalues"></a><span data-ttu-id="a0e78-182">如何从 PSDefaultParameterValues 中删除值 \$</span><span class="sxs-lookup"><span data-stu-id="a0e78-182">How to remove values from \$PSDefaultParameterValues</span></span>

<span data-ttu-id="a0e78-183">若要从中删除值 `$PSDefaultParameterValues` ，请使用哈希表的 **remove** 方法。</span><span class="sxs-lookup"><span data-stu-id="a0e78-183">To remove a value from `$PSDefaultParameterValues`, use the **Remove** method of hash tables.</span></span> <span data-ttu-id="a0e78-184">删除值并不会影响哈希表的现有值。</span><span class="sxs-lookup"><span data-stu-id="a0e78-184">Removing a value doesn't affect the hash table's existing values.</span></span>

<span data-ttu-id="a0e78-185">下面的语法演示如何对使用 **Remove** 方法 `$PSDefaultParameterValues` 。</span><span class="sxs-lookup"><span data-stu-id="a0e78-185">The following syntax shows how to use the **Remove** method on `$PSDefaultParameterValues`.</span></span>

```
PS> $PSDefaultParameterValues.Remove("CmdletName:ParameterName")
```

<span data-ttu-id="a0e78-186">在此示例中，将更新在上一个示例中创建的哈希表，以删除 **键/值** 对。</span><span class="sxs-lookup"><span data-stu-id="a0e78-186">In this example, the hash table created in the prior example is updated to remove a **Key/Value** pair.</span></span> <span data-ttu-id="a0e78-187">**Remove** 方法删除该 `Get-Process:Name` 密钥。</span><span class="sxs-lookup"><span data-stu-id="a0e78-187">The **Remove** method removes the `Get-Process:Name` key.</span></span>

```powershell
$PSDefaultParameterValues.Remove("Get-Process:Name")
```

<span data-ttu-id="a0e78-188">`$PSDefaultParameterValues`变量显示已更新的哈希表。</span><span class="sxs-lookup"><span data-stu-id="a0e78-188">The `$PSDefaultParameterValues` variable displays the updated hash table.</span></span> <span data-ttu-id="a0e78-189">`Get-Process:Name`已删除该密钥。</span><span class="sxs-lookup"><span data-stu-id="a0e78-189">The `Get-Process:Name` key was removed.</span></span>

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    Server123
```

### <a name="how-to-change-values-in-psdefaultparametervalues"></a><span data-ttu-id="a0e78-190">如何更改 PSDefaultParameterValues 中的值 \$</span><span class="sxs-lookup"><span data-stu-id="a0e78-190">How to change values in \$PSDefaultParameterValues</span></span>

<span data-ttu-id="a0e78-191">对特定值所做的更改不会影响现有哈希表的值。</span><span class="sxs-lookup"><span data-stu-id="a0e78-191">Changes to a specific value don't affect existing hash table values.</span></span> <span data-ttu-id="a0e78-192">若要在中更改特定的 **键/值** 对 `$PSDefaultParameterValues` ，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="a0e78-192">To change a specific **Key/Value** pair in `$PSDefaultParameterValues`, use the following syntax:</span></span>

```
PS> $PSDefaultParameterValues["CmdletName:ParameterName"]="DefaultValue"
```

<span data-ttu-id="a0e78-193">在此示例中，将更新在上一个示例中创建的哈希表以更改 **键/值** 对。</span><span class="sxs-lookup"><span data-stu-id="a0e78-193">In this example, the hash table created in the prior example is updated to change a **Key/Value** pair.</span></span> <span data-ttu-id="a0e78-194">以下命令将键更改 `Send-MailMessage:SmtpServer` 为新值 **ServerXYZ** 。</span><span class="sxs-lookup"><span data-stu-id="a0e78-194">The following command changes the `Send-MailMessage:SmtpServer` key to a new value of **ServerXYZ** .</span></span>

```powershell
$PSDefaultParameterValues["Send-MailMessage:SmtpServer"]="ServerXYZ"
```

<span data-ttu-id="a0e78-195">`$PSDefaultParameterValues`变量显示已更新的哈希表。</span><span class="sxs-lookup"><span data-stu-id="a0e78-195">The `$PSDefaultParameterValues` variable displays the updated hash table.</span></span> <span data-ttu-id="a0e78-196">`Send-MailMessage:SmtpServer`该键已更改为新值。</span><span class="sxs-lookup"><span data-stu-id="a0e78-196">The `Send-MailMessage:SmtpServer` key was changed to a new value.</span></span>

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    ServerXYZ
```

### <a name="how-to-disable-and-re-enable-psdefaultparametervalues"></a><span data-ttu-id="a0e78-197">如何禁用和重新启用 \$ PSDefaultParameterValues</span><span class="sxs-lookup"><span data-stu-id="a0e78-197">How to disable and re-enable \$PSDefaultParameterValues</span></span>

<span data-ttu-id="a0e78-198">你可以暂时禁用然后重新启用 `$PSDefaultParameterValues` 。</span><span class="sxs-lookup"><span data-stu-id="a0e78-198">You can temporarily disable and then re-enable `$PSDefaultParameterValues`.</span></span>
<span data-ttu-id="a0e78-199">`$PSDefaultParameterValues`如果正在运行需要不同默认参数值的脚本，禁用会很有用。</span><span class="sxs-lookup"><span data-stu-id="a0e78-199">Disabling `$PSDefaultParameterValues` is useful if you're running scripts that need different default parameter values.</span></span>

<span data-ttu-id="a0e78-200">若要禁用 `$PSDefaultParameterValues` ，请添加 `Disabled` 值为 **True** 的的键。</span><span class="sxs-lookup"><span data-stu-id="a0e78-200">To disable `$PSDefaultParameterValues`, add a key of `Disabled` with a value of **True** .</span></span> <span data-ttu-id="a0e78-201">中的值 `$PSDefaultParameterValues` 将保留，但无效。</span><span class="sxs-lookup"><span data-stu-id="a0e78-201">The values in `$PSDefaultParameterValues` are preserved, but aren't effective.</span></span>

```
PS> $PSDefaultParameterValues.Add("Disabled", $True)
```

<span data-ttu-id="a0e78-202">下面的语法实现相同的结果。</span><span class="sxs-lookup"><span data-stu-id="a0e78-202">The following syntax accomplishes the same result.</span></span>

```
PS> $PSDefaultParameterValues["Disabled"]=$True
```

<span data-ttu-id="a0e78-203">`$PSDefaultParameterValues`变量显示已更新的哈希表，其中包含键的值 `Disabled` 。</span><span class="sxs-lookup"><span data-stu-id="a0e78-203">The `$PSDefaultParameterValues` variable displays the updated hash table with the value for the `Disabled` key.</span></span>

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Disabled                       True
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    ServerXYZ
```

<span data-ttu-id="a0e78-204">若要重新启用 `$PSDefaultParameterValues` ，请删除 **禁用** 的密钥，或将 **禁用** 的项的值更改为 `$False` 。</span><span class="sxs-lookup"><span data-stu-id="a0e78-204">To re-enable `$PSDefaultParameterValues`, remove the **Disabled** key or change the value of the **Disabled** key to `$False`.</span></span> <span data-ttu-id="a0e78-205">以前的值 `$PSDefaultParameterValues` 再次生效。</span><span class="sxs-lookup"><span data-stu-id="a0e78-205">The previous value of `$PSDefaultParameterValues` is effective again.</span></span>

```
PS> $PSDefaultParameterValues.Remove("Disabled")
```

<span data-ttu-id="a0e78-206">下面的语法实现相同的结果。</span><span class="sxs-lookup"><span data-stu-id="a0e78-206">The following syntax accomplishes the same result.</span></span>

```
PS> $PSDefaultParameterValues["Disabled"]=$False
```

<span data-ttu-id="a0e78-207">`$PSDefaultParameterValues`变量显示已更新的哈希表。</span><span class="sxs-lookup"><span data-stu-id="a0e78-207">The `$PSDefaultParameterValues` variable displays the updated hash table.</span></span> <span data-ttu-id="a0e78-208">使用 **Remove** 方法时， `Disabled` 会从输出中删除该密钥。</span><span class="sxs-lookup"><span data-stu-id="a0e78-208">When the **Remove** method is used, the `Disabled` key is removed from the output.</span></span>
<span data-ttu-id="a0e78-209">如果使用了替代语法重新启用 `$PSDefaultParameterValues` ，则 `Disabled` 键显示为 **False** 。</span><span class="sxs-lookup"><span data-stu-id="a0e78-209">If the alternate syntax was used to re-enable `$PSDefaultParameterValues`, the `Disabled` key is displayed as **False** .</span></span>

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Disabled                       False
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    ServerXYZ
```

## <a name="see-also"></a><span data-ttu-id="a0e78-210">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0e78-210">See also</span></span>

[<span data-ttu-id="a0e78-211">about_CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a0e78-211">about_CommonParameters</span></span>](https://go.microsoft.com/fwlink/?LinkID=113216)

[<span data-ttu-id="a0e78-212">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="a0e78-212">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="a0e78-213">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="a0e78-213">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="a0e78-214">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="a0e78-214">about_Hash_Tables</span></span>](about_Hash_Tables.md)

[<span data-ttu-id="a0e78-215">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="a0e78-215">about_Preference_Variables</span></span>](about_Preference_Variables.md)

[<span data-ttu-id="a0e78-216">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="a0e78-216">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="a0e78-217">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="a0e78-217">about_Script_Blocks</span></span>](about_Script_Blocks.md)
