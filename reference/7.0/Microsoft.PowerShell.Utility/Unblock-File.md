---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unblock-File
ms.openlocfilehash: 353469a02a1580df6c9b238ca8db4ddb46cd18f1
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2020
ms.locfileid: "93197275"
---
# <span data-ttu-id="db4c5-103">Unblock-File</span><span class="sxs-lookup"><span data-stu-id="db4c5-103">Unblock-File</span></span>

## <span data-ttu-id="db4c5-104">摘要</span><span class="sxs-lookup"><span data-stu-id="db4c5-104">SYNOPSIS</span></span>
<span data-ttu-id="db4c5-105">取消阻止已从 Internet 下载的文件。</span><span class="sxs-lookup"><span data-stu-id="db4c5-105">Unblocks files that were downloaded from the Internet.</span></span>

## <span data-ttu-id="db4c5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="db4c5-106">SYNTAX</span></span>

### <span data-ttu-id="db4c5-107">ByPath（默认值）</span><span class="sxs-lookup"><span data-stu-id="db4c5-107">ByPath (Default)</span></span>

```
Unblock-File [-Path] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="db4c5-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="db4c5-108">ByLiteralPath</span></span>

```
Unblock-File -LiteralPath <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="db4c5-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="db4c5-109">DESCRIPTION</span></span>

<span data-ttu-id="db4c5-110">**Unblock-File** cmdlet 允许你打开已从 Internet 下载的文件。</span><span class="sxs-lookup"><span data-stu-id="db4c5-110">The **Unblock-File** cmdlet lets you open files that were downloaded from the Internet.</span></span>
<span data-ttu-id="db4c5-111">它取消阻止从 Internet 下载的 PowerShell 脚本文件，以便你可以运行这些文件，即使 PowerShell 执行策略是 **RemoteSigned** 也是如此。</span><span class="sxs-lookup"><span data-stu-id="db4c5-111">It unblocks PowerShell script files that were downloaded from the Internet so you can run them, even when the PowerShell execution policy is **RemoteSigned** .</span></span>
<span data-ttu-id="db4c5-112">默认情况下，将阻止这些文件以保护计算机免受不受信任的文件的威胁。</span><span class="sxs-lookup"><span data-stu-id="db4c5-112">By default, these files are blocked to protect the computer from untrusted files.</span></span>

<span data-ttu-id="db4c5-113">在使用 **Unblock-File** cmdlet 之前，请查看该文件及其来源，并验证是否可以安全打开它。</span><span class="sxs-lookup"><span data-stu-id="db4c5-113">Before using the **Unblock-File** cmdlet, review the file and its source and verify that it is safe to open.</span></span>

<span data-ttu-id="db4c5-114">在内部， **Unblock-File** cmdlet 可删除 Zone.Identifier 备用数据流，该数据流的值为“3”，以指示它是从 Internet 下载的。</span><span class="sxs-lookup"><span data-stu-id="db4c5-114">Internally, the **Unblock-File** cmdlet removes the Zone.Identifier alternate data stream, which has a value of "3" to indicate that it was downloaded from the Internet.</span></span>

