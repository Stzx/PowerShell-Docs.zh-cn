---
external help file: ISE-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: ISE
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/ise/import-isesnippet?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-IseSnippet
ms.openlocfilehash: 810be675fc593f665ccc6f3d5b86ac2f6b633863
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197526"
---
# <span data-ttu-id="c921d-103">Import-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="c921d-103">Import-IseSnippet</span></span>

## <span data-ttu-id="c921d-104">摘要</span><span class="sxs-lookup"><span data-stu-id="c921d-104">SYNOPSIS</span></span>
<span data-ttu-id="c921d-105">将 ISE 代码段导入到当前会话中</span><span class="sxs-lookup"><span data-stu-id="c921d-105">Imports ISE snippets into the current session</span></span>

## <span data-ttu-id="c921d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c921d-106">SYNTAX</span></span>

### <span data-ttu-id="c921d-107">FromFolder（默认值）</span><span class="sxs-lookup"><span data-stu-id="c921d-107">FromFolder (Default)</span></span>

```
Import-IseSnippet [-Path] <String> [-Recurse] [<CommonParameters>]
```

### <span data-ttu-id="c921d-108">FromModule</span><span class="sxs-lookup"><span data-stu-id="c921d-108">FromModule</span></span>

```
Import-IseSnippet [-Recurse] -Module <String> [-ListAvailable] [<CommonParameters>]
```

## <span data-ttu-id="c921d-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c921d-109">DESCRIPTION</span></span>

<span data-ttu-id="c921d-110">该 `Import-IseSnippet` cmdlet 将可重用文本 "代码段" 从模块或目录导入到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="c921d-110">The `Import-IseSnippet` cmdlet imports reusable text "snippets" from a module or a directory into the current session.</span></span> <span data-ttu-id="c921d-111">代码段将立即可供在 Windows PowerShell ISE 中使用。</span><span class="sxs-lookup"><span data-stu-id="c921d-111">The snippets are immediately available for use in Windows PowerShell ISE.</span></span> <span data-ttu-id="c921d-112">此 cmdlet 仅适用于 (ISE) 的 Windows PowerShell 集成脚本环境。</span><span class="sxs-lookup"><span data-stu-id="c921d-112">This cmdlet works only in Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

<span data-ttu-id="c921d-113">若要查看和使用导入的代码段，请从 Windows PowerShell ISE **编辑** "菜单中，单击" **启动代码段** "或按 <kbd>Ctrl</kbd> + <kbd>J</kbd>。</span><span class="sxs-lookup"><span data-stu-id="c921d-113">To view and use the imported snippets, from the Windows PowerShell ISE **Edit** menu, click **Start Snippets** or press <kbd>Ctrl</kbd>+<kbd>J</kbd>.</span></span>

<span data-ttu-id="c921d-114">导入的代码段仅在当前会话中可用。</span><span class="sxs-lookup"><span data-stu-id="c921d-114">Imported snippets are available only in the current session.</span></span> <span data-ttu-id="c921d-115">若要将代码段导入到所有 Windows PowerShell ISE 的会话中，请将 `Import-IseSnippet` 命令添加到 Windows PowerShell 配置文件中，或将代码段文件复制到本地代码段目录 `$home\Documents\WindowsPowershell\Snippets` 。</span><span class="sxs-lookup"><span data-stu-id="c921d-115">To import the snippets into all Windows PowerShell ISE sessions, add an `Import-IseSnippet` command to your Windows PowerShell profile or copy the snippet files to your local snippets directory `$home\Documents\WindowsPowershell\Snippets`.</span></span>

<span data-ttu-id="c921d-116">若要导入代码段，必须在 Windows PowerShell ISE 代码段的代码段 XML 中正确设置代码段格式，并将其保存在 Snippet.ps1xml 文件中。</span><span class="sxs-lookup"><span data-stu-id="c921d-116">To import snippets, they must be properly formatted in the snippet XML for Windows PowerShell ISE snippets and saved in Snippet.ps1xml files.</span></span> <span data-ttu-id="c921d-117">若要创建符合条件的代码段，请使用 `New-IseSnippet` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c921d-117">To create eligible snippets, use the `New-IseSnippet` cmdlet.</span></span> <span data-ttu-id="c921d-118">`New-IseSnippet``<SnippetTitle>.Snippets.ps1xml`在目录中创建文件 `$home\Documents\WindowsPowerShell\Snippets` 。</span><span class="sxs-lookup"><span data-stu-id="c921d-118">`New-IseSnippet` creates a `<SnippetTitle>.Snippets.ps1xml` file in the `$home\Documents\WindowsPowerShell\Snippets` directory.</span></span> <span data-ttu-id="c921d-119">你可以将代码段移动或复制到 Windows PowerShell 模块的 Snippets 目录或任何其他目录。</span><span class="sxs-lookup"><span data-stu-id="c921d-119">You can move or copy the snippets to the Snippets directory of a Windows PowerShell module, or to any other directory.</span></span>

