---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-content?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Content
ms.openlocfilehash: 2d7575718391052fedea978b6957e5caec0eafdc
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197571"
---
# <span data-ttu-id="005cc-103">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="005cc-103">Clear-Content</span></span>

## <span data-ttu-id="005cc-104">摘要</span><span class="sxs-lookup"><span data-stu-id="005cc-104">SYNOPSIS</span></span>
<span data-ttu-id="005cc-105">删除项的内容，但不删除该项。</span><span class="sxs-lookup"><span data-stu-id="005cc-105">Deletes the contents of an item, but does not delete the item.</span></span>

## <span data-ttu-id="005cc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="005cc-106">SYNTAX</span></span>

### <span data-ttu-id="005cc-107">Path（默认值）</span><span class="sxs-lookup"><span data-stu-id="005cc-107">Path (Default)</span></span>

```
Clear-Content [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-Stream <String>] [<CommonParameters>]
```

### <span data-ttu-id="005cc-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="005cc-108">LiteralPath</span></span>

```
Clear-Content -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-Stream <String>] [<CommonParameters>]
```

## <span data-ttu-id="005cc-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="005cc-109">DESCRIPTION</span></span>

<span data-ttu-id="005cc-110">`Clear-Content`Cmdlet 删除项的内容（如从文件中删除文本），但不删除该项。</span><span class="sxs-lookup"><span data-stu-id="005cc-110">The `Clear-Content` cmdlet deletes the contents of an item, such as deleting the text from a file, but it does not delete the item.</span></span>
<span data-ttu-id="005cc-111">鉴于上述原因，项存在，但没有内容。</span><span class="sxs-lookup"><span data-stu-id="005cc-111">As a result, the item exists, but it is empty.</span></span>
<span data-ttu-id="005cc-112">与 `Clear-Content` 类似 `Clear-Item` ，但它适用于具有内容的项，而不是具有值的项。</span><span class="sxs-lookup"><span data-stu-id="005cc-112">The `Clear-Content` is similar to `Clear-Item`, but it works on items with contents, instead of items with values.</span></span>

## <span data-ttu-id="005cc-113">示例</span><span class="sxs-lookup"><span data-stu-id="005cc-113">EXAMPLES</span></span>

### <span data-ttu-id="005cc-114">示例1：删除目录中的所有内容</span><span class="sxs-lookup"><span data-stu-id="005cc-114">Example 1: Delete all content from a directory</span></span>

```powershell
Clear-Content "..\SmpUsers\*\init.txt"
```

<span data-ttu-id="005cc-115">此命令删除 SmpUsers 目录的所有子目录内的“init.txt”文件中的所有内容。</span><span class="sxs-lookup"><span data-stu-id="005cc-115">This command deletes all of the content from the "init.txt" files in all subdirectories of the SmpUsers directory.</span></span>
<span data-ttu-id="005cc-116">不删除这些文件，但它们为空。</span><span class="sxs-lookup"><span data-stu-id="005cc-116">The files are not deleted, but they are empty.</span></span>

### <span data-ttu-id="005cc-117">示例2：删除包含通配符的所有文件的内容</span><span class="sxs-lookup"><span data-stu-id="005cc-117">Example 2: Delete content of all files with a wildcard</span></span>

```powershell
Clear-Content -Path "*" -Filter "*.log" -Force
```

<span data-ttu-id="005cc-118">此命令删除当前目录中所有扩展名为“.log”的文件（包括具有只读属性的文件）的内容。</span><span class="sxs-lookup"><span data-stu-id="005cc-118">This command deletes the contents of all files in the current directory with the ".log" file name extension, including files with the read-only attribute.</span></span>
<span data-ttu-id="005cc-119">路径中的星号 (\*) 表示当前目录中的所有项。</span><span class="sxs-lookup"><span data-stu-id="005cc-119">The asterisk (\*) in the path represents all items in the current directory.</span></span>
<span data-ttu-id="005cc-120">**Force** 参数使该命令对只读文件有效。</span><span class="sxs-lookup"><span data-stu-id="005cc-120">The **Force** parameter makes the command effective on read-only files.</span></span>
<span data-ttu-id="005cc-121">使用筛选器将命令限制为具有 .log 文件扩展名的文件，而不是指定 \* 。在路径中，可以更快地执行操作。</span><span class="sxs-lookup"><span data-stu-id="005cc-121">Using a filter to restrict the command to files with the .log file name extension instead of specifying \*.log in the path makes the operation faster.</span></span>

### <span data-ttu-id="005cc-122">示例3：清除流中的所有数据</span><span class="sxs-lookup"><span data-stu-id="005cc-122">Example 3: Clear all data from a stream</span></span>