<span data-ttu-id="db4c5-115">有关 PowerShell 执行策略的详细信息，请参阅 [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md)。</span><span class="sxs-lookup"><span data-stu-id="db4c5-115">For more information about PowerShell execution policies, see [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span></span>

<span data-ttu-id="db4c5-116">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="db4c5-116">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="db4c5-117">示例</span><span class="sxs-lookup"><span data-stu-id="db4c5-117">EXAMPLES</span></span>

### <span data-ttu-id="db4c5-118">示例 1：取消阻止一个文件</span><span class="sxs-lookup"><span data-stu-id="db4c5-118">Example 1: Unblock a file</span></span>

```
PS C:\> Unblock-File -Path C:\Users\User01\Documents\Downloads\PowerShellTips.chm
```

<span data-ttu-id="db4c5-119">此命令将取消阻止 PowerShellTips.chm 文件。</span><span class="sxs-lookup"><span data-stu-id="db4c5-119">This command unblocks the PowerShellTips.chm file.</span></span>

### <span data-ttu-id="db4c5-120">示例 2：取消阻止多个文件</span><span class="sxs-lookup"><span data-stu-id="db4c5-120">Example 2: Unblock multiple files</span></span>

```
PS C:\> dir C:\Downloads\*PowerShell* | Unblock-File
```

<span data-ttu-id="db4c5-121">此命令将取消阻止 C:\Downloads 目录中名称包含“PowerShell”的所有文件。</span><span class="sxs-lookup"><span data-stu-id="db4c5-121">This command unblocks all of the files in the C:\Downloads directory whose names include "PowerShell".</span></span>
<span data-ttu-id="db4c5-122">在你已验证所有文件都安全之前，不要运行类似此命令的命令。</span><span class="sxs-lookup"><span data-stu-id="db4c5-122">Do not run a command like this one until you have verified that all files are safe.</span></span>

### <span data-ttu-id="db4c5-123">示例 3：查找和取消阻止脚本</span><span class="sxs-lookup"><span data-stu-id="db4c5-123">Example 3: Find and unblock scripts</span></span>

```
The first command uses the *Stream* parameter of the Get-Item cmdlet get files with the Zone.Identifier stream.Although you could pipe the output directly to the **Unblock-File** cmdlet (Get-Item * -Stream "Zone.Identifier" -ErrorAction SilentlyContinue | ForEach {Unblock-File $_.FileName}), it is prudent to review the file and confirm that it is safe before unblocking.
PS C:\> Get-Item * -Stream "Zone.Identifier" -ErrorAction SilentlyContinue
   FileName: C:\ps-test\Start-ActivityTracker.ps1

Stream                   Length
------                   ------
Zone.Identifier              26

The second command shows what happens when you run a blocked script in a PowerShell session in which the execution policy is **RemoteSigned**. The RemoteSigned policy prevents you from running scripts that are downloaded from the Internet unless they are digitally signed.
PS C:\> C:\ps-test\Start-ActivityTracker.ps1
c:\ps-test\Start-ActivityTracker.ps1 : File c:\ps-test\Start-ActivityTracker.ps1 cannot
be loaded. The file c:\ps-test\Start-ActivityTracker.ps1 is not digitally signed. The script
will not execute on the system. For more information, see about_Execution_Policies.

At line:1 char:1
+ c:\ps-test\Start-ActivityTracker.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : SecurityError: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess

The third command uses the **Unblock-File** cmdlet to unblock the script so it can run in the session.
PS C:\> Get-Item C:\ps-test\Start-ActivityTracker.ps1 | Unblock-File
```

<span data-ttu-id="db4c5-124">此命令显示了如何查找和取消阻止 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="db4c5-124">This command shows how to find and unblock PowerShell scripts.</span></span>

## <span data-ttu-id="db4c5-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="db4c5-125">PARAMETERS</span></span>

### <span data-ttu-id="db4c5-126">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="db4c5-126">-LiteralPath</span></span>
<span data-ttu-id="db4c5-127">指定要取消阻止的文件。</span><span class="sxs-lookup"><span data-stu-id="db4c5-127">Specifies the files to unblock.</span></span>
<span data-ttu-id="db4c5-128">与 *Path* 不同， *LiteralPath* 参数的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="db4c5-128">Unlike *Path* , the value of the *LiteralPath* parameter is used exactly as it is typed.</span></span>
<span data-ttu-id="db4c5-129">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="db4c5-129">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="db4c5-130">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="db4c5-130">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="db4c5-131">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="db4c5-131">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="db4c5-132">-Path</span><span class="sxs-lookup"><span data-stu-id="db4c5-132">-Path</span></span>
<span data-ttu-id="db4c5-133">指定要取消阻止的文件。</span><span class="sxs-lookup"><span data-stu-id="db4c5-133">Specifies the files to unblock.</span></span>
<span data-ttu-id="db4c5-134">支持使用通配符。</span><span class="sxs-lookup"><span data-stu-id="db4c5-134">Wildcard characters are supported.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="db4c5-135">-Confirm</span><span class="sxs-lookup"><span data-stu-id="db4c5-135">-Confirm</span></span>

<span data-ttu-id="db4c5-136">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="db4c5-136">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="db4c5-137">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="db4c5-137">-WhatIf</span></span>

<span data-ttu-id="db4c5-138">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="db4c5-138">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="db4c5-139">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="db4c5-139">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="db4c5-140">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="db4c5-140">CommonParameters</span></span>

<span data-ttu-id="db4c5-141">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="db4c5-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="db4c5-142">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="db4c5-142">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="db4c5-143">输入</span><span class="sxs-lookup"><span data-stu-id="db4c5-143">INPUTS</span></span>

### <span data-ttu-id="db4c5-144">System.String</span><span class="sxs-lookup"><span data-stu-id="db4c5-144">System.String</span></span>

<span data-ttu-id="db4c5-145">可以通过管道将文件路径传递给 **Unblock-File** 。</span><span class="sxs-lookup"><span data-stu-id="db4c5-145">You can pipe a file path to **Unblock-File** .</span></span>

## <span data-ttu-id="db4c5-146">输出</span><span class="sxs-lookup"><span data-stu-id="db4c5-146">OUTPUTS</span></span>

### <span data-ttu-id="db4c5-147">无</span><span class="sxs-lookup"><span data-stu-id="db4c5-147">None</span></span>

<span data-ttu-id="db4c5-148">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="db4c5-148">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="db4c5-149">注释</span><span class="sxs-lookup"><span data-stu-id="db4c5-149">NOTES</span></span>

- <span data-ttu-id="db4c5-150">PowerShell 7 中增加了对 macOS 的支持。</span><span class="sxs-lookup"><span data-stu-id="db4c5-150">Support for macOS was added in PowerShell 7.</span></span>
- <span data-ttu-id="db4c5-151">此 `Unblock-File` cmdlet 仅适用于文件系统驱动器。</span><span class="sxs-lookup"><span data-stu-id="db4c5-151">The `Unblock-File` cmdlet works only in file system drives.</span></span>
- <span data-ttu-id="db4c5-152">`Unblock-File`执行与文件资源管理器的 " **属性** " 对话框中的 " **解除阻止** " 按钮相同的操作。</span><span class="sxs-lookup"><span data-stu-id="db4c5-152">`Unblock-File` performs the same operation as the **Unblock** button on the **Properties** dialog box in File Explorer.</span></span>
- <span data-ttu-id="db4c5-153">如果在 `Unblock-File` 未被阻止的文件上使用 cmdlet，则该命令对未阻止的文件无效，并且该 cmdlet 不会生成错误。</span><span class="sxs-lookup"><span data-stu-id="db4c5-153">If you use the `Unblock-File` cmdlet on a file that is not blocked, the command has no effect on the unblocked file and the cmdlet does not generate errors.</span></span>

## <span data-ttu-id="db4c5-154">相关链接</span><span class="sxs-lookup"><span data-stu-id="db4c5-154">RELATED LINKS</span></span>

[<span data-ttu-id="db4c5-155">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="db4c5-155">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[<span data-ttu-id="db4c5-156">Get-Item</span><span class="sxs-lookup"><span data-stu-id="db4c5-156">Get-Item</span></span>](../Microsoft.PowerShell.Management/Get-Item.md)

[<span data-ttu-id="db4c5-157">Out-File</span><span class="sxs-lookup"><span data-stu-id="db4c5-157">Out-File</span></span>](Out-File.md)

[<span data-ttu-id="db4c5-158">FileSystem 提供程序</span><span class="sxs-lookup"><span data-stu-id="db4c5-158">FileSystem Provider</span></span>](../Microsoft.PowerShell.Core/about/about_FileSystem_Provider.md)