<span data-ttu-id="c921d-120">`Get-IseSnippet`Cmdlet 可在本地代码段目录中获取用户创建的代码段，而不会获取导入的代码段。</span><span class="sxs-lookup"><span data-stu-id="c921d-120">The `Get-IseSnippet` cmdlet, which gets user-created snippets in the local snippets directory, does not get imported snippets.</span></span>

<span data-ttu-id="c921d-121">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c921d-121">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="c921d-122">示例</span><span class="sxs-lookup"><span data-stu-id="c921d-122">EXAMPLES</span></span>

### <span data-ttu-id="c921d-123">示例 1：从目录中导入代码段</span><span class="sxs-lookup"><span data-stu-id="c921d-123">Example 1: Import snippets from a directory</span></span>

<span data-ttu-id="c921d-124">此示例将代码段从目录导入 `\\Server01\Public\Snippets` 到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="c921d-124">This example imports the snippets from the `\\Server01\Public\Snippets` directory into the current session.</span></span> <span data-ttu-id="c921d-125">它使用 **递归** 参数从代码段目录的所有子目录中获取代码片段。</span><span class="sxs-lookup"><span data-stu-id="c921d-125">It uses the **Recurse** parameter to get snippets from all subdirectories of the Snippets directory.</span></span>

```powershell
Import-IseSnippet -Path \\Server01\Public\Snippets -Recurse
```

### <span data-ttu-id="c921d-126">示例 2：从模块中导入代码段</span><span class="sxs-lookup"><span data-stu-id="c921d-126">Example 2: Import snippets from a module</span></span>

<span data-ttu-id="c921d-127">此示例从 **SnippetModule** 模块导入代码段。</span><span class="sxs-lookup"><span data-stu-id="c921d-127">This example imports the snippets from the **SnippetModule** module.</span></span> <span data-ttu-id="c921d-128">该命令使用 **ListAvailable** 参数导入代码段，即使 **SnippetModule** 模块在命令运行时未导入到用户会话中也是如此。</span><span class="sxs-lookup"><span data-stu-id="c921d-128">The command uses the **ListAvailable** parameter to import the snippets even if the **SnippetModule** module is not imported into the user's session when the command runs.</span></span>

```powershell
Import-IseSnippet -Module SnippetModule -ListAvailable
```

### <span data-ttu-id="c921d-129">示例 3：查找模块中的代码段</span><span class="sxs-lookup"><span data-stu-id="c921d-129">Example 3: Find snippets in modules</span></span>

<span data-ttu-id="c921d-130">此示例将获取 PSModulePath 环境变量中所有已安装模块中的代码段。</span><span class="sxs-lookup"><span data-stu-id="c921d-130">This example gets snippets in all installed modules in the PSModulePath environment variable.</span></span>

```powershell
($env:PSModulePath).split(";") |
  ForEach-Object {dir $_\*\Snippets\*.Snippets.ps1xml -ErrorAction SilentlyContinue} |
    ForEach-Object {$_.fullname}
```

### <span data-ttu-id="c921d-131">示例 4：导入所有模块代码段</span><span class="sxs-lookup"><span data-stu-id="c921d-131">Example 4: Import all module snippets</span></span>

<span data-ttu-id="c921d-132">此示例将所有已安装模块中的所有代码段导入到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="c921d-132">This example imports all snippets from all installed modules into the current session.</span></span> <span data-ttu-id="c921d-133">通常，不需要运行如下所示的命令，因为在导入模块时，具有代码段的模块将使用 `Import-IseSnippet` cmdlet 导入这些模块。</span><span class="sxs-lookup"><span data-stu-id="c921d-133">Typically, you don't need to run a command like this because modules that have snippets will use the `Import-IseSnippet` cmdlet to import them for you when the module is imported.</span></span>

```powershell
($env:PSModulePath).split(";") |
  ForEach-Object {dir $_\*\Snippets\*.Snippets.ps1xml -ErrorAction SilentlyContinue} |
    ForEach-Object {$psise.CurrentPowerShellTab.Snippets.Load($_)}
```

### <span data-ttu-id="c921d-134">示例 5：复制所有模块代码段</span><span class="sxs-lookup"><span data-stu-id="c921d-134">Example 5: Copy all module snippets</span></span>

