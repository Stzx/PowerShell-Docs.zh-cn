---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/split-path?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Split-Path
ms.openlocfilehash: 5d92acbe080b0d232047f1184c9a369b8837845c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198030"
---
# <span data-ttu-id="8b878-103">Split-Path</span><span class="sxs-lookup"><span data-stu-id="8b878-103">Split-Path</span></span>

## <span data-ttu-id="8b878-104">摘要</span><span class="sxs-lookup"><span data-stu-id="8b878-104">SYNOPSIS</span></span>
<span data-ttu-id="8b878-105">返回指定的路径部分。</span><span class="sxs-lookup"><span data-stu-id="8b878-105">Returns the specified part of a path.</span></span>

## <span data-ttu-id="8b878-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8b878-106">SYNTAX</span></span>

### <span data-ttu-id="8b878-107">ParentSet（默认值）</span><span class="sxs-lookup"><span data-stu-id="8b878-107">ParentSet (Default)</span></span>

```
Split-Path [-Path] <String[]> [-Parent] [-Resolve] [-Credential <PSCredential>] [-UseTransaction]
 [<CommonParameters>]
```

### <span data-ttu-id="8b878-108">NoQualifierSet</span><span class="sxs-lookup"><span data-stu-id="8b878-108">NoQualifierSet</span></span>

```
Split-Path [-Path] <String[]> [-NoQualifier] [-Resolve] [-Credential <PSCredential>] [-UseTransaction]
 [<CommonParameters>]
```

### <span data-ttu-id="8b878-109">LeafSet</span><span class="sxs-lookup"><span data-stu-id="8b878-109">LeafSet</span></span>

```
Split-Path [-Path] <String[]> [-Leaf] [-Resolve] [-Credential <PSCredential>] [-UseTransaction]
 [<CommonParameters>]
```

### <span data-ttu-id="8b878-110">QualifierSet</span><span class="sxs-lookup"><span data-stu-id="8b878-110">QualifierSet</span></span>

```
Split-Path [-Path] <String[]> [-Qualifier] [-Resolve] [-Credential <PSCredential>] [-UseTransaction]
 [<CommonParameters>]
```

### <span data-ttu-id="8b878-111">IsAbsoluteSet</span><span class="sxs-lookup"><span data-stu-id="8b878-111">IsAbsoluteSet</span></span>

```
Split-Path [-Path] <String[]> [-Resolve] [-IsAbsolute] [-Credential <PSCredential>] [-UseTransaction]
 [<CommonParameters>]
```

### <span data-ttu-id="8b878-112">LiteralPathSet</span><span class="sxs-lookup"><span data-stu-id="8b878-112">LiteralPathSet</span></span>

```
Split-Path -LiteralPath <String[]> [-Resolve] [-Credential <PSCredential>] [-UseTransaction]
 [<CommonParameters>]
```

## <span data-ttu-id="8b878-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8b878-113">DESCRIPTION</span></span>

<span data-ttu-id="8b878-114">**拆分路径** cmdlet 仅返回路径的指定部分，如父文件夹、子文件夹或文件名。</span><span class="sxs-lookup"><span data-stu-id="8b878-114">The **Split-Path** cmdlet returns only the specified part of a path, such as the parent folder, a subfolder, or a file name.</span></span>
<span data-ttu-id="8b878-115">它也可以获取拆分路径所引用的项，并指示该路径是相对路径还是绝对路径。</span><span class="sxs-lookup"><span data-stu-id="8b878-115">It can also get items that are referenced by the split path and tell whether the path is relative or absolute.</span></span>

<span data-ttu-id="8b878-116">使用此 cmdlet 可以只获取或只提交路径的选定部分。</span><span class="sxs-lookup"><span data-stu-id="8b878-116">You can use this cmdlet to get or submit only a selected part of a path.</span></span>

## <span data-ttu-id="8b878-117">示例</span><span class="sxs-lookup"><span data-stu-id="8b878-117">EXAMPLES</span></span>

