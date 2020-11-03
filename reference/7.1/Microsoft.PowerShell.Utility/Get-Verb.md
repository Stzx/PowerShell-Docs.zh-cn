---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/07/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-verb?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Verb
ms.openlocfilehash: 27434dfbc76d26724b34fe19fd143a7c52a14e90
ms.sourcegitcommit: 7d052985c20761fdf4c6d7ce4e04df4c551c36a3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/11/2020
ms.locfileid: "93199310"
---
# <span data-ttu-id="bfb29-103">Get-Verb</span><span class="sxs-lookup"><span data-stu-id="bfb29-103">Get-Verb</span></span>

## <span data-ttu-id="bfb29-104">摘要</span><span class="sxs-lookup"><span data-stu-id="bfb29-104">SYNOPSIS</span></span>
<span data-ttu-id="bfb29-105">获取已批准的 PowerShell 谓词。</span><span class="sxs-lookup"><span data-stu-id="bfb29-105">Gets approved PowerShell verbs.</span></span>

## <span data-ttu-id="bfb29-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bfb29-106">SYNTAX</span></span>

```
Get-Verb [[-Verb] <String[]>] [[-Group] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="bfb29-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bfb29-107">DESCRIPTION</span></span>

<span data-ttu-id="bfb29-108">`Get-Verb`函数获取已批准在 PowerShell 命令中使用的谓词。</span><span class="sxs-lookup"><span data-stu-id="bfb29-108">The `Get-Verb` function gets verbs that are approved for use in PowerShell commands.</span></span>

<span data-ttu-id="bfb29-109">建议 PowerShell cmdlet 和函数名称采用 `Verb-Noun` 格式，并包含已批准的谓词。</span><span class="sxs-lookup"><span data-stu-id="bfb29-109">It is recommended that PowerShell cmdlet and function names have the `Verb-Noun` format and include an approved verb.</span></span> <span data-ttu-id="bfb29-110">这种做法使命令名称更一致、可预测且更易于使用。</span><span class="sxs-lookup"><span data-stu-id="bfb29-110">This practice makes command names more consistent, predictable, and easier to use.</span></span>

<span data-ttu-id="bfb29-111">使用未经批准的谓词的命令仍在 PowerShell 中运行。</span><span class="sxs-lookup"><span data-stu-id="bfb29-111">Commands that use unapproved verbs, still run in PowerShell.</span></span> <span data-ttu-id="bfb29-112">但是，当导入的模块的名称中包含未批准的谓词的命令时，该 `Import-Module` 命令将显示一条警告消息。</span><span class="sxs-lookup"><span data-stu-id="bfb29-112">However, when you import a module that includes a command with an unapproved verb in its name, the `Import-Module` command displays a warning message.</span></span>

> [!NOTE]
> <span data-ttu-id="bfb29-113">返回的谓词列表 `Get-Verb` 可能不完整。</span><span class="sxs-lookup"><span data-stu-id="bfb29-113">The verb list that `Get-Verb` returns might not be complete.</span></span> <span data-ttu-id="bfb29-114">有关包含说明的已批准 PowerShell 动词的更新列表，请参阅 Microsoft Docs 中的 [批准的动词](../../docs-conceptual/developer/cmdlet/approved-verbs-for-windows-powershell-commands.md) 。</span><span class="sxs-lookup"><span data-stu-id="bfb29-114">For an updated list of approved PowerShell verbs with descriptions, see [Approved Verbs](../../docs-conceptual/developer/cmdlet/approved-verbs-for-windows-powershell-commands.md) in the Microsoft Docs.</span></span>

## <span data-ttu-id="bfb29-115">示例</span><span class="sxs-lookup"><span data-stu-id="bfb29-115">Examples</span></span>

### <span data-ttu-id="bfb29-116">示例 1-获取所有谓词的列表</span><span class="sxs-lookup"><span data-stu-id="bfb29-116">Example 1 - Get a list of all verbs</span></span>

```powershell
Get-Verb
```

### <span data-ttu-id="bfb29-117">示例 2-获取以 "un" 开头的已批准谓词的列表</span><span class="sxs-lookup"><span data-stu-id="bfb29-117">Example 2 - Get a list of approved verbs that begin with "un"</span></span>

```powershell
Get-Verb un*
```

```Output
Verb       AliasPrefix Group     Description
----       ----------- -----     -----------
Undo       un          Common    Sets a resource to its previous state
Unlock     uk          Common    Releases a resource that was locked
Unpublish  ub          Data      Makes a resource unavailable to others
Uninstall  us          Lifecycle Removes a resource from an indicated location
Unregister ur          Lifecycle Removes the entry for a resource from a repository
Unblock    ul          Security  Removes restrictions to a resource
Unprotect  up          Security  Removes safeguards from a resource that were added to prevent it from attack or loss
```

### <span data-ttu-id="bfb29-118">示例 3-获取安全组中所有已批准的谓词</span><span class="sxs-lookup"><span data-stu-id="bfb29-118">Example 3 - Get all approved verbs in the Security group</span></span>

```powershell
Get-Verb -Group Security
```

```Output
Verb      AliasPrefix Group    Description
----      ----------- -----    -----------
Block     bl          Security Restricts access to a resource
Grant     gr          Security Allows access to a resource
Protect   pt          Security Safeguards a resource from attack or loss
Revoke    rk          Security Specifies an action that does not allow access to a resource
Unblock   ul          Security Removes restrictions to a resource
Unprotect up          Security Removes safeguards from a resource that were added to prevent it from attack or loss
```

### <span data-ttu-id="bfb29-119">示例 4-查找模块中具有未经批准的谓词的所有命令</span><span class="sxs-lookup"><span data-stu-id="bfb29-119">Example 4 - Finds all commands in a module that have unapproved verbs</span></span>

```powershell
Get-Command -Module Microsoft.PowerShell.Utility | Where-Object Verb -NotIn (Get-Verb).Verb
```

```Output
CommandType     Name            Version    Source
-----------     ----            -------    ------
Cmdlet          Sort-Object     3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Tee-Object      3.1.0.0    Microsoft.PowerShell.Utility
```

## <span data-ttu-id="bfb29-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bfb29-120">PARAMETERS</span></span>

### <span data-ttu-id="bfb29-121">-Verb</span><span class="sxs-lookup"><span data-stu-id="bfb29-121">-Verb</span></span>

<span data-ttu-id="bfb29-122">仅获取指定的谓词。</span><span class="sxs-lookup"><span data-stu-id="bfb29-122">Gets only the specified verbs.</span></span> <span data-ttu-id="bfb29-123">输入谓词的名称或名称模式。</span><span class="sxs-lookup"><span data-stu-id="bfb29-123">Enter the name of a verb or a name pattern.</span></span> <span data-ttu-id="bfb29-124">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="bfb29-124">Wildcards are allowed.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Common, Communications, Data, Diagnostic, Lifecycle, Other, Security

Required: False
Position: 1
Default value: All groups
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="bfb29-125">-Group</span><span class="sxs-lookup"><span data-stu-id="bfb29-125">-Group</span></span>

<span data-ttu-id="bfb29-126">仅获取指定的组。</span><span class="sxs-lookup"><span data-stu-id="bfb29-126">Gets only the specified groups.</span></span> <span data-ttu-id="bfb29-127">输入组的名称。</span><span class="sxs-lookup"><span data-stu-id="bfb29-127">Enter the name of a group.</span></span> <span data-ttu-id="bfb29-128">不允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="bfb29-128">Wildcards are not allowed.</span></span>

<span data-ttu-id="bfb29-129">此参数是在 PowerShell 6.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="bfb29-129">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: All verbs
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="bfb29-130">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="bfb29-130">CommonParameters</span></span>

<span data-ttu-id="bfb29-131">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="bfb29-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bfb29-132">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="bfb29-132">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bfb29-133">输入</span><span class="sxs-lookup"><span data-stu-id="bfb29-133">INPUTS</span></span>

### <span data-ttu-id="bfb29-134">无</span><span class="sxs-lookup"><span data-stu-id="bfb29-134">None</span></span>

## <span data-ttu-id="bfb29-135">输出</span><span class="sxs-lookup"><span data-stu-id="bfb29-135">OUTPUTS</span></span>

### <span data-ttu-id="bfb29-136">System.web. VerbInfo</span><span class="sxs-lookup"><span data-stu-id="bfb29-136">System.Management.Automation.VerbInfo</span></span>

## <span data-ttu-id="bfb29-137">注释</span><span class="sxs-lookup"><span data-stu-id="bfb29-137">NOTES</span></span>

<span data-ttu-id="bfb29-138">根据最常见的用途，将 PowerShell 谓词分配给某个组。</span><span class="sxs-lookup"><span data-stu-id="bfb29-138">PowerShell verbs are assigned to a group based on their most common use.</span></span> <span data-ttu-id="bfb29-139">谓词组旨在简化谓词的查找和比较，而不会限制谓词的使用。</span><span class="sxs-lookup"><span data-stu-id="bfb29-139">The groups are designed to make the verbs easy to find and compare, not to restrict their use.</span></span> <span data-ttu-id="bfb29-140">对于任意类型的命令，均可使用任何批准的谓词。</span><span class="sxs-lookup"><span data-stu-id="bfb29-140">You can use any approved verb for any type of command.</span></span>

<span data-ttu-id="bfb29-141">每个 PowerShell 谓词分配给以下组之一。</span><span class="sxs-lookup"><span data-stu-id="bfb29-141">Each PowerShell verb is assigned to one of the following groups.</span></span>

- <span data-ttu-id="bfb29-142">常见：定义可应用于几乎任何 cmdlet 的常规操作，例如 Add。</span><span class="sxs-lookup"><span data-stu-id="bfb29-142">Common: Define generic actions that can apply to almost any cmdlet, such as Add.</span></span>
- <span data-ttu-id="bfb29-143">通信：定义适用于通信的操作，例如 "连接"。</span><span class="sxs-lookup"><span data-stu-id="bfb29-143">Communications: Define actions that apply to communications, such as Connect.</span></span>
- <span data-ttu-id="bfb29-144">数据：定义适用于数据处理的操作，例如备份。</span><span class="sxs-lookup"><span data-stu-id="bfb29-144">Data: Define actions that apply to data handling, such as Backup.</span></span>
- <span data-ttu-id="bfb29-145">诊断：定义适用于诊断的操作，例如 "调试"。</span><span class="sxs-lookup"><span data-stu-id="bfb29-145">Diagnostic: Define actions that apply to diagnostics, such as Debug.</span></span>
- <span data-ttu-id="bfb29-146">生命周期：定义适用于 cmdlet 生命周期的操作，如 "完成"。</span><span class="sxs-lookup"><span data-stu-id="bfb29-146">Lifecycle: Define actions that apply to the lifecycle of a cmdlet, such as Complete.</span></span>
- <span data-ttu-id="bfb29-147">安全性：定义适用于安全的操作，例如 Revoke。</span><span class="sxs-lookup"><span data-stu-id="bfb29-147">Security: Define actions that apply to security, such as Revoke.</span></span>
- <span data-ttu-id="bfb29-148">其他：定义其他类型的操作。</span><span class="sxs-lookup"><span data-stu-id="bfb29-148">Other: Define other types of actions.</span></span>

<span data-ttu-id="bfb29-149">与 PowerShell 一起安装的一些 cmdlet （例如 `Tee-Object` 和 `Where-Object` ）使用未经批准的谓词。</span><span class="sxs-lookup"><span data-stu-id="bfb29-149">Some of the cmdlets that are installed with PowerShell, such as `Tee-Object` and `Where-Object`, use unapproved verbs.</span></span> <span data-ttu-id="bfb29-150">这些 cmdlet 是历史例外，它们的动词归类为 **reserved** 。</span><span class="sxs-lookup"><span data-stu-id="bfb29-150">These cmdlets are historic exceptions and their verbs are classified as **reserved** .</span></span>

## <span data-ttu-id="bfb29-151">相关链接</span><span class="sxs-lookup"><span data-stu-id="bfb29-151">RELATED LINKS</span></span>

[<span data-ttu-id="bfb29-152">Import-Module</span><span class="sxs-lookup"><span data-stu-id="bfb29-152">Import-Module</span></span>](../microsoft.powershell.core/import-module.md)