<span data-ttu-id="c921d-135">此示例将所有已安装模块中的代码段文件复制到当前用户的代码段目录。</span><span class="sxs-lookup"><span data-stu-id="c921d-135">This example copies the snippet files from all installed modules into the Snippets directory of the current user.</span></span> <span data-ttu-id="c921d-136">与仅影响当前会话的导入的代码段不同，复制的代码段在每个 Windows PowerShell ISE 会话中都可用。</span><span class="sxs-lookup"><span data-stu-id="c921d-136">Unlike imported snippets, which affect only the current session, copied snippets are available in every Windows PowerShell ISE session.</span></span>

```powershell
($env:PSModulePath).split(";") |
  ForEach-Object {dir $_\*\Snippets\*.Snippets.ps1xml -ErrorAction SilentlyContinue} |
    Copy-Item -Destination $home\Documents\WindowsPowerShell\Snippets
```

## <span data-ttu-id="c921d-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c921d-137">PARAMETERS</span></span>

### <span data-ttu-id="c921d-138">-ListAvailable</span><span class="sxs-lookup"><span data-stu-id="c921d-138">-ListAvailable</span></span>

<span data-ttu-id="c921d-139">指示此 cmdlet 从安装在计算机上的模块中获取代码段，即使这些模块未导入到当前会话中也是如此。</span><span class="sxs-lookup"><span data-stu-id="c921d-139">Indicates that this cmdlet gets snippets from modules that are installed on the computer, even if the modules are not imported into the current session.</span></span> <span data-ttu-id="c921d-140">如果省略此参数，且 **module** 参数指定的模块未导入到当前会话中，则从该模块获取代码段的尝试将失败。</span><span class="sxs-lookup"><span data-stu-id="c921d-140">If this parameter is omitted, and the module that is specified by the **Module** parameter is not imported into the current session, the attempt to get the snippets from the module fails.</span></span>

<span data-ttu-id="c921d-141">仅当命令中使用了 **Module** 参数时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="c921d-141">This parameter is valid only when the **Module** parameter is used in the command.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FromModule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c921d-142">-Module</span><span class="sxs-lookup"><span data-stu-id="c921d-142">-Module</span></span>

<span data-ttu-id="c921d-143">将代码段从指定的模块导入到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="c921d-143">Imports snippets from the specified module into the current session.</span></span> <span data-ttu-id="c921d-144">不支持通配符。</span><span class="sxs-lookup"><span data-stu-id="c921d-144">Wildcard characters are not supported.</span></span>

<span data-ttu-id="c921d-145">此参数从模块路径的代码段子目录中 Snippet.ps1xml 文件导入代码段，如 `$home\Documents\WindowsPowerShell\Modules\<ModuleName>\Snippets` 。</span><span class="sxs-lookup"><span data-stu-id="c921d-145">This parameter imports snippets from Snippet.ps1xml files in the Snippets subdirectory in the module path, such as `$home\Documents\WindowsPowerShell\Modules\<ModuleName>\Snippets`.</span></span>

<span data-ttu-id="c921d-146">此参数旨在供模块作者在启动脚本中使用，例如在模块清单的 **ScriptsToProcess** 项中指定的脚本。</span><span class="sxs-lookup"><span data-stu-id="c921d-146">This parameter is designed to be used by module authors in a startup script, such as a script specified in the **ScriptsToProcess** key of a module manifest.</span></span> <span data-ttu-id="c921d-147">模块中的代码段不会随模块一起自动导入，但你可以使用 `Import-IseSnippet` 命令导入它们。</span><span class="sxs-lookup"><span data-stu-id="c921d-147">Snippets in a module are not automatically imported with the module, but you can use an `Import-IseSnippet` command to import them.</span></span>

```yaml
Type: System.String
Parameter Sets: FromModule
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c921d-148">-Path</span><span class="sxs-lookup"><span data-stu-id="c921d-148">-Path</span></span>

<span data-ttu-id="c921d-149">指定此 cmdlet 在其中导入代码段的代码段目录的路径。</span><span class="sxs-lookup"><span data-stu-id="c921d-149">Specifies the path to the snippets directory in which this cmdlet imports snippets.</span></span>

```yaml
Type: System.String
Parameter Sets: FromFolder
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="c921d-150">-Recurse</span><span class="sxs-lookup"><span data-stu-id="c921d-150">-Recurse</span></span>

<span data-ttu-id="c921d-151">指示此 cmdlet 从 **Path** 参数的值的所有子目录中导入代码段。</span><span class="sxs-lookup"><span data-stu-id="c921d-151">Indicates that this cmdlet imports snippets from all subdirectories of the value of the **Path** parameter.</span></span>

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

### <span data-ttu-id="c921d-152">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c921d-152">CommonParameters</span></span>