### <span data-ttu-id="8b878-118">示例1：获取路径的限定符</span><span class="sxs-lookup"><span data-stu-id="8b878-118">Example 1: Get the qualifier of a path</span></span>

```
PS C:\> Split-Path -Path "HKCU:\Software\Microsoft" -Qualifier
HKCU:
```

<span data-ttu-id="8b878-119">此命令只返回路径的限定符。</span><span class="sxs-lookup"><span data-stu-id="8b878-119">This command returns only the qualifier of the path.</span></span>
<span data-ttu-id="8b878-120">限定符是驱动器。</span><span class="sxs-lookup"><span data-stu-id="8b878-120">The qualifier is the drive.</span></span>

### <span data-ttu-id="8b878-121">示例2：显示文件名</span><span class="sxs-lookup"><span data-stu-id="8b878-121">Example 2: Display file names</span></span>

```
PS C:\> Split-Path -Path "C:\Test\Logs\*.log" -Leaf -Resolve
Pass1.log
Pass2.log
...
```

<span data-ttu-id="8b878-122">此命令显示拆分路径所引用的文件。</span><span class="sxs-lookup"><span data-stu-id="8b878-122">This command displays the files that are referenced by the split path.</span></span>
<span data-ttu-id="8b878-123">由于此路径拆分为最后一项，也称为叶，因此该命令只显示文件名。</span><span class="sxs-lookup"><span data-stu-id="8b878-123">Because this path is split to the last item, also known as the leaf, the command displays only the file names.</span></span>

<span data-ttu-id="8b878-124">*Resolve* 参数指示 **拆分** 路径显示拆分路径所引用的项，而不是显示拆分路径。</span><span class="sxs-lookup"><span data-stu-id="8b878-124">The *Resolve* parameter tells **Split-Path** to display the items that the split path references, instead of displaying the split path.</span></span>

<span data-ttu-id="8b878-125">与所有 **拆分路径** 命令一样，此命令将返回字符串。</span><span class="sxs-lookup"><span data-stu-id="8b878-125">Like all **Split-Path** commands, this command returns strings.</span></span>
<span data-ttu-id="8b878-126">它不返回表示文件的 **FileInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="8b878-126">It does not return **FileInfo** objects that represent the files.</span></span>

### <span data-ttu-id="8b878-127">示例3：获取父容器</span><span class="sxs-lookup"><span data-stu-id="8b878-127">Example 3: Get the parent container</span></span>

```
PS C:\> Split-Path -Path "C:\WINDOWS\system32\WindowsPowerShell\V1.0\about_*.txt"
C:\WINDOWS\system32\WindowsPowerShell\V1.0
```

<span data-ttu-id="8b878-128">此命令只返回路径的父容器。</span><span class="sxs-lookup"><span data-stu-id="8b878-128">This command returns only the parent containers of the path.</span></span>
<span data-ttu-id="8b878-129">由于它不包括任何用于指定拆分的参数，因此 **拆分路径** 将使用拆分位置默认值（即 *父级* ）。</span><span class="sxs-lookup"><span data-stu-id="8b878-129">Because it does not include any parameters to specify the split, **Split-Path** uses the split location default, which is *Parent* .</span></span>

### <span data-ttu-id="8b878-130">示例4：确定路径是否为绝对路径</span><span class="sxs-lookup"><span data-stu-id="8b878-130">Example 4: Determines whether a path is absolute</span></span>

```
PS C:\> Split-Path -Path ".\My Pictures\*.jpg" -IsAbsolute
False
```

