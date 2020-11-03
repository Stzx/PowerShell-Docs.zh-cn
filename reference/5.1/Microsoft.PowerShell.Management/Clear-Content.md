---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-content?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Content
ms.openlocfilehash: b318abb06d36be5e28b9dcc3dc62fd4a70ab38fb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198322"
---
# <span data-ttu-id="df30c-103">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="df30c-103">Clear-Content</span></span>

## <span data-ttu-id="df30c-104">摘要</span><span class="sxs-lookup"><span data-stu-id="df30c-104">SYNOPSIS</span></span>
<span data-ttu-id="df30c-105">删除项的内容，但不删除该项。</span><span class="sxs-lookup"><span data-stu-id="df30c-105">Deletes the contents of an item, but does not delete the item.</span></span>

## <span data-ttu-id="df30c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="df30c-106">SYNTAX</span></span>

### <span data-ttu-id="df30c-107">Path（默认值）</span><span class="sxs-lookup"><span data-stu-id="df30c-107">Path (Default)</span></span>

```
Clear-Content [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [-Stream <String>] [<CommonParameters>]
```

### <span data-ttu-id="df30c-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="df30c-108">LiteralPath</span></span>

```
Clear-Content -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [-Stream <String>] [<CommonParameters>]
```

## <span data-ttu-id="df30c-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="df30c-109">DESCRIPTION</span></span>

<span data-ttu-id="df30c-110">`Clear-Content`Cmdlet 删除项的内容（如从文件中删除文本），但不删除该项。</span><span class="sxs-lookup"><span data-stu-id="df30c-110">The `Clear-Content` cmdlet deletes the contents of an item, such as deleting the text from a file, but it does not delete the item.</span></span>
<span data-ttu-id="df30c-111">鉴于上述原因，项存在，但没有内容。</span><span class="sxs-lookup"><span data-stu-id="df30c-111">As a result, the item exists, but it is empty.</span></span>
<span data-ttu-id="df30c-112">与 `Clear-Content` 类似 `Clear-Item` ，但它适用于具有内容的项，而不是具有值的项。</span><span class="sxs-lookup"><span data-stu-id="df30c-112">The `Clear-Content` is similar to `Clear-Item`, but it works on items with contents, instead of items with values.</span></span>

## <span data-ttu-id="df30c-113">示例</span><span class="sxs-lookup"><span data-stu-id="df30c-113">EXAMPLES</span></span>

### <span data-ttu-id="df30c-114">示例1：删除目录中的所有内容</span><span class="sxs-lookup"><span data-stu-id="df30c-114">Example 1: Delete all content from a directory</span></span>

```powershell
Clear-Content "..\SmpUsers\*\init.txt"
```

<span data-ttu-id="df30c-115">此命令删除 SmpUsers 目录的所有子目录内的“init.txt”文件中的所有内容。</span><span class="sxs-lookup"><span data-stu-id="df30c-115">This command deletes all of the content from the "init.txt" files in all subdirectories of the SmpUsers directory.</span></span>
<span data-ttu-id="df30c-116">不删除这些文件，但它们为空。</span><span class="sxs-lookup"><span data-stu-id="df30c-116">The files are not deleted, but they are empty.</span></span>

### <span data-ttu-id="df30c-117">示例2：删除包含通配符的所有文件的内容</span><span class="sxs-lookup"><span data-stu-id="df30c-117">Example 2: Delete content of all files with a wildcard</span></span>

```powershell
Clear-Content -Path "*" -Filter "*.log" -Force
```

<span data-ttu-id="df30c-118">此命令删除当前目录中所有扩展名为“.log”的文件（包括具有只读属性的文件）的内容。</span><span class="sxs-lookup"><span data-stu-id="df30c-118">This command deletes the contents of all files in the current directory with the ".log" file name extension, including files with the read-only attribute.</span></span>
<span data-ttu-id="df30c-119">路径中的星号 (\*) 表示当前目录中的所有项。</span><span class="sxs-lookup"><span data-stu-id="df30c-119">The asterisk (\*) in the path represents all items in the current directory.</span></span>
<span data-ttu-id="df30c-120">**Force** 参数使该命令对只读文件有效。</span><span class="sxs-lookup"><span data-stu-id="df30c-120">The **Force** parameter makes the command effective on read-only files.</span></span>
<span data-ttu-id="df30c-121">使用筛选器将命令限制为具有 .log 文件扩展名的文件，而不是指定 \* 。在路径中，可以更快地执行操作。</span><span class="sxs-lookup"><span data-stu-id="df30c-121">Using a filter to restrict the command to files with the .log file name extension instead of specifying \*.log in the path makes the operation faster.</span></span>