<span data-ttu-id="005cc-123">此示例显示了 `Clear-Content` cmdlet 如何从备用数据流中清除内容，同时保持流不变。</span><span class="sxs-lookup"><span data-stu-id="005cc-123">This example shows how the `Clear-Content` cmdlet clears the content from an alternate data stream while leaving the stream intact.</span></span>

<span data-ttu-id="005cc-124">第一个命令使用 `Get-Content` cmdlet 来获取 Copy-Script.ps1 文件中的区域的内容，该文件是从 Internet 下载的。</span><span class="sxs-lookup"><span data-stu-id="005cc-124">The first command uses the `Get-Content` cmdlet to get the content of the Zone.Identifier stream in the Copy-Script.ps1 file, which was downloaded from the Internet.</span></span>

<span data-ttu-id="005cc-125">第二个命令使用 `Clear-Content` cmdlet 清除内容。</span><span class="sxs-lookup"><span data-stu-id="005cc-125">The second command uses the `Clear-Content` cmdlet to clear the content.</span></span>

<span data-ttu-id="005cc-126">第三个命令重复第一个命令。</span><span class="sxs-lookup"><span data-stu-id="005cc-126">The third command repeats the first command.</span></span> <span data-ttu-id="005cc-127">它将验证内容是否已清除，但流仍保持不变。</span><span class="sxs-lookup"><span data-stu-id="005cc-127">It verifies that the content is cleared, but the stream remains.</span></span> <span data-ttu-id="005cc-128">如果已删除该流，则该命令将生成错误。</span><span class="sxs-lookup"><span data-stu-id="005cc-128">If the stream were deleted, the command would generate an error.</span></span>

<span data-ttu-id="005cc-129">您可以使用类似此方法的方法来清除备用数据流的内容。</span><span class="sxs-lookup"><span data-stu-id="005cc-129">You can use a method like this one to clear the content of an alternate data stream.</span></span> <span data-ttu-id="005cc-130">但是，若要取消安全检查（该安全检查可阻止从 Internet 下载的文件），则不建议使用此方法。</span><span class="sxs-lookup"><span data-stu-id="005cc-130">However, it is not the recommended way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="005cc-131">如果验证下载的文件是安全的，请使用 `Unblock-File` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="005cc-131">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

```
PS C:\> Get-Content C:\Test\Copy-Script.ps1 -Stream Zone.Identifier

[ZoneTransfer]
ZoneId=3

PS C:\>Clear-Content C:\Test\Copy-Script.ps1 -Stream Zone.Identifier

PS C:\>Get-Content C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
PS C:\>
```

## <span data-ttu-id="005cc-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="005cc-132">PARAMETERS</span></span>

### <span data-ttu-id="005cc-133">-Stream</span><span class="sxs-lookup"><span data-stu-id="005cc-133">-Stream</span></span>

<span data-ttu-id="005cc-134">指定内容的备用数据流。</span><span class="sxs-lookup"><span data-stu-id="005cc-134">Specifies an alternative data stream for content.</span></span>
<span data-ttu-id="005cc-135">如果该流不存在，则此 cmdlet 将创建它。</span><span class="sxs-lookup"><span data-stu-id="005cc-135">If the stream does not exist, this cmdlet creates it.</span></span>
<span data-ttu-id="005cc-136">不支持通配符。</span><span class="sxs-lookup"><span data-stu-id="005cc-136">Wildcard characters are not supported.</span></span>

<span data-ttu-id="005cc-137">Stream 是 FileSystem 提供程序添加到的动态参数 `Clear-Content` 。</span><span class="sxs-lookup"><span data-stu-id="005cc-137">Stream is a dynamic parameter that the FileSystem provider adds to `Clear-Content`.</span></span>
<span data-ttu-id="005cc-138">此参数仅在文件系统驱动器中有效。</span><span class="sxs-lookup"><span data-stu-id="005cc-138">This parameter works only in file system drives.</span></span>

<span data-ttu-id="005cc-139">可以使用 `Clear-Content` cmdlet 更改区域的内容。标识符备用数据流。</span><span class="sxs-lookup"><span data-stu-id="005cc-139">You can use the `Clear-Content` cmdlet to change the content of the Zone.Identifier alternate data stream.</span></span>
<span data-ttu-id="005cc-140">但是，若要取消安全检查（该安全检查可阻止从 Internet 下载的文件），则不建议使用此方法。</span><span class="sxs-lookup"><span data-stu-id="005cc-140">However, we do not recommend this as a way to eliminate security checks that block files that are downloaded from the Internet.</span></span>
<span data-ttu-id="005cc-141">如果验证下载的文件是安全的，请使用 `Unblock-File` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="005cc-141">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

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