<span data-ttu-id="c921d-153">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="c921d-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c921d-154">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="c921d-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c921d-155">输入</span><span class="sxs-lookup"><span data-stu-id="c921d-155">INPUTS</span></span>

### <span data-ttu-id="c921d-156">无</span><span class="sxs-lookup"><span data-stu-id="c921d-156">None</span></span>

<span data-ttu-id="c921d-157">此 cmdlet 不通过管道接受输入。</span><span class="sxs-lookup"><span data-stu-id="c921d-157">This cmdlet does not take input from the pipeline.</span></span>

## <span data-ttu-id="c921d-158">输出</span><span class="sxs-lookup"><span data-stu-id="c921d-158">OUTPUTS</span></span>

### <span data-ttu-id="c921d-159">无</span><span class="sxs-lookup"><span data-stu-id="c921d-159">None</span></span>

<span data-ttu-id="c921d-160">此 cmdlet 将不产生输出。</span><span class="sxs-lookup"><span data-stu-id="c921d-160">This cmdlet does not generate output.</span></span>

## <span data-ttu-id="c921d-161">注释</span><span class="sxs-lookup"><span data-stu-id="c921d-161">NOTES</span></span>

- <span data-ttu-id="c921d-162">不能使用 `Get-IseSnippet` cmdlet 来获取导入的代码段。</span><span class="sxs-lookup"><span data-stu-id="c921d-162">You cannot use the `Get-IseSnippet` cmdlet to get imported snippets.</span></span> <span data-ttu-id="c921d-163">`Get-IseSnippet` 仅获取目录中的代码段 `$home\Documents\WindowsPowerShell\Snippets` 。</span><span class="sxs-lookup"><span data-stu-id="c921d-163">`Get-IseSnippet` gets only snippets in the `$home\Documents\WindowsPowerShell\Snippets` directory.</span></span>
- <span data-ttu-id="c921d-164">`Import-IseSnippet`使用 " **ISESnippetCollection** " 对象的 **Load** 静态方法。</span><span class="sxs-lookup"><span data-stu-id="c921d-164">`Import-IseSnippet` uses the **Load** static method of **Microsoft.PowerShell.Host.ISE.ISESnippetCollection** objects.</span></span> <span data-ttu-id="c921d-165">您还可以在 Windows PowerShell ISE 对象模型中使用代码段的 **Load** 方法： `$psISE.CurrentPowerShellTab.Snippets.Load()`</span><span class="sxs-lookup"><span data-stu-id="c921d-165">You can also use the **Load** method of snippets in the Windows PowerShell ISE object model: `$psISE.CurrentPowerShellTab.Snippets.Load()`</span></span>
- <span data-ttu-id="c921d-166">`New-IseSnippet`Cmdlet 将新的用户创建的代码段存储在 types.ps1xml 文件中。</span><span class="sxs-lookup"><span data-stu-id="c921d-166">The `New-IseSnippet` cmdlet stores new user-created snippets in unsigned .ps1xml files.</span></span> <span data-ttu-id="c921d-167">因此，Windows PowerShell 无法将其加载到执行策略为 **AllSigned** 或 **Restricted** 的会话中。</span><span class="sxs-lookup"><span data-stu-id="c921d-167">As such, Windows PowerShell cannot load them into a session in which the execution policy is **AllSigned** or **Restricted** .</span></span> <span data-ttu-id="c921d-168">在 **Restricted** 或 **AllSigned** 会话中，你可以创建、获取和导入用户创建的未签名代码段，但无法在会话中使用它们。</span><span class="sxs-lookup"><span data-stu-id="c921d-168">In a **Restricted** or **AllSigned** session, you can create, get, and import unsigned user-created snippets, but you cannot use them in the session.</span></span>

  <span data-ttu-id="c921d-169">若要使用 cmdlet 返回的未签名用户创建的代码段 `Import-IseSnippet` ，请更改执行策略，然后重新启动 Windows PowerShell ISE。</span><span class="sxs-lookup"><span data-stu-id="c921d-169">To use unsigned user-created snippets that the `Import-IseSnippet` cmdlet returns, change the execution policy, and then restart Windows PowerShell ISE.</span></span>

  <span data-ttu-id="c921d-170">有关 Windows PowerShell 执行策略的详细信息，请参阅 [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c921d-170">For more information about Windows PowerShell execution policies, see [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).</span></span>

## <span data-ttu-id="c921d-171">相关链接</span><span class="sxs-lookup"><span data-stu-id="c921d-171">RELATED LINKS</span></span>

[<span data-ttu-id="c921d-172">Get-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="c921d-172">Get-IseSnippet</span></span>](Get-IseSnippet.md)

[<span data-ttu-id="c921d-173">New-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="c921d-173">New-IseSnippet</span></span>](New-IseSnippet.md)