### <span data-ttu-id="df30c-122">示例3：清除流中的所有数据</span><span class="sxs-lookup"><span data-stu-id="df30c-122">Example 3: Clear all data from a stream</span></span>

<span data-ttu-id="df30c-123">此示例显示了 `Clear-Content` cmdlet 如何从备用数据流中清除内容，同时保持流不变。</span><span class="sxs-lookup"><span data-stu-id="df30c-123">This example shows how the `Clear-Content` cmdlet clears the content from an alternate data stream while leaving the stream intact.</span></span>

<span data-ttu-id="df30c-124">第一个命令使用 `Get-Content` cmdlet 来获取 Copy-Script.ps1 文件中的区域的内容，该文件是从 Internet 下载的。</span><span class="sxs-lookup"><span data-stu-id="df30c-124">The first command uses the `Get-Content` cmdlet to get the content of the Zone.Identifier stream in the Copy-Script.ps1 file, which was downloaded from the Internet.</span></span>

<span data-ttu-id="df30c-125">第二个命令使用 `Clear-Content` cmdlet 清除内容。</span><span class="sxs-lookup"><span data-stu-id="df30c-125">The second command uses the `Clear-Content` cmdlet to clear the content.</span></span>

<span data-ttu-id="df30c-126">第三个命令重复第一个命令。</span><span class="sxs-lookup"><span data-stu-id="df30c-126">The third command repeats the first command.</span></span> <span data-ttu-id="df30c-127">它将验证内容是否已清除，但流仍保持不变。</span><span class="sxs-lookup"><span data-stu-id="df30c-127">It verifies that the content is cleared, but the stream remains.</span></span> <span data-ttu-id="df30c-128">如果已删除该流，则该命令将生成错误。</span><span class="sxs-lookup"><span data-stu-id="df30c-128">If the stream were deleted, the command would generate an error.</span></span>

<span data-ttu-id="df30c-129">您可以使用类似此方法的方法来清除备用数据流的内容。</span><span class="sxs-lookup"><span data-stu-id="df30c-129">You can use a method like this one to clear the content of an alternate data stream.</span></span> <span data-ttu-id="df30c-130">但是，若要取消安全检查（该安全检查可阻止从 Internet 下载的文件），则不建议使用此方法。</span><span class="sxs-lookup"><span data-stu-id="df30c-130">However, it is not the recommended way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="df30c-131">如果验证下载的文件是安全的，请使用 `Unblock-File` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="df30c-131">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

```powershell
Get-Content C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
```

```Output
[ZoneTransfer]
ZoneId=3
```

```powershell
Clear-Content C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
Get-Content C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
```

```Output

```

## <span data-ttu-id="df30c-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="df30c-132">PARAMETERS</span></span>

### <span data-ttu-id="df30c-133">-Credential</span><span class="sxs-lookup"><span data-stu-id="df30c-133">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="df30c-134">随 PowerShell 一起安装的任何提供程序都不支持此参数。</span><span class="sxs-lookup"><span data-stu-id="df30c-134">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="df30c-135">若要在运行此 cmdlet 时模拟其他用户或提升凭据，请使用 Invoke 命令。</span><span class="sxs-lookup"><span data-stu-id="df30c-135">To impersonate another user, or elevate your credentials when running this cmdlet, use Invoke-Command.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="df30c-136">-Exclude</span><span class="sxs-lookup"><span data-stu-id="df30c-136">-Exclude</span></span>

<span data-ttu-id="df30c-137">以字符串数组的形式指定此 cmdlet 从内容路径中省略的字符串。</span><span class="sxs-lookup"><span data-stu-id="df30c-137">Specifies, as a string array, strings that this cmdlet omits from the path to the content.</span></span>
<span data-ttu-id="df30c-138">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="df30c-138">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="df30c-139">请输入路径元素或模式，例如“\*.txt”。</span><span class="sxs-lookup"><span data-stu-id="df30c-139">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="df30c-140">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="df30c-140">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="df30c-141">-Filter</span><span class="sxs-lookup"><span data-stu-id="df30c-141">-Filter</span></span>

<span data-ttu-id="df30c-142">以提供程序的格式或语言指定筛选器。</span><span class="sxs-lookup"><span data-stu-id="df30c-142">Specifies a filter in the provider's format or language.</span></span>
<span data-ttu-id="df30c-143">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="df30c-143">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="df30c-144">筛选器的语法（包括通配符的使用）取决于提供程序。</span><span class="sxs-lookup"><span data-stu-id="df30c-144">The syntax of the filter, including the use of wildcards, depends on the provider.</span></span>
<span data-ttu-id="df30c-145">筛选器比其他参数更有效，因为提供程序是在检索对象时应用筛选器，而不是在检索对象后再对其进行筛选。</span><span class="sxs-lookup"><span data-stu-id="df30c-145">Filters are more efficient than other parameters, because the provider applies them when retrieving the objects, rather than having PowerShell filter the objects after they are retrieved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="df30c-146">-Force</span><span class="sxs-lookup"><span data-stu-id="df30c-146">-Force</span></span>