### <span data-ttu-id="005cc-142">-Credential</span><span class="sxs-lookup"><span data-stu-id="005cc-142">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="005cc-143">随 PowerShell 一起安装的任何提供程序都不支持此参数。</span><span class="sxs-lookup"><span data-stu-id="005cc-143">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="005cc-144">若要在运行此 cmdlet 时模拟其他用户或提升凭据，请使用 Invoke 命令。</span><span class="sxs-lookup"><span data-stu-id="005cc-144">To impersonate another user, or elevate your credentials when running this cmdlet, use Invoke-Command.</span></span>

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

### <span data-ttu-id="005cc-145">-Exclude</span><span class="sxs-lookup"><span data-stu-id="005cc-145">-Exclude</span></span>

<span data-ttu-id="005cc-146">以字符串数组的形式指定此 cmdlet 从内容路径中省略的字符串。</span><span class="sxs-lookup"><span data-stu-id="005cc-146">Specifies, as a string array, strings that this cmdlet omits from the path to the content.</span></span>
<span data-ttu-id="005cc-147">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="005cc-147">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="005cc-148">请输入路径元素或模式，例如“\*.txt”。</span><span class="sxs-lookup"><span data-stu-id="005cc-148">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="005cc-149">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="005cc-149">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="005cc-150">-Filter</span><span class="sxs-lookup"><span data-stu-id="005cc-150">-Filter</span></span>

<span data-ttu-id="005cc-151">以提供程序的格式或语言指定筛选器。</span><span class="sxs-lookup"><span data-stu-id="005cc-151">Specifies a filter in the provider's format or language.</span></span>
<span data-ttu-id="005cc-152">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="005cc-152">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="005cc-153">筛选器的语法（包括通配符的使用）取决于提供程序。</span><span class="sxs-lookup"><span data-stu-id="005cc-153">The syntax of the filter, including the use of wildcards, depends on the provider.</span></span>
<span data-ttu-id="005cc-154">筛选器比其他参数更有效，因为提供程序是在检索对象时应用筛选器，而不是在检索对象后再对其进行筛选。</span><span class="sxs-lookup"><span data-stu-id="005cc-154">Filters are more efficient than other parameters, because the provider applies them when retrieving the objects, rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="005cc-155">-Force</span><span class="sxs-lookup"><span data-stu-id="005cc-155">-Force</span></span>

<span data-ttu-id="005cc-156">强制运行命令而不要求用户确认。</span><span class="sxs-lookup"><span data-stu-id="005cc-156">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="005cc-157">-Include</span><span class="sxs-lookup"><span data-stu-id="005cc-157">-Include</span></span>

<span data-ttu-id="005cc-158">以字符串数组的形式指定此 cmdlet 清除的内容。</span><span class="sxs-lookup"><span data-stu-id="005cc-158">Specifies, as a string array, content that this cmdlet clears.</span></span>
<span data-ttu-id="005cc-159">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="005cc-159">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="005cc-160">请输入路径元素或模式，例如“\*.txt”。</span><span class="sxs-lookup"><span data-stu-id="005cc-160">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="005cc-161">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="005cc-161">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="005cc-162">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="005cc-162">-LiteralPath</span></span>

<span data-ttu-id="005cc-163">指定要删除其内容的项的路径。</span><span class="sxs-lookup"><span data-stu-id="005cc-163">Specifies the paths to the items from which content is deleted.</span></span>
<span data-ttu-id="005cc-164">与 **Path** 参数不同， **LiteralPath** 的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="005cc-164">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="005cc-165">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="005cc-165">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="005cc-166">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="005cc-166">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="005cc-167">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="005cc-167">Single quotation marks tell having PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="005cc-168">-Path</span><span class="sxs-lookup"><span data-stu-id="005cc-168">-Path</span></span>

<span data-ttu-id="005cc-169">指定要删除其内容的项的路径。</span><span class="sxs-lookup"><span data-stu-id="005cc-169">Specifies the paths to the items from which content is deleted.</span></span>
<span data-ttu-id="005cc-170">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="005cc-170">Wildcards are permitted.</span></span>
<span data-ttu-id="005cc-171">此路径必须是指向该项的路径，而不是容器的路径。</span><span class="sxs-lookup"><span data-stu-id="005cc-171">The paths must be paths to items, not to containers.</span></span>
<span data-ttu-id="005cc-172">例如，必须指定一个或多个文件的路径，而不是目录的路径。</span><span class="sxs-lookup"><span data-stu-id="005cc-172">For example, you must specify a path to one or more files, not a path to a directory.</span></span>
<span data-ttu-id="005cc-173">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="005cc-173">Wildcards are permitted.</span></span>
<span data-ttu-id="005cc-174">此参数为必需参数，但参数名（“Path”）为可选项。</span><span class="sxs-lookup"><span data-stu-id="005cc-174">This parameter is required, but the parameter name ("Path") is optional.</span></span>

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

