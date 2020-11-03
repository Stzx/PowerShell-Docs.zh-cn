---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/07/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-item?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Item
ms.openlocfilehash: 18bf42e4378ce561fb24a3c3d5191ebf38a0ea20
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198068"
---
# <span data-ttu-id="3cc02-103">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="3cc02-103">Remove-Item</span></span>

## <span data-ttu-id="3cc02-104">摘要</span><span class="sxs-lookup"><span data-stu-id="3cc02-104">SYNOPSIS</span></span>
<span data-ttu-id="3cc02-105">删除指定项。</span><span class="sxs-lookup"><span data-stu-id="3cc02-105">Deletes the specified items.</span></span>

## <span data-ttu-id="3cc02-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3cc02-106">SYNTAX</span></span>

### <span data-ttu-id="3cc02-107">Path（默认值）</span><span class="sxs-lookup"><span data-stu-id="3cc02-107">Path (Default)</span></span>

```
Remove-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Recurse]
 [-Force] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [-Stream <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="3cc02-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="3cc02-108">LiteralPath</span></span>

```
Remove-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Recurse]
 [-Force] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [-Stream <String[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="3cc02-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3cc02-109">DESCRIPTION</span></span>

<span data-ttu-id="3cc02-110">`Remove-Item`Cmdlet 删除一个或多个项。</span><span class="sxs-lookup"><span data-stu-id="3cc02-110">The `Remove-Item` cmdlet deletes one or more items.</span></span> <span data-ttu-id="3cc02-111">由于许多提供程序都支持它，因此它可以删除多种不同类型的项，其中包括文件、文件夹、注册表项、变量、别名和函数。</span><span class="sxs-lookup"><span data-stu-id="3cc02-111">Because it is supported by many providers, it can delete many different types of items, including files, folders, registry keys, variables, aliases, and functions.</span></span>

## <span data-ttu-id="3cc02-112">示例</span><span class="sxs-lookup"><span data-stu-id="3cc02-112">EXAMPLES</span></span>

### <span data-ttu-id="3cc02-113">示例1：删除具有任何文件扩展名的文件</span><span class="sxs-lookup"><span data-stu-id="3cc02-113">Example 1: Delete files that have any file name extension</span></span>

<span data-ttu-id="3cc02-114">此示例将从文件夹中删除所有名称中包含点)  (的文件 `.` `C:\Test` 。</span><span class="sxs-lookup"><span data-stu-id="3cc02-114">This example deletes all of the files that have names that include a dot (`.`) from the `C:\Test` folder.</span></span> <span data-ttu-id="3cc02-115">由于该命令指定一个点，因此该命令不删除没有文件扩展名的文件夹或文件。</span><span class="sxs-lookup"><span data-stu-id="3cc02-115">Because the command specifies a dot, the command does not delete folders or files that have no file name extension.</span></span>

```powershell
Remove-Item C:\Test\*.*
```

### <span data-ttu-id="3cc02-116">示例2：删除文件夹中的某些文档文件</span><span class="sxs-lookup"><span data-stu-id="3cc02-116">Example 2: Delete some of the document files in a folder</span></span>

<span data-ttu-id="3cc02-117">此示例从当前文件夹中删除所有具有 `.doc` 文件扩展名的文件和不包含的名称 `*1*` 。</span><span class="sxs-lookup"><span data-stu-id="3cc02-117">This example deletes from the current folder all files that have a `.doc` file name extension and a name that does not include `*1*`.</span></span>

```powershell
Remove-Item * -Include *.doc -Exclude *1*
```

<span data-ttu-id="3cc02-118">它使用通配符 (`*`) 来指定当前文件夹的内容。</span><span class="sxs-lookup"><span data-stu-id="3cc02-118">It uses the wildcard character (`*`) to specify the contents of the current folder.</span></span> <span data-ttu-id="3cc02-119">它使用 **Include** 和 **Exclude** 参数来指定要删除的文件。</span><span class="sxs-lookup"><span data-stu-id="3cc02-119">It uses the **Include** and **Exclude** parameters to specify the files to delete.</span></span>

### <span data-ttu-id="3cc02-120">示例3：删除隐藏的只读文件</span><span class="sxs-lookup"><span data-stu-id="3cc02-120">Example 3: Delete hidden, read-only files</span></span>

<span data-ttu-id="3cc02-121">此命令删除 *隐藏* 和 *只读* 文件。</span><span class="sxs-lookup"><span data-stu-id="3cc02-121">This command deletes a file that is both *hidden* and *read-only* .</span></span>

```powershell
Remove-Item -Path C:\Test\hidden-RO-file.txt -Force
```

<span data-ttu-id="3cc02-122">它使用 **Path** 参数指定文件。</span><span class="sxs-lookup"><span data-stu-id="3cc02-122">It uses the **Path** parameter to specify the file.</span></span> <span data-ttu-id="3cc02-123">它使用 **Force** 参数将其删除。</span><span class="sxs-lookup"><span data-stu-id="3cc02-123">It uses the **Force** parameter to delete it.</span></span> <span data-ttu-id="3cc02-124">如果没有 **强制** ，则无法删除 _只读_ 或 _隐藏_ 文件。</span><span class="sxs-lookup"><span data-stu-id="3cc02-124">Without **Force** , you cannot delete _read-only_ or _hidden_ files.</span></span>

### <span data-ttu-id="3cc02-125">示例4：以递归方式删除子文件夹中的文件</span><span class="sxs-lookup"><span data-stu-id="3cc02-125">Example 4: Delete files in subfolders recursively</span></span>

<span data-ttu-id="3cc02-126">此命令将以递归方式删除当前文件夹和所有子文件夹中的所有 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="3cc02-126">This command deletes all of the CSV files in the current folder and all subfolders recursively.</span></span>

<span data-ttu-id="3cc02-127">因为中的 **递归** 参数 `Remove-Item` 有一个已知的问题，所以本示例中的命令使用 `Get-ChildItem` 来获取所需的文件，然后使用管道运算符将其传递给 `Remove-Item` 。</span><span class="sxs-lookup"><span data-stu-id="3cc02-127">Because the **Recurse** parameter in `Remove-Item` has a known issue, the command in this example uses `Get-ChildItem` to get the desired files, and then uses the pipeline operator to pass them to `Remove-Item`.</span></span>

```powershell
Get-ChildItem * -Include *.csv -Recurse | Remove-Item
```

<span data-ttu-id="3cc02-128">在 `Get-ChildItem` 命令中， **路径** 的值为 (`*`) ，表示当前文件夹的内容。</span><span class="sxs-lookup"><span data-stu-id="3cc02-128">In the `Get-ChildItem` command, **Path** has a value of (`*`), which represents the contents of the current folder.</span></span> <span data-ttu-id="3cc02-129">它使用 **Include** 来指定 CSV 文件类型，并使用 **递归** 来使检索递归。</span><span class="sxs-lookup"><span data-stu-id="3cc02-129">It uses **Include** to specify the CSV file type, and it uses **Recurse** to make the retrieval recursive.</span></span> <span data-ttu-id="3cc02-130">如果尝试指定文件类型（如 `-Path *.csv` ），则该 cmdlet 会将搜索的使用者解释为没有子项的文件，而 **递归** 会失败。</span><span class="sxs-lookup"><span data-stu-id="3cc02-130">If you try to specify the file type the path, such as `-Path *.csv`, the cmdlet interprets the subject of the search to be a file that has no child items, and **Recurse** fails.</span></span>

### <span data-ttu-id="3cc02-131">示例5：以递归方式删除子项</span><span class="sxs-lookup"><span data-stu-id="3cc02-131">Example 5: Delete subkeys recursively</span></span>

<span data-ttu-id="3cc02-132">此命令删除 "OldApp" 注册表项及其所有子项和值。</span><span class="sxs-lookup"><span data-stu-id="3cc02-132">This command deletes the "OldApp" registry key and all its subkeys and values.</span></span> <span data-ttu-id="3cc02-133">它使用 `Remove-Item` 删除密钥。</span><span class="sxs-lookup"><span data-stu-id="3cc02-133">It uses `Remove-Item` to remove the key.</span></span> <span data-ttu-id="3cc02-134">指定了路径，但省略了可选的参数名称 ( **路径** ) 。</span><span class="sxs-lookup"><span data-stu-id="3cc02-134">The path is specified, but the optional parameter name ( **Path** ) is omitted.</span></span>

<span data-ttu-id="3cc02-135">**递归** 参数会以递归方式删除 "OldApp" 项的所有内容。</span><span class="sxs-lookup"><span data-stu-id="3cc02-135">The **Recurse** parameter deletes all of the contents of the "OldApp" key recursively.</span></span> <span data-ttu-id="3cc02-136">如果该注册表项包含子项并且省略了 **递归** 参数，系统会提示您确认是否要删除该注册表项的内容。</span><span class="sxs-lookup"><span data-stu-id="3cc02-136">If the key contains subkeys and you omit the **Recurse** parameter, you are prompted to confirm that you want to delete the contents of the key.</span></span>

```powershell
Remove-Item HKLM:\Software\MyCompany\OldApp -Recurse
```

### <span data-ttu-id="3cc02-137">示例6：删除包含特殊字符的文件</span><span class="sxs-lookup"><span data-stu-id="3cc02-137">Example 6: Deleting files with special characters</span></span>

<span data-ttu-id="3cc02-138">下面的示例演示如何删除包含特殊字符（如方括号或圆括号）的文件。</span><span class="sxs-lookup"><span data-stu-id="3cc02-138">The following example shows how to delete files that contain special characters like brackets or parentheses.</span></span>

```powershell
Get-ChildItem
```

```Output
    Directory: C:\temp\Downloads

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a---          6/1/2018  12:19 PM           1362 myFile.txt
-a---          6/1/2018  12:30 PM           1132 myFile[1].txt
-a---          6/1/2018  12:19 PM           1283 myFile[2].txt
-a---          6/1/2018  12:19 PM           1432 myFile[3].txt

```

```powershell
Get-ChildItem | Where-Object Name -Like '*`[*'
```

```Output
    Directory: C:\temp\Downloads

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a---          6/1/2018  12:30 PM           1132 myFile[1].txt
-a---          6/1/2018  12:19 PM           1283 myFile[2].txt
-a---          6/1/2018  12:19 PM           1432 myFile[3].txt

```

```powershell
Get-ChildItem | Where-Object Name -Like '*`[*' | ForEach-Object { Remove-Item -LiteralPath $_.Name }
Get-ChildItem
```

```Output
    Directory: C:\temp\Downloads

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a---          6/1/2018  12:19 PM           1362 myFile.txt
```

### <span data-ttu-id="3cc02-139">示例7：删除备用数据流</span><span class="sxs-lookup"><span data-stu-id="3cc02-139">Example 7: Remove an alternate data stream</span></span>

<span data-ttu-id="3cc02-140">此示例演示如何使用 cmdlet 的 **Stream** 动态参数 `Remove-Item` 删除备用数据流。</span><span class="sxs-lookup"><span data-stu-id="3cc02-140">This example shows how to use the **Stream** dynamic parameter of the `Remove-Item` cmdlet to delete an alternate data stream.</span></span> <span data-ttu-id="3cc02-141">流参数是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="3cc02-141">The stream parameter is introduced in Windows PowerShell 3.0.</span></span>

```powershell
Get-Item C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
```

```Output
   FileName: \\C:\Test\Copy-Script.ps1

Stream                   Length
------                   ------
Zone.Identifier              26

```

```powershell
Remove-Item C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
Get-Item C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
```

```Output
Get-Item : Could not open alternate data stream 'Zone.Identifier' of file 'C:\Test\Copy-Script.ps1'.
At line:1 char:1
+ Get-Item 'C:\Test\Copy-Script.ps1' -Stream Zone.Identifier
+ [!INCLUDE[]()][!INCLUDE[]()][!INCLUDE[]()][!INCLUDE[]()][!INCLUDE[]()]~~
    + CategoryInfo          : ObjectNotFound: (C:\Test\Copy-Script.ps1:String) [Get-Item], FileNotFoundE
   xception
    + FullyQualifiedErrorId : AlternateDataStreamNotFound,Microsoft.PowerShell.Commands.GetItemCommand

```

<span data-ttu-id="3cc02-142">**Stream** 参数 `Get-Item` 获取该文件的 **区域。标识符** 流 `Copy-Script.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="3cc02-142">The **Stream** parameter `Get-Item` gets the **Zone.Identifier** stream of the `Copy-Script.ps1` file.</span></span> <span data-ttu-id="3cc02-143">`Remove-Item` 使用 **Stream** 参数删除 **区域的标识符** 流。</span><span class="sxs-lookup"><span data-stu-id="3cc02-143">`Remove-Item` uses the **Stream** parameter to remove the **Zone.Identifier** stream of the file.</span></span> <span data-ttu-id="3cc02-144">最后，该 `Get-Item` cmdlet 会显示 **区域。** 已删除标识符流。</span><span class="sxs-lookup"><span data-stu-id="3cc02-144">Finally, the `Get-Item` cmdlet shows that the **Zone.Identifier** stream was deleted.</span></span>

## <span data-ttu-id="3cc02-145">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3cc02-145">PARAMETERS</span></span>

### <span data-ttu-id="3cc02-146">-Credential</span><span class="sxs-lookup"><span data-stu-id="3cc02-146">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="3cc02-147">随 PowerShell 一起安装的任何提供程序都不支持此参数。</span><span class="sxs-lookup"><span data-stu-id="3cc02-147">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="3cc02-148">若要在运行此 cmdlet 时模拟其他用户或提升凭据，请使用 [Invoke 命令](../Microsoft.PowerShell.Core/Invoke-Command.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc02-148">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="3cc02-149">-Exclude</span><span class="sxs-lookup"><span data-stu-id="3cc02-149">-Exclude</span></span>

<span data-ttu-id="3cc02-150">指定为字符串数组，此 cmdlet 在操作中排除的项。</span><span class="sxs-lookup"><span data-stu-id="3cc02-150">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="3cc02-151">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="3cc02-151">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="3cc02-152">请输入路径元素或模式，例如 `*.txt`。</span><span class="sxs-lookup"><span data-stu-id="3cc02-152">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="3cc02-153">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="3cc02-153">Wildcard characters are permitted.</span></span> <span data-ttu-id="3cc02-154">仅 **Exclude** 当命令包括项的内容时（例如 `C:\Windows\*` ，其中的通配符指定目录的内容），Exclude 参数才有效 `C:\Windows` 。</span><span class="sxs-lookup"><span data-stu-id="3cc02-154">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="3cc02-155">-Filter</span><span class="sxs-lookup"><span data-stu-id="3cc02-155">-Filter</span></span>

<span data-ttu-id="3cc02-156">指定用于限定 **路径** 参数的筛选器。</span><span class="sxs-lookup"><span data-stu-id="3cc02-156">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="3cc02-157">[FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)提供程序是唯一一种支持使用筛选器的已安装 PowerShell 提供程序。</span><span class="sxs-lookup"><span data-stu-id="3cc02-157">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="3cc02-158">可以在 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)中找到 **文件系统** 筛选语言的语法。</span><span class="sxs-lookup"><span data-stu-id="3cc02-158">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="3cc02-159">筛选器比其他参数更有效，因为提供程序在 cmdlet 获取对象时应用筛选器，而不是在检索对象后再对其进行筛选。</span><span class="sxs-lookup"><span data-stu-id="3cc02-159">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="3cc02-160">-Force</span><span class="sxs-lookup"><span data-stu-id="3cc02-160">-Force</span></span>

<span data-ttu-id="3cc02-161">强制 cmdlet 删除不能更改的项，如隐藏文件或只读文件，或者只读别名或变量。</span><span class="sxs-lookup"><span data-stu-id="3cc02-161">Forces the cmdlet to remove items that cannot otherwise be changed, such as hidden or read-only files or read-only aliases or variables.</span></span> <span data-ttu-id="3cc02-162">该 cmdlet 不能删除常量别名或变量。</span><span class="sxs-lookup"><span data-stu-id="3cc02-162">The cmdlet cannot remove constant aliases or variables.</span></span>
<span data-ttu-id="3cc02-163">不同提供程序有不同的实现。</span><span class="sxs-lookup"><span data-stu-id="3cc02-163">Implementation varies from provider to provider.</span></span> <span data-ttu-id="3cc02-164">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc02-164">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span> <span data-ttu-id="3cc02-165">即使使用 **Force** 参数，该 cmdlet 也无法覆盖安全限制。</span><span class="sxs-lookup"><span data-stu-id="3cc02-165">Even using the **Force** parameter, the cmdlet cannot override security restrictions.</span></span>

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

### <span data-ttu-id="3cc02-166">-Include</span><span class="sxs-lookup"><span data-stu-id="3cc02-166">-Include</span></span>

<span data-ttu-id="3cc02-167">指定此 cmdlet 将在操作中包含的一个项或多个项（作为一个字符串数组）。</span><span class="sxs-lookup"><span data-stu-id="3cc02-167">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="3cc02-168">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="3cc02-168">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="3cc02-169">请输入路径元素或模式，例如 `"*.txt"`。</span><span class="sxs-lookup"><span data-stu-id="3cc02-169">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="3cc02-170">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="3cc02-170">Wildcard characters are permitted.</span></span> <span data-ttu-id="3cc02-171">仅 **Include** 当命令包括项的内容时（例如 `C:\Windows\*` ，其中的通配符指定目录的内容），Include 参数才有效 `C:\Windows` 。</span><span class="sxs-lookup"><span data-stu-id="3cc02-171">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="3cc02-172">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="3cc02-172">-LiteralPath</span></span>

<span data-ttu-id="3cc02-173">指定一个或多个位置的路径。</span><span class="sxs-lookup"><span data-stu-id="3cc02-173">Specifies a path to one or more locations.</span></span> <span data-ttu-id="3cc02-174">**LiteralPath** 的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="3cc02-174">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="3cc02-175">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="3cc02-175">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="3cc02-176">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="3cc02-176">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="3cc02-177">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="3cc02-177">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="3cc02-178">有关详细信息，请参阅 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc02-178">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="3cc02-179">-Path</span><span class="sxs-lookup"><span data-stu-id="3cc02-179">-Path</span></span>

<span data-ttu-id="3cc02-180">指定要删除的项的路径。</span><span class="sxs-lookup"><span data-stu-id="3cc02-180">Specifies a path of the items being removed.</span></span>
<span data-ttu-id="3cc02-181">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="3cc02-181">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="3cc02-182">-Recurse</span><span class="sxs-lookup"><span data-stu-id="3cc02-182">-Recurse</span></span>

<span data-ttu-id="3cc02-183">指示此 cmdlet 删除指定位置和位置的所有子项中的项。</span><span class="sxs-lookup"><span data-stu-id="3cc02-183">Indicates that this cmdlet deletes the items in the specified locations and in all child items of the locations.</span></span>

<span data-ttu-id="3cc02-184">如果与 **Include** 参数一起使用，则 **递归** 参数可能不会删除所有子文件夹或所有子项。</span><span class="sxs-lookup"><span data-stu-id="3cc02-184">When it is used with the **Include** parameter, the **Recurse** parameter might not delete all subfolders or all child items.</span></span> <span data-ttu-id="3cc02-185">这是一个已知问题。</span><span class="sxs-lookup"><span data-stu-id="3cc02-185">This is a known issue.</span></span> <span data-ttu-id="3cc02-186">作为一种解决方法，请尝试 `Get-ChildItem -Recurse` 将命令结果传递给 `Remove-Item` ，如本主题中的 "示例 4" 中所述。</span><span class="sxs-lookup"><span data-stu-id="3cc02-186">As a workaround, try piping results of the `Get-ChildItem -Recurse` command to `Remove-Item`, as described in "Example 4" in this topic.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3cc02-187">-Stream</span><span class="sxs-lookup"><span data-stu-id="3cc02-187">-Stream</span></span>

<span data-ttu-id="3cc02-188">**Stream** 参数是 FileSystem 提供程序添加到的动态参数 `Remove-Item` 。</span><span class="sxs-lookup"><span data-stu-id="3cc02-188">The **Stream** parameter is a dynamic parameter that the FileSystem provider adds to `Remove-Item`.</span></span>
<span data-ttu-id="3cc02-189">此参数仅在文件系统驱动器中有效。</span><span class="sxs-lookup"><span data-stu-id="3cc02-189">This parameter works only in file system drives.</span></span>

<span data-ttu-id="3cc02-190">您可以使用 `Remove-Item` 删除备用数据流。</span><span class="sxs-lookup"><span data-stu-id="3cc02-190">You can use `Remove-Item` to delete an alternative data stream.</span></span> <span data-ttu-id="3cc02-191">但是，若要取消安全检查（该安全检查可阻止从 Internet 下载的文件），则不建议使用此方法。</span><span class="sxs-lookup"><span data-stu-id="3cc02-191">However, it is not the recommended way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="3cc02-192">如果验证下载的文件是安全的，请使用 `Unblock-File` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3cc02-192">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

<span data-ttu-id="3cc02-193">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="3cc02-193">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3cc02-194">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="3cc02-194">-UseTransaction</span></span>

<span data-ttu-id="3cc02-195">在活动事务中使用该命令。</span><span class="sxs-lookup"><span data-stu-id="3cc02-195">Includes the command in the active transaction.</span></span>
<span data-ttu-id="3cc02-196">仅当正在执行事务时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="3cc02-196">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="3cc02-197">有关详细信息，请参阅 [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)</span><span class="sxs-lookup"><span data-stu-id="3cc02-197">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)</span></span>

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

### <span data-ttu-id="3cc02-198">-Confirm</span><span class="sxs-lookup"><span data-stu-id="3cc02-198">-Confirm</span></span>

<span data-ttu-id="3cc02-199">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="3cc02-199">Prompts you for confirmation before running the cmdlet.</span></span> <span data-ttu-id="3cc02-200">有关详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="3cc02-200">For more information, see the following articles:</span></span>

- [<span data-ttu-id="3cc02-201">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="3cc02-201">about_Preference_Variables</span></span>](../microsoft.powershell.core/about/about_preference_variables.md#confirmpreference)
- [<span data-ttu-id="3cc02-202">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="3cc02-202">about_Functions_CmdletBindingAttribute</span></span>](../microsoft.powershell.core/about/about_functions_cmdletbindingattribute.md?#confirmimpact)

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

### <span data-ttu-id="3cc02-203">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="3cc02-203">-WhatIf</span></span>

<span data-ttu-id="3cc02-204">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="3cc02-204">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="3cc02-205">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="3cc02-205">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="3cc02-206">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3cc02-206">CommonParameters</span></span>

<span data-ttu-id="3cc02-207">此 cmdlet 支持通用参数： `-Debug` 、 `-ErrorAction` 、 `-ErrorVariable` 、、、、、、、 `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` 和 `-WarningVariable` 。</span><span class="sxs-lookup"><span data-stu-id="3cc02-207">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="3cc02-208">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc02-208">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="3cc02-209">输入</span><span class="sxs-lookup"><span data-stu-id="3cc02-209">INPUTS</span></span>

### <span data-ttu-id="3cc02-210">System.String</span><span class="sxs-lookup"><span data-stu-id="3cc02-210">System.String</span></span>

<span data-ttu-id="3cc02-211">可以通过管道将包含路径（但不是文本路径）的字符串传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3cc02-211">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="3cc02-212">输出</span><span class="sxs-lookup"><span data-stu-id="3cc02-212">OUTPUTS</span></span>

### <span data-ttu-id="3cc02-213">无</span><span class="sxs-lookup"><span data-stu-id="3cc02-213">None</span></span>

<span data-ttu-id="3cc02-214">此 cmdlet 不返回任何输出。</span><span class="sxs-lookup"><span data-stu-id="3cc02-214">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="3cc02-215">注释</span><span class="sxs-lookup"><span data-stu-id="3cc02-215">NOTES</span></span>

<span data-ttu-id="3cc02-216">`Remove-Item`Cmdlet 设计用于处理由任何提供程序公开的数据。</span><span class="sxs-lookup"><span data-stu-id="3cc02-216">The `Remove-Item` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="3cc02-217">若要列出会话中可用的提供程序，请键入 `Get-PsProvider`。</span><span class="sxs-lookup"><span data-stu-id="3cc02-217">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="3cc02-218">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc02-218">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

<span data-ttu-id="3cc02-219">如果在不使用 **递归** 参数的情况下尝试删除包含项的文件夹，该 cmdlet 会提示确认。</span><span class="sxs-lookup"><span data-stu-id="3cc02-219">When you try to delete a folder that contains items without using the **Recurse** parameter, the cmdlet prompts for confirmation.</span></span> <span data-ttu-id="3cc02-220">使用不 `-Confirm:$false` 会禁止显示提示。</span><span class="sxs-lookup"><span data-stu-id="3cc02-220">Using `-Confirm:$false` does not suppress the prompt.</span></span> <span data-ttu-id="3cc02-221">这是设计的结果。</span><span class="sxs-lookup"><span data-stu-id="3cc02-221">This is by design.</span></span>

## <span data-ttu-id="3cc02-222">相关链接</span><span class="sxs-lookup"><span data-stu-id="3cc02-222">RELATED LINKS</span></span>

[<span data-ttu-id="3cc02-223">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="3cc02-223">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="3cc02-224">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="3cc02-224">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="3cc02-225">Get-Item</span><span class="sxs-lookup"><span data-stu-id="3cc02-225">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="3cc02-226">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="3cc02-226">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="3cc02-227">Move-Item</span><span class="sxs-lookup"><span data-stu-id="3cc02-227">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="3cc02-228">New-Item</span><span class="sxs-lookup"><span data-stu-id="3cc02-228">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="3cc02-229">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3cc02-229">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="3cc02-230">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="3cc02-230">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="3cc02-231">Set-Item</span><span class="sxs-lookup"><span data-stu-id="3cc02-231">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="3cc02-232">about_Providers</span><span class="sxs-lookup"><span data-stu-id="3cc02-232">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="3cc02-233">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="3cc02-233">about_Preference_Variables</span></span>](../microsoft.powershell.core/about/about_preference_variables.md#confirmpreference)

[<span data-ttu-id="3cc02-234">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="3cc02-234">about_Functions_CmdletBindingAttribute</span></span>](../microsoft.powershell.core/about/about_functions_cmdletbindingattribute.md?#confirmimpact)