<span data-ttu-id="df30c-147">强制运行命令而不要求用户确认。</span><span class="sxs-lookup"><span data-stu-id="df30c-147">Forces the command to run without asking for user confirmation.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df30c-148">-Include</span><span class="sxs-lookup"><span data-stu-id="df30c-148">-Include</span></span>

<span data-ttu-id="df30c-149">以字符串数组的形式指定此 cmdlet 清除的内容。</span><span class="sxs-lookup"><span data-stu-id="df30c-149">Specifies, as a string array, content that this cmdlet clears.</span></span>
<span data-ttu-id="df30c-150">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="df30c-150">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="df30c-151">请输入路径元素或模式，例如“\*.txt”。</span><span class="sxs-lookup"><span data-stu-id="df30c-151">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="df30c-152">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="df30c-152">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="df30c-153">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="df30c-153">-LiteralPath</span></span>

<span data-ttu-id="df30c-154">指定要删除其内容的项的路径。</span><span class="sxs-lookup"><span data-stu-id="df30c-154">Specifies the paths to the items from which content is deleted.</span></span>
<span data-ttu-id="df30c-155">与 **Path** 参数不同， **LiteralPath** 的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="df30c-155">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="df30c-156">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="df30c-156">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="df30c-157">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="df30c-157">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="df30c-158">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="df30c-158">Single quotation marks tell having PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="df30c-159">-Path</span><span class="sxs-lookup"><span data-stu-id="df30c-159">-Path</span></span>

<span data-ttu-id="df30c-160">指定要删除其内容的项的路径。</span><span class="sxs-lookup"><span data-stu-id="df30c-160">Specifies the paths to the items from which content is deleted.</span></span>
<span data-ttu-id="df30c-161">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="df30c-161">Wildcards are permitted.</span></span>
<span data-ttu-id="df30c-162">此路径必须是指向该项的路径，而不是容器的路径。</span><span class="sxs-lookup"><span data-stu-id="df30c-162">The paths must be paths to items, not to containers.</span></span>
<span data-ttu-id="df30c-163">例如，必须指定一个或多个文件的路径，而不是目录的路径。</span><span class="sxs-lookup"><span data-stu-id="df30c-163">For example, you must specify a path to one or more files, not a path to a directory.</span></span>
<span data-ttu-id="df30c-164">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="df30c-164">Wildcards are permitted.</span></span>
<span data-ttu-id="df30c-165">此参数为必需参数，但参数名（“Path”）为可选项。</span><span class="sxs-lookup"><span data-stu-id="df30c-165">This parameter is required, but the parameter name ("Path") is optional.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="df30c-166">-Stream</span><span class="sxs-lookup"><span data-stu-id="df30c-166">-Stream</span></span>

<span data-ttu-id="df30c-167">指定内容的备用数据流。</span><span class="sxs-lookup"><span data-stu-id="df30c-167">Specifies an alternative data stream for content.</span></span>
<span data-ttu-id="df30c-168">如果该流不存在，则此 cmdlet 将创建它。</span><span class="sxs-lookup"><span data-stu-id="df30c-168">If the stream does not exist, this cmdlet creates it.</span></span>
<span data-ttu-id="df30c-169">不支持通配符。</span><span class="sxs-lookup"><span data-stu-id="df30c-169">Wildcard characters are not supported.</span></span>

<span data-ttu-id="df30c-170">**Stream** 是 FileSystem 提供程序添加到的动态参数 `Clear-Content` 。</span><span class="sxs-lookup"><span data-stu-id="df30c-170">**Stream** is a dynamic parameter that the FileSystem provider adds to `Clear-Content`.</span></span>
<span data-ttu-id="df30c-171">此参数仅在文件系统驱动器中有效。</span><span class="sxs-lookup"><span data-stu-id="df30c-171">This parameter works only in file system drives.</span></span>

<span data-ttu-id="df30c-172">可以使用 `Clear-Content` cmdlet 更改区域的内容。标识符备用数据流。</span><span class="sxs-lookup"><span data-stu-id="df30c-172">You can use the `Clear-Content` cmdlet to change the content of the Zone.Identifier alternate data stream.</span></span>
<span data-ttu-id="df30c-173">但是，若要取消安全检查（该安全检查可阻止从 Internet 下载的文件），则不建议使用此方法。</span><span class="sxs-lookup"><span data-stu-id="df30c-173">However, we do not recommend this as a way to eliminate security checks that block files that are downloaded from the Internet.</span></span>
<span data-ttu-id="df30c-174">如果验证下载的文件是安全的，请使用 `Unblock-File` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="df30c-174">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

