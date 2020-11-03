---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
ms.date: 09/07/2018
Module Name: Microsoft.PowerShell.Core
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/functions/get-verb?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Verb
ms.openlocfilehash: 4474bb50c2bf3be10e72d2554190208e956f9040
ms.sourcegitcommit: 7d052985c20761fdf4c6d7ce4e04df4c551c36a3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/11/2020
ms.locfileid: "93199304"
---
# <span data-ttu-id="0fa78-103">Get-Verb</span><span class="sxs-lookup"><span data-stu-id="0fa78-103">Get-Verb</span></span>

## <span data-ttu-id="0fa78-104">摘要</span><span class="sxs-lookup"><span data-stu-id="0fa78-104">SYNOPSIS</span></span>
<span data-ttu-id="0fa78-105">获取已批准的 PowerShell 谓词。</span><span class="sxs-lookup"><span data-stu-id="0fa78-105">Gets approved PowerShell verbs.</span></span>

## <span data-ttu-id="0fa78-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0fa78-106">SYNTAX</span></span>

```
Get-Verb [[-verb] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="0fa78-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0fa78-107">DESCRIPTION</span></span>

<span data-ttu-id="0fa78-108">`Get-Verb`函数获取已批准在 PowerShell 命令中使用的谓词。</span><span class="sxs-lookup"><span data-stu-id="0fa78-108">The `Get-Verb` function gets verbs that are approved for use in PowerShell commands.</span></span>

<span data-ttu-id="0fa78-109">PowerShell 建议 cmdlet 和函数名称采用 Verb-Noun 格式，并包含已批准的谓词。</span><span class="sxs-lookup"><span data-stu-id="0fa78-109">PowerShell recommends cmdlet and function names have the Verb-Noun format and include an approved verb.</span></span> <span data-ttu-id="0fa78-110">这种做法使命令名称更一致、可预测且更易于使用。</span><span class="sxs-lookup"><span data-stu-id="0fa78-110">This practice makes command names more consistent, predictable, and easier to use.</span></span>

<span data-ttu-id="0fa78-111">使用未经批准的谓词的命令在 PowerShell 中运行。</span><span class="sxs-lookup"><span data-stu-id="0fa78-111">Commands that use unapproved verbs run in PowerShell.</span></span> <span data-ttu-id="0fa78-112">但是，当导入的模块的名称中包含未批准的谓词的命令时，该 `Import-Module` 命令将显示一条警告消息。</span><span class="sxs-lookup"><span data-stu-id="0fa78-112">However, when you import a module that includes a command with an unapproved verb in its name, the `Import-Module` command displays a warning message.</span></span>

> [!NOTE]
> <span data-ttu-id="0fa78-113">返回的谓词列表 `Get-Verb` 可能不完整。</span><span class="sxs-lookup"><span data-stu-id="0fa78-113">The verb list that `Get-Verb` returns might not be complete.</span></span> <span data-ttu-id="0fa78-114">有关包含说明的已批准 PowerShell 动词的更新列表，请参阅 Microsoft Docs 中的 [批准的动词](../../docs-conceptual/developer/cmdlet/approved-verbs-for-windows-powershell-commands.md) 。</span><span class="sxs-lookup"><span data-stu-id="0fa78-114">For an updated list of approved PowerShell verbs with descriptions, see [Approved Verbs](../../docs-conceptual/developer/cmdlet/approved-verbs-for-windows-powershell-commands.md) in the Microsoft Docs.</span></span>

## <span data-ttu-id="0fa78-115">示例</span><span class="sxs-lookup"><span data-stu-id="0fa78-115">EXAMPLES</span></span>

### <span data-ttu-id="0fa78-116">示例 1-获取所有谓词的列表</span><span class="sxs-lookup"><span data-stu-id="0fa78-116">Example 1 - Get a list of all verbs</span></span>

```powershell
Get-Verb
```

### <span data-ttu-id="0fa78-117">示例 2-获取以 "un" 开头的已批准谓词的列表</span><span class="sxs-lookup"><span data-stu-id="0fa78-117">Example 2 - Get a list of approved verbs that begin with "un"</span></span>

```powershell
Get-Verb un*
```

```Output
Verb                 Group
----                 -----
Undo                 Common
Unlock               Common
Unpublish            Data
Uninstall            Lifecycle
Unregister           Lifecycle
Unblock              Security
Unprotect            Security
```

### <span data-ttu-id="0fa78-118">示例 3-获取安全组中所有已批准的谓词</span><span class="sxs-lookup"><span data-stu-id="0fa78-118">Example 3 - Get all approved verbs in the Security group</span></span>

```powershell
Get-Verb | Where-Object Group -EQ Security
```

```Output
Verb      Group
----      -----
Block     Security
Grant     Security
Protect   Security
Revoke    Security
Unblock   Security
Unprotect Security
```

### <span data-ttu-id="0fa78-119">示例 4-查找模块中具有未经批准的谓词的所有命令</span><span class="sxs-lookup"><span data-stu-id="0fa78-119">Example 4 - Finds all commands in a module that have unapproved verbs</span></span>

```powershell
Get-Command -Module Microsoft.PowerShell.Utility | Where-Object Verb -NotIn (Get-Verb).Verb
```

```Output
CommandType     Name            Version    Source
-----------     ----            -------    ------
Cmdlet          Sort-Object     3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Tee-Object      3.1.0.0    Microsoft.PowerShell.Utility
```

## <span data-ttu-id="0fa78-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0fa78-120">PARAMETERS</span></span>

### <span data-ttu-id="0fa78-121">-verb</span><span class="sxs-lookup"><span data-stu-id="0fa78-121">-verb</span></span>

<span data-ttu-id="0fa78-122">仅获取指定的谓词。</span><span class="sxs-lookup"><span data-stu-id="0fa78-122">Gets only the specified verbs.</span></span>
<span data-ttu-id="0fa78-123">输入谓词的名称或名称模式。</span><span class="sxs-lookup"><span data-stu-id="0fa78-123">Enter the name of a verb or a name pattern.</span></span>
<span data-ttu-id="0fa78-124">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="0fa78-124">Wildcards are allowed.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: All verbs
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

## <span data-ttu-id="0fa78-125">输入</span><span class="sxs-lookup"><span data-stu-id="0fa78-125">INPUTS</span></span>

### <span data-ttu-id="0fa78-126">无</span><span class="sxs-lookup"><span data-stu-id="0fa78-126">None</span></span>

## <span data-ttu-id="0fa78-127">输出</span><span class="sxs-lookup"><span data-stu-id="0fa78-127">OUTPUTS</span></span>

### <span data-ttu-id="0fa78-128">Selected.Microsoft.PowerShell.Commands.MemberDefinition</span><span class="sxs-lookup"><span data-stu-id="0fa78-128">Selected.Microsoft.PowerShell.Commands.MemberDefinition</span></span>

## <span data-ttu-id="0fa78-129">注释</span><span class="sxs-lookup"><span data-stu-id="0fa78-129">NOTES</span></span>

<span data-ttu-id="0fa78-130">`Get-Verb` 返回 MemberDefinition 对象的已修改版本。</span><span class="sxs-lookup"><span data-stu-id="0fa78-130">`Get-Verb` returns a modified version of a Microsoft.PowerShell.Commands.MemberDefinition object.</span></span>
<span data-ttu-id="0fa78-131">该对象不具有 MemberDefinition 对象的标准属性。</span><span class="sxs-lookup"><span data-stu-id="0fa78-131">The object does not have the standard properties of a MemberDefinition object.</span></span> <span data-ttu-id="0fa78-132">而是具有 Verb 和 Group 属性。</span><span class="sxs-lookup"><span data-stu-id="0fa78-132">Instead it has Verb and Group properties.</span></span> <span data-ttu-id="0fa78-133">Verb 属性包含带有谓词名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="0fa78-133">The Verb property contains a string with the verb name.</span></span> <span data-ttu-id="0fa78-134">Group 属性包含带有谓词组的字符串。</span><span class="sxs-lookup"><span data-stu-id="0fa78-134">The Group property contains a string with the verb group.</span></span>

<span data-ttu-id="0fa78-135">根据最常见的用途，将 PowerShell 谓词分配给某个组。</span><span class="sxs-lookup"><span data-stu-id="0fa78-135">PowerShell verbs are assigned to a group based on their most common use.</span></span> <span data-ttu-id="0fa78-136">谓词组旨在简化谓词的查找和比较，而不会限制谓词的使用。</span><span class="sxs-lookup"><span data-stu-id="0fa78-136">The groups are designed to make the verbs easy to find and compare, not to restrict their use.</span></span> <span data-ttu-id="0fa78-137">对于任意类型的命令，均可使用任何批准的谓词。</span><span class="sxs-lookup"><span data-stu-id="0fa78-137">You can use any approved verb for any type of command.</span></span>

<span data-ttu-id="0fa78-138">每个 PowerShell 谓词分配给以下组之一。</span><span class="sxs-lookup"><span data-stu-id="0fa78-138">Each PowerShell verb is assigned to one of the following groups.</span></span>

- <span data-ttu-id="0fa78-139">常见：定义可应用于几乎任何 cmdlet 的常规操作，例如 Add。</span><span class="sxs-lookup"><span data-stu-id="0fa78-139">Common: Define generic actions that can apply to almost any cmdlet, such as Add.</span></span>
- <span data-ttu-id="0fa78-140">通信：定义适用于通信的操作，例如 "连接"。</span><span class="sxs-lookup"><span data-stu-id="0fa78-140">Communications:  Define actions that apply to communications, such as Connect.</span></span>
- <span data-ttu-id="0fa78-141">数据：定义适用于数据处理的操作，例如备份。</span><span class="sxs-lookup"><span data-stu-id="0fa78-141">Data:  Define actions that apply to data handling, such as Backup.</span></span>
- <span data-ttu-id="0fa78-142">诊断：定义适用于诊断的操作，例如 "调试"。</span><span class="sxs-lookup"><span data-stu-id="0fa78-142">Diagnostic: Define actions that apply to diagnostics, such as Debug.</span></span>
- <span data-ttu-id="0fa78-143">生命周期：定义适用于 cmdlet 生命周期的操作，如 "完成"。</span><span class="sxs-lookup"><span data-stu-id="0fa78-143">Lifecycle: Define actions that apply to the lifecycle of a cmdlet, such as Complete.</span></span>
- <span data-ttu-id="0fa78-144">安全性：定义适用于安全的操作，例如 Revoke。</span><span class="sxs-lookup"><span data-stu-id="0fa78-144">Security: Define actions that apply to security, such as Revoke.</span></span>
- <span data-ttu-id="0fa78-145">其他：定义其他类型的操作。</span><span class="sxs-lookup"><span data-stu-id="0fa78-145">Other: Define other types of actions.</span></span>

<span data-ttu-id="0fa78-146">与 PowerShell 一起安装的一些 cmdlet （例如 `Tee-Object` 和 `Where-Object` ）使用未经批准的谓词。</span><span class="sxs-lookup"><span data-stu-id="0fa78-146">Some of the cmdlets that are installed with PowerShell, such as `Tee-Object` and `Where-Object`, use unapproved verbs.</span></span> <span data-ttu-id="0fa78-147">这些 cmdlet 是历史例外，它们的动词归类为 **reserved** 。</span><span class="sxs-lookup"><span data-stu-id="0fa78-147">These cmdlets are historic exceptions and their verbs are classified as **reserved** .</span></span>

## <span data-ttu-id="0fa78-148">相关链接</span><span class="sxs-lookup"><span data-stu-id="0fa78-148">RELATED LINKS</span></span>

[<span data-ttu-id="0fa78-149">Import-Module</span><span class="sxs-lookup"><span data-stu-id="0fa78-149">Import-Module</span></span>](import-module.md)