<span data-ttu-id="8b878-131">此命令确定路径是相对路径还是绝对路径。</span><span class="sxs-lookup"><span data-stu-id="8b878-131">This command determines whether the path is relative or absolute.</span></span>
<span data-ttu-id="8b878-132">在这种情况下，因为路径相对于当前文件夹（由点 )  ( 表示），所以，它返回 $False。</span><span class="sxs-lookup"><span data-stu-id="8b878-132">In this case, because the path is relative to the current folder, which is represented by a dot (.), it returns $False.</span></span>

### <span data-ttu-id="8b878-133">示例5：将位置更改为指定路径</span><span class="sxs-lookup"><span data-stu-id="8b878-133">Example 5: Change location to a specified path</span></span>

```
PS C:\> Set-Location (Split-Path -Path $profile)
PS C:\Documents and Settings\User01\My Documents\WindowsPowerShell>
```

<span data-ttu-id="8b878-134">此命令将你的位置更改为包含 PowerShell 配置文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="8b878-134">This command changes your location to the folder that contains the PowerShell profile.</span></span>

<span data-ttu-id="8b878-135">括号中的命令使用 **拆分路径** 来仅返回内置 $Profile 变量中存储的路径的父路径。</span><span class="sxs-lookup"><span data-stu-id="8b878-135">The command in parentheses uses **Split-Path** to return only the parent of the path stored in the built-in $Profile variable.</span></span>
<span data-ttu-id="8b878-136">*Parent* 参数是默认的拆分位置参数。</span><span class="sxs-lookup"><span data-stu-id="8b878-136">The *Parent* parameter is the default split location parameter.</span></span>
<span data-ttu-id="8b878-137">因此，你可以从命令中省略它。</span><span class="sxs-lookup"><span data-stu-id="8b878-137">Therefore, you can omit it from the command.</span></span>
<span data-ttu-id="8b878-138">圆括号直接 PowerShell 以首先运行命令。</span><span class="sxs-lookup"><span data-stu-id="8b878-138">The parentheses direct PowerShell to run the command first.</span></span>
<span data-ttu-id="8b878-139">这是一种移动到具有长路径名称的文件夹的有效方法。</span><span class="sxs-lookup"><span data-stu-id="8b878-139">This is a useful way to move to a folder that has a long path name.</span></span>

### <span data-ttu-id="8b878-140">示例6：使用管道拆分路径</span><span class="sxs-lookup"><span data-stu-id="8b878-140">Example 6: Split a path by using the pipeline</span></span>

```
PS C:\> 'C:\Documents and Settings\User01\My Documents\My Pictures' | Split-Path
C:\Documents and Settings\User01\My Documents
```

<span data-ttu-id="8b878-141">此命令使用管道运算符 (|) 将路径发送到 **拆分路径** 。</span><span class="sxs-lookup"><span data-stu-id="8b878-141">This command uses a pipeline operator (|) to send a path to **Split-Path** .</span></span>
<span data-ttu-id="8b878-142">路径用引号引起以指示它是一个标记。</span><span class="sxs-lookup"><span data-stu-id="8b878-142">The path is enclosed in quotation marks to indicate that it is a single token.</span></span>

## <span data-ttu-id="8b878-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8b878-143">PARAMETERS</span></span>

### <span data-ttu-id="8b878-144">-Credential</span><span class="sxs-lookup"><span data-stu-id="8b878-144">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="8b878-145">随 PowerShell 一起安装的任何提供程序都不支持此参数。</span><span class="sxs-lookup"><span data-stu-id="8b878-145">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="8b878-146">若要在运行此 cmdlet 时模拟其他用户或提升凭据，请使用 [Invoke 命令](../Microsoft.PowerShell.Core/Invoke-Command.md)。</span><span class="sxs-lookup"><span data-stu-id="8b878-146">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8b878-147">-IsAbsolute</span><span class="sxs-lookup"><span data-stu-id="8b878-147">-IsAbsolute</span></span>

<span data-ttu-id="8b878-148">指示如果路径为绝对路径，则此 cmdlet 返回 $True; 如果路径是相对路径，则为 $False。</span><span class="sxs-lookup"><span data-stu-id="8b878-148">Indicates that this cmdlet returns $True if the path is absolute and $False if it is relative.</span></span>
<span data-ttu-id="8b878-149">绝对路径的长度大于零，并且不使用点 (。 ) 指示当前路径。</span><span class="sxs-lookup"><span data-stu-id="8b878-149">An absolute path has a length greater than zero and does not use a dot (.) to indicate the current path.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: IsAbsoluteSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8b878-150">-Leaf</span><span class="sxs-lookup"><span data-stu-id="8b878-150">-Leaf</span></span>

<span data-ttu-id="8b878-151">指示此 cmdlet 仅返回路径中的最后一项或容器。</span><span class="sxs-lookup"><span data-stu-id="8b878-151">Indicates that this cmdlet returns only the last item or container in the path.</span></span>
<span data-ttu-id="8b878-152">例如，在路径中 `C:\Test\Logs\Pass1.log` ，它仅返回 pass1.log。</span><span class="sxs-lookup"><span data-stu-id="8b878-152">For example, in the path `C:\Test\Logs\Pass1.log`, it returns only Pass1.log.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LeafSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8b878-153">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="8b878-153">-LiteralPath</span></span>

<span data-ttu-id="8b878-154">指定要拆分的路径。</span><span class="sxs-lookup"><span data-stu-id="8b878-154">Specifies the paths to be split.</span></span>
<span data-ttu-id="8b878-155">不同于 *Path* ， *LiteralPath* 的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="8b878-155">Unlike *Path* , the value of *LiteralPath* is used exactly as it is typed.</span></span>
<span data-ttu-id="8b878-156">不会将任何字符解释为通配字符。</span><span class="sxs-lookup"><span data-stu-id="8b878-156">No characters are interpreted as wildcard characters.</span></span>
<span data-ttu-id="8b878-157">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="8b878-157">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="8b878-158">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="8b878-158">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPathSet
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8b878-159">-NoQualifier</span><span class="sxs-lookup"><span data-stu-id="8b878-159">-NoQualifier</span></span>

<span data-ttu-id="8b878-160">指示此 cmdlet 返回无限定符的路径。</span><span class="sxs-lookup"><span data-stu-id="8b878-160">Indicates that this cmdlet returns the path without the qualifier.</span></span>
<span data-ttu-id="8b878-161">对于 FileSystem 或 Registry 提供程序，限定符是提供程序路径的驱动器，例如，C: 或 HKCU:。</span><span class="sxs-lookup"><span data-stu-id="8b878-161">For the FileSystem or registry providers, the qualifier is the drive of the provider path, such as C: or HKCU:.</span></span>
<span data-ttu-id="8b878-162">例如，在路径中 `C:\Test\Logs\Pass1.log` ，它仅返回 \Test\Logs\Pass1.log。</span><span class="sxs-lookup"><span data-stu-id="8b878-162">For example, in the path `C:\Test\Logs\Pass1.log`, it returns only \Test\Logs\Pass1.log.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NoQualifierSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8b878-163">-Parent</span><span class="sxs-lookup"><span data-stu-id="8b878-163">-Parent</span></span>

<span data-ttu-id="8b878-164">指示此 cmdlet 仅返回项或路径指定的容器的父容器。</span><span class="sxs-lookup"><span data-stu-id="8b878-164">Indicates that this cmdlet returns only the parent containers of the item or of the container specified by the path.</span></span>
<span data-ttu-id="8b878-165">例如，在路径中 `C:\Test\Logs\Pass1.log` ，它返回 C:\Test\Logs。</span><span class="sxs-lookup"><span data-stu-id="8b878-165">For example, in the path `C:\Test\Logs\Pass1.log`, it returns C:\Test\Logs.</span></span>
<span data-ttu-id="8b878-166">*Parent* 参数是默认的拆分位置参数。</span><span class="sxs-lookup"><span data-stu-id="8b878-166">The *Parent* parameter is the default split location parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ParentSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8b878-167">-Path</span><span class="sxs-lookup"><span data-stu-id="8b878-167">-Path</span></span>

<span data-ttu-id="8b878-168">指定要拆分的路径。</span><span class="sxs-lookup"><span data-stu-id="8b878-168">Specifies the paths to be split.</span></span>
<span data-ttu-id="8b878-169">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="8b878-169">Wildcard characters are permitted.</span></span>
<span data-ttu-id="8b878-170">如果路径包括空格，请将其括在引号中。</span><span class="sxs-lookup"><span data-stu-id="8b878-170">If the path includes spaces, enclose it in quotation marks.</span></span>
<span data-ttu-id="8b878-171">还可以通过管道将路径传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8b878-171">You can also pipe a path to this cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ParentSet, NoQualifierSet, LeafSet, QualifierSet, IsAbsoluteSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="8b878-172">-Qualifier</span><span class="sxs-lookup"><span data-stu-id="8b878-172">-Qualifier</span></span>

<span data-ttu-id="8b878-173">指示此 cmdlet 仅返回指定路径的限定符。</span><span class="sxs-lookup"><span data-stu-id="8b878-173">Indicates that this cmdlet returns only the qualifier of the specified path.</span></span>
<span data-ttu-id="8b878-174">对于 FileSystem 或 Registry 提供程序，限定符是提供程序路径的驱动器，例如，C: 或 HKCU:。</span><span class="sxs-lookup"><span data-stu-id="8b878-174">For the FileSystem or registry providers, the qualifier is the drive of the provider path, such as C: or HKCU:.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: QualifierSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8b878-175">-Resolve</span><span class="sxs-lookup"><span data-stu-id="8b878-175">-Resolve</span></span>

<span data-ttu-id="8b878-176">指示此 cmdlet 显示生成的拆分路径所引用的项，而不是显示路径元素。</span><span class="sxs-lookup"><span data-stu-id="8b878-176">Indicates that this cmdlet displays the items that are referenced by the resulting split path instead of displaying the path elements.</span></span>

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

### <span data-ttu-id="8b878-177">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="8b878-177">-UseTransaction</span></span>

<span data-ttu-id="8b878-178">在活动事务中使用该命令。</span><span class="sxs-lookup"><span data-stu-id="8b878-178">Includes the command in the active transaction.</span></span>
<span data-ttu-id="8b878-179">仅当正在执行事务时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="8b878-179">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="8b878-180">有关详细信息，请参阅 about_Transactions。</span><span class="sxs-lookup"><span data-stu-id="8b878-180">For more information, see about_Transactions.</span></span>

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

### <span data-ttu-id="8b878-181">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8b878-181">CommonParameters</span></span>

<span data-ttu-id="8b878-182">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="8b878-182">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8b878-183">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="8b878-183">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8b878-184">输入</span><span class="sxs-lookup"><span data-stu-id="8b878-184">INPUTS</span></span>

### <span data-ttu-id="8b878-185">System.String</span><span class="sxs-lookup"><span data-stu-id="8b878-185">System.String</span></span>

<span data-ttu-id="8b878-186">可以通过管道将包含路径的字符串传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8b878-186">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="8b878-187">输出</span><span class="sxs-lookup"><span data-stu-id="8b878-187">OUTPUTS</span></span>

### <span data-ttu-id="8b878-188">System.String、System.Boolean</span><span class="sxs-lookup"><span data-stu-id="8b878-188">System.String, System.Boolean</span></span>

<span data-ttu-id="8b878-189">**拆分路径** 返回文本字符串。</span><span class="sxs-lookup"><span data-stu-id="8b878-189">**Split-Path** returns text strings.</span></span>
<span data-ttu-id="8b878-190">当你指定 *Resolve* 参数时， **拆分路径** 将返回描述项位置的字符串;它不返回表示项的对象，如 **FileInfo** 或 **RegistryKey** 对象。</span><span class="sxs-lookup"><span data-stu-id="8b878-190">When you specify the *Resolve* parameter, **Split-Path** returns a string that describes the location of the items; it does not return objects that represent the items, such as a **FileInfo** or **RegistryKey** object.</span></span>

<span data-ttu-id="8b878-191">指定 *IsAbsolute* 参数时， **拆分路径** 将返回一个 **布尔** 值。</span><span class="sxs-lookup"><span data-stu-id="8b878-191">When you specify the *IsAbsolute* parameter, **Split-Path** returns a **Boolean** value.</span></span>

## <span data-ttu-id="8b878-192">注释</span><span class="sxs-lookup"><span data-stu-id="8b878-192">NOTES</span></span>

* <span data-ttu-id="8b878-193"> ( *限定符* 、 *Parent* 、 *叶* 和 *NoQualifier* ) 的拆分位置参数是互斥的。</span><span class="sxs-lookup"><span data-stu-id="8b878-193">The split location parameters ( *Qualifier* , *Parent* , *Leaf* , and *NoQualifier* ) are exclusive.</span></span> <span data-ttu-id="8b878-194">在每个命令中只能使用一个参数。</span><span class="sxs-lookup"><span data-stu-id="8b878-194">You can use only one in each command.</span></span>

  <span data-ttu-id="8b878-195">包含路径 cmdlet (路径 **名词的** cmdlet) **使用路径名，** 并以所有 PowerShell 提供程序可解释的简洁格式返回名称。</span><span class="sxs-lookup"><span data-stu-id="8b878-195">The cmdlets that contain the **Path** noun (the **Path** cmdlets) work with path names and return the names in a concise format that all PowerShell providers can interpret.</span></span>
<span data-ttu-id="8b878-196">这些 cmdlet 用于需要在其中以特定格式显示全部或部分路径名称的程序或脚本中。</span><span class="sxs-lookup"><span data-stu-id="8b878-196">They are designed for use in programs and scripts where you want to display all or part of a path name in a particular format.</span></span>
<span data-ttu-id="8b878-197">使用 **Dirname** 、 **Normpath** 、 **Realpath** 、 **Join** 或其他路径操控器的方式来使用它们。</span><span class="sxs-lookup"><span data-stu-id="8b878-197">Use them in the way that you would use **Dirname** , **Normpath** , **Realpath** , **Join** , or other path manipulators.</span></span>

  <span data-ttu-id="8b878-198">可以将 **路径** cmdlet 与多个提供程序一起使用。</span><span class="sxs-lookup"><span data-stu-id="8b878-198">You can use the **Path** cmdlets together with several providers.</span></span>
<span data-ttu-id="8b878-199">其中包括 FileSystem、Registry 和 Certificate 提供程序。</span><span class="sxs-lookup"><span data-stu-id="8b878-199">These include the FileSystem, Registry, and Certificate providers.</span></span>

  <span data-ttu-id="8b878-200">**拆分路径** 用于处理由任何提供程序公开的数据。</span><span class="sxs-lookup"><span data-stu-id="8b878-200">**Split-Path** is designed to work with the data exposed by any provider.</span></span>
<span data-ttu-id="8b878-201">若要列出会话中可用的提供程序，请键入 `Get-PSProvider`。</span><span class="sxs-lookup"><span data-stu-id="8b878-201">To list the providers available in your session, type `Get-PSProvider`.</span></span>
<span data-ttu-id="8b878-202">有关详细信息，请参阅 about_Providers。</span><span class="sxs-lookup"><span data-stu-id="8b878-202">For more information, see about_Providers.</span></span>

## <span data-ttu-id="8b878-203">相关链接</span><span class="sxs-lookup"><span data-stu-id="8b878-203">RELATED LINKS</span></span>

[<span data-ttu-id="8b878-204">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="8b878-204">Convert-Path</span></span>](Convert-Path.md)

[<span data-ttu-id="8b878-205">Join-Path</span><span class="sxs-lookup"><span data-stu-id="8b878-205">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="8b878-206">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="8b878-206">Resolve-Path</span></span>](Resolve-Path.md)

[<span data-ttu-id="8b878-207">Test-Path</span><span class="sxs-lookup"><span data-stu-id="8b878-207">Test-Path</span></span>](Test-Path.md)