<span data-ttu-id="df30c-175">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="df30c-175">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df30c-176">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="df30c-176">-UseTransaction</span></span>

<span data-ttu-id="df30c-177">在活动事务中使用该命令。</span><span class="sxs-lookup"><span data-stu-id="df30c-177">Includes the command in the active transaction.</span></span>
<span data-ttu-id="df30c-178">仅当正在执行事务时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="df30c-178">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="df30c-179">有关详细信息，请参阅 [about_transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)。</span><span class="sxs-lookup"><span data-stu-id="df30c-179">For more information, see [about_transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df30c-180">-Confirm</span><span class="sxs-lookup"><span data-stu-id="df30c-180">-Confirm</span></span>

<span data-ttu-id="df30c-181">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="df30c-181">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="df30c-182">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="df30c-182">-WhatIf</span></span>

<span data-ttu-id="df30c-183">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="df30c-183">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="df30c-184">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="df30c-184">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="df30c-185">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="df30c-185">CommonParameters</span></span>

<span data-ttu-id="df30c-186">此 cmdlet 支持通用参数： `-Debug` 、 `-ErrorAction` 、 `-ErrorVariable` 、、、、、、、 `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` 和 `-WarningVariable` 。</span><span class="sxs-lookup"><span data-stu-id="df30c-186">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="df30c-187">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="df30c-187">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="df30c-188">输入</span><span class="sxs-lookup"><span data-stu-id="df30c-188">INPUTS</span></span>

### <span data-ttu-id="df30c-189">无</span><span class="sxs-lookup"><span data-stu-id="df30c-189">None</span></span>

<span data-ttu-id="df30c-190">不能通过管道将对象传递给 `Clear-Content` 。</span><span class="sxs-lookup"><span data-stu-id="df30c-190">You cannot pipe objects to `Clear-Content`.</span></span>

## <span data-ttu-id="df30c-191">输出</span><span class="sxs-lookup"><span data-stu-id="df30c-191">OUTPUTS</span></span>

### <span data-ttu-id="df30c-192">无</span><span class="sxs-lookup"><span data-stu-id="df30c-192">None</span></span>

<span data-ttu-id="df30c-193">此 cmdlet 不返回任何对象。</span><span class="sxs-lookup"><span data-stu-id="df30c-193">This cmdlet does not return any objects.</span></span>

## <span data-ttu-id="df30c-194">注释</span><span class="sxs-lookup"><span data-stu-id="df30c-194">NOTES</span></span>

<span data-ttu-id="df30c-195">你可以将 `Clear-Content` 与 PowerShell FileSystem 提供程序和操作内容的其他提供程序一起使用。</span><span class="sxs-lookup"><span data-stu-id="df30c-195">You can use `Clear-Content` with the PowerShell FileSystem provider and with other providers that manipulate content.</span></span>
<span data-ttu-id="df30c-196">若要清除不视为内容的项（例如，由 PowerShell 证书或注册表提供程序管理的项），请使用 `Clear-Item` 。</span><span class="sxs-lookup"><span data-stu-id="df30c-196">To clear items that are not considered to be content, such as items managed by the PowerShell Certificate or Registry providers, use `Clear-Item`.</span></span>

<span data-ttu-id="df30c-197">`Clear-Content`Cmdlet 设计用于处理由任何提供程序公开的数据。</span><span class="sxs-lookup"><span data-stu-id="df30c-197">The `Clear-Content` cmdlet is designed to work with the data exposed by any provider.</span></span>
<span data-ttu-id="df30c-198">若要列出会话中可用的提供程序，请键入 `Get-PsProvider`。</span><span class="sxs-lookup"><span data-stu-id="df30c-198">To list the providers available in your session, type `Get-PsProvider`.</span></span>
<span data-ttu-id="df30c-199">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="df30c-199">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="df30c-200">相关链接</span><span class="sxs-lookup"><span data-stu-id="df30c-200">RELATED LINKS</span></span>

[<span data-ttu-id="df30c-201">Add-Content</span><span class="sxs-lookup"><span data-stu-id="df30c-201">Add-Content</span></span>](Add-Content.md)

[<span data-ttu-id="df30c-202">Get-Content</span><span class="sxs-lookup"><span data-stu-id="df30c-202">Get-Content</span></span>](Get-Content.md)

[<span data-ttu-id="df30c-203">Get-Item</span><span class="sxs-lookup"><span data-stu-id="df30c-203">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="df30c-204">Set-Content</span><span class="sxs-lookup"><span data-stu-id="df30c-204">Set-Content</span></span>](Set-Content.md)

[<span data-ttu-id="df30c-205">about_Providers</span><span class="sxs-lookup"><span data-stu-id="df30c-205">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