### <span data-ttu-id="005cc-175">-Confirm</span><span class="sxs-lookup"><span data-stu-id="005cc-175">-Confirm</span></span>

<span data-ttu-id="005cc-176">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="005cc-176">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="005cc-177">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="005cc-177">-WhatIf</span></span>

<span data-ttu-id="005cc-178">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="005cc-178">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="005cc-179">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="005cc-179">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="005cc-180">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="005cc-180">CommonParameters</span></span>

<span data-ttu-id="005cc-181">此 cmdlet 支持通用参数： `-Debug` 、 `-ErrorAction` 、 `-ErrorVariable` 、、、、、、、 `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` 和 `-WarningVariable` 。</span><span class="sxs-lookup"><span data-stu-id="005cc-181">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="005cc-182">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="005cc-182">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="005cc-183">输入</span><span class="sxs-lookup"><span data-stu-id="005cc-183">INPUTS</span></span>

### <span data-ttu-id="005cc-184">无</span><span class="sxs-lookup"><span data-stu-id="005cc-184">None</span></span>

<span data-ttu-id="005cc-185">不能通过管道将对象传递给 `Clear-Content` 。</span><span class="sxs-lookup"><span data-stu-id="005cc-185">You cannot pipe objects to `Clear-Content`.</span></span>

## <span data-ttu-id="005cc-186">输出</span><span class="sxs-lookup"><span data-stu-id="005cc-186">OUTPUTS</span></span>

### <span data-ttu-id="005cc-187">无</span><span class="sxs-lookup"><span data-stu-id="005cc-187">None</span></span>

<span data-ttu-id="005cc-188">此 cmdlet 不返回任何对象。</span><span class="sxs-lookup"><span data-stu-id="005cc-188">This cmdlet does not return any objects.</span></span>

## <span data-ttu-id="005cc-189">注释</span><span class="sxs-lookup"><span data-stu-id="005cc-189">NOTES</span></span>

<span data-ttu-id="005cc-190">你可以将 `Clear-Content` 与 PowerShell FileSystem 提供程序和操作内容的其他提供程序一起使用。</span><span class="sxs-lookup"><span data-stu-id="005cc-190">You can use `Clear-Content` with the PowerShell FileSystem provider and with other providers that manipulate content.</span></span>
<span data-ttu-id="005cc-191">若要清除不视为内容的项（例如，由 PowerShell 证书或注册表提供程序管理的项），请使用 `Clear-Item` 。</span><span class="sxs-lookup"><span data-stu-id="005cc-191">To clear items that are not considered to be content, such as items managed by the PowerShell Certificate or Registry providers, use `Clear-Item`.</span></span>

<span data-ttu-id="005cc-192">`Clear-Content`Cmdlet 设计用于处理由任何提供程序公开的数据。</span><span class="sxs-lookup"><span data-stu-id="005cc-192">The `Clear-Content` cmdlet is designed to work with the data exposed by any provider.</span></span>
<span data-ttu-id="005cc-193">若要列出会话中可用的提供程序，请键入 `Get-PsProvider`。</span><span class="sxs-lookup"><span data-stu-id="005cc-193">To list the providers available in your session, type `Get-PsProvider`.</span></span>
<span data-ttu-id="005cc-194">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="005cc-194">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="005cc-195">相关链接</span><span class="sxs-lookup"><span data-stu-id="005cc-195">RELATED LINKS</span></span>

[<span data-ttu-id="005cc-196">Add-Content</span><span class="sxs-lookup"><span data-stu-id="005cc-196">Add-Content</span></span>](Add-Content.md)

[<span data-ttu-id="005cc-197">Get-Content</span><span class="sxs-lookup"><span data-stu-id="005cc-197">Get-Content</span></span>](Get-Content.md)

[<span data-ttu-id="005cc-198">Get-Item</span><span class="sxs-lookup"><span data-stu-id="005cc-198">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="005cc-199">Set-Content</span><span class="sxs-lookup"><span data-stu-id="005cc-199">Set-Content</span></span>](Set-Content.md)

[<span data-ttu-id="005cc-200">about_Providers</span><span class="sxs-lookup"><span data-stu-id="005cc-200">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
