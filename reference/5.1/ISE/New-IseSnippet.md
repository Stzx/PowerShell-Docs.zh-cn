---
external help file: ISE-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: ISE
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/ise/new-isesnippet?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-IseSnippet
ms.openlocfilehash: 0ed1c2913fc7531574bfbdd435a002d60931d24a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197525"
---
# <span data-ttu-id="289a4-103">New-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="289a4-103">New-IseSnippet</span></span>

## <span data-ttu-id="289a4-104">摘要</span><span class="sxs-lookup"><span data-stu-id="289a4-104">SYNOPSIS</span></span>
<span data-ttu-id="289a4-105">创建 Windows PowerShell ISE 代码段。</span><span class="sxs-lookup"><span data-stu-id="289a4-105">Creates a Windows PowerShell ISE code snippet.</span></span>

## <span data-ttu-id="289a4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="289a4-106">SYNTAX</span></span>

```
New-IseSnippet [-Title] <String> [-Description] <String> [-Text] <String> [-Author <String>]
 [-CaretOffset <Int32>] [-Force] [<CommonParameters>]
```

## <span data-ttu-id="289a4-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="289a4-107">DESCRIPTION</span></span>

<span data-ttu-id="289a4-108">`New-ISESnippet`Cmdlet 可为 Windows PowerShell ISE 创建可重用文本 "代码段"。</span><span class="sxs-lookup"><span data-stu-id="289a4-108">The `New-ISESnippet` cmdlet creates a reusable text "snippet" for Windows PowerShell ISE.</span></span> <span data-ttu-id="289a4-109">你可以使用代码段将文本添加到 Windows PowerShell ISE 中的“脚本”窗格或“命令”窗格。</span><span class="sxs-lookup"><span data-stu-id="289a4-109">You can use snippets to add text to the Script pane or Command pane in Windows PowerShell ISE.</span></span> <span data-ttu-id="289a4-110">此 cmdlet 仅在 Windows PowerShell ISE 中可用。</span><span class="sxs-lookup"><span data-stu-id="289a4-110">This cmdlet is available only in Windows PowerShell ISE.</span></span>

<span data-ttu-id="289a4-111">从 Windows PowerShell 3.0 开始，Windows PowerShell ISE 包括内置代码段集合。</span><span class="sxs-lookup"><span data-stu-id="289a4-111">Beginning in Windows PowerShell 3.0, Windows PowerShell ISE includes a collection of built-in snippets.</span></span> <span data-ttu-id="289a4-112">`New-ISESnippet`Cmdlet 可让你创建自己的代码段以添加到内置集合。</span><span class="sxs-lookup"><span data-stu-id="289a4-112">The `New-ISESnippet` cmdlet lets you create your own snippets to add to the built-in collection.</span></span> <span data-ttu-id="289a4-113">你可以查看、更改、添加、删除和共享代码段文件，并将其包含在 Windows PowerShell 模块中。</span><span class="sxs-lookup"><span data-stu-id="289a4-113">You can view, change, add, delete, and share snippet files and include them in Windows PowerShell modules.</span></span> <span data-ttu-id="289a4-114">若要查看 Windows PowerShell ISE 中的代码段，请在 " **编辑** " 菜单中选择 " **启动代码段** " 或按 <kbd>CTRL</kbd> + <kbd>J</kbd>。</span><span class="sxs-lookup"><span data-stu-id="289a4-114">To see snippets in Windows PowerShell ISE, from the **Edit** menu, select **Start Snippets** or press <kbd>CTRL</kbd>+<kbd>J</kbd>.</span></span>

<span data-ttu-id="289a4-115">`New-ISESnippet`Cmdlet `<Title>.Snippets.ps1xml` 在目录中创建一个文件，该文件 `$home\Documents\WindowsPowerShell\Snippets` 具有你指定的标题。</span><span class="sxs-lookup"><span data-stu-id="289a4-115">The `New-ISESnippet` cmdlet creates a `<Title>.Snippets.ps1xml` file in the `$home\Documents\WindowsPowerShell\Snippets` directory with the title that you specify.</span></span> <span data-ttu-id="289a4-116">若要将代码段文件包含在你创作的模块中，请将代码段文件添加到模块目录的代码段子目录。</span><span class="sxs-lookup"><span data-stu-id="289a4-116">To include a snippet file in a module that you are authoring, add the snippet file to a Snippets subdirectory of your module directory.</span></span>

<span data-ttu-id="289a4-117">不能在执行策略受到 **限制** 或 **AllSigned** 的会话中使用用户创建的代码段。</span><span class="sxs-lookup"><span data-stu-id="289a4-117">You cannot use user-created snippets in a session in which the execution policy is **Restricted** or **AllSigned** .</span></span>

<span data-ttu-id="289a4-118">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="289a4-118">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="289a4-119">示例</span><span class="sxs-lookup"><span data-stu-id="289a4-119">EXAMPLES</span></span>

### <span data-ttu-id="289a4-120">示例1：创建 Comment-Based 帮助代码段</span><span class="sxs-lookup"><span data-stu-id="289a4-120">Example 1: Create a Comment-Based help snippet</span></span>

```
New-IseSnippet -Title Comment-BasedHelp -Description "A template for comment-based help." -Text "<#
    .SYNOPSIS

    .DESCRIPTION
    .PARAMETER  <Parameter-Name>
    .INPUTS
    .OUTPUTS
    .EXAMPLE
    .LINK
#>"
```

<span data-ttu-id="289a4-121">此命令将为 Windows PowerShell ISE 创建一个 Comment-BasedHelp 代码段。</span><span class="sxs-lookup"><span data-stu-id="289a4-121">This command creates a Comment-BasedHelp snippet for Windows PowerShell ISE.</span></span> <span data-ttu-id="289a4-122">它 `Comment-BasedHelp.snippets.ps1xml` 在用户的代码段目录中创建名为的文件 `$home\Documents\WindowsPowerShell\Snippets` 。</span><span class="sxs-lookup"><span data-stu-id="289a4-122">It creates a file named `Comment-BasedHelp.snippets.ps1xml` in the user's Snippets directory `$home\Documents\WindowsPowerShell\Snippets`.</span></span>

### <span data-ttu-id="289a4-123">示例2：创建必需的代码段</span><span class="sxs-lookup"><span data-stu-id="289a4-123">Example 2: Create a mandatory snippet</span></span>

```
$M = @'
Param
(
  [parameter(Mandatory=$true)]
  [String[]]
  $<ParameterName>
)
'@

New-ISESnippet -Text $M -Title Mandatory -Description "Adds a mandatory function parameter." -Author "Patti Fuller, Fabrikam Corp." -Force
```

<span data-ttu-id="289a4-124">此示例将创建一个名为 " **强制** " Windows PowerShell ISE 的代码段。</span><span class="sxs-lookup"><span data-stu-id="289a4-124">This example creates a snippet named **Mandatory** for Windows PowerShell ISE.</span></span> <span data-ttu-id="289a4-125">第一个命令将代码段文本保存在 `$M` 变量中。</span><span class="sxs-lookup"><span data-stu-id="289a4-125">The first command saves the snippet text in the `$M` variable.</span></span> <span data-ttu-id="289a4-126">第二个命令使用 `New-ISESnippet` cmdlet 创建代码片段。</span><span class="sxs-lookup"><span data-stu-id="289a4-126">The second command uses the `New-ISESnippet` cmdlet to create the snippet.</span></span> <span data-ttu-id="289a4-127">该命令使用 **Force** 参数来采用相同名称重写上一个代码段。</span><span class="sxs-lookup"><span data-stu-id="289a4-127">The command uses the **Force** parameter to overwrite a previous snippet with the same name.</span></span>

### <span data-ttu-id="289a4-128">示例3：将必需的代码片段从文件夹复制到目标文件夹</span><span class="sxs-lookup"><span data-stu-id="289a4-128">Example 3: Copy a mandatory snippet from a folder to a destination folder</span></span>

```
Copy-Item "$Home\Documents\WindowsPowerShell\Snippets\Mandatory.Snippets.ps1xml" -Destination "\\Server\Share"
```

<span data-ttu-id="289a4-129">此命令使用 `Copy-Item` cmdlet 从文件夹中将 **强制** 代码段复制 `New-ISESnippet` 到 Server\Share 文件共享。</span><span class="sxs-lookup"><span data-stu-id="289a4-129">This command uses the `Copy-Item` cmdlet to copy the **Mandatory** snippet from the folder where `New-ISESnippet` places it to the Server\Share file share.</span></span>

## <span data-ttu-id="289a4-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="289a4-130">PARAMETERS</span></span>

### <span data-ttu-id="289a4-131">-作者</span><span class="sxs-lookup"><span data-stu-id="289a4-131">-Author</span></span>

<span data-ttu-id="289a4-132">指定代码段的作者。</span><span class="sxs-lookup"><span data-stu-id="289a4-132">Specifies the author of the snippet.</span></span> <span data-ttu-id="289a4-133">作者字段将显示在代码段文件中，但当你在 Windows PowerShell ISE 中单击代码段名称时，不会显示该字段。</span><span class="sxs-lookup"><span data-stu-id="289a4-133">The author field appears in the snippet file, but it does not appear when you click the snippet name in Windows PowerShell ISE.</span></span>

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

### <span data-ttu-id="289a4-134">-CaretOffset</span><span class="sxs-lookup"><span data-stu-id="289a4-134">-CaretOffset</span></span>

<span data-ttu-id="289a4-135">指定此 cmdlet 将光标置于其上的代码段文本的字符。</span><span class="sxs-lookup"><span data-stu-id="289a4-135">Specifies the character of the snippet text that this cmdlet places the cursor on.</span></span> <span data-ttu-id="289a4-136">输入一个表示光标位置的整数，其中“1”表示文本的第一个字符。</span><span class="sxs-lookup"><span data-stu-id="289a4-136">Enter an integer that represents the cursor position, with "1" representing the first character of text.</span></span> <span data-ttu-id="289a4-137">默认值 0（零）将光标紧接在文本的第一个字符之前。</span><span class="sxs-lookup"><span data-stu-id="289a4-137">The default value, 0 (zero), places the cursor immediately before the first character of text.</span></span> <span data-ttu-id="289a4-138">此参数不会缩进代码段文本。</span><span class="sxs-lookup"><span data-stu-id="289a4-138">This parameter does not indent the snippet text.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="289a4-139">-Description</span><span class="sxs-lookup"><span data-stu-id="289a4-139">-Description</span></span>

<span data-ttu-id="289a4-140">指定代码段的说明。</span><span class="sxs-lookup"><span data-stu-id="289a4-140">Specifies a description of the snippet.</span></span> <span data-ttu-id="289a4-141">当你在 Windows PowerShell ISE 中单击代码段名称时，将显示说明值。</span><span class="sxs-lookup"><span data-stu-id="289a4-141">The description value appears when you click the snippet name in Windows PowerShell ISE.</span></span> <span data-ttu-id="289a4-142">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="289a4-142">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="289a4-143">-Force</span><span class="sxs-lookup"><span data-stu-id="289a4-143">-Force</span></span>

<span data-ttu-id="289a4-144">指示此 cmdlet 将覆盖同一位置中具有相同名称的代码段文件。</span><span class="sxs-lookup"><span data-stu-id="289a4-144">Indicates that this cmdlet overwrites snippet files with the same name in the same location.</span></span> <span data-ttu-id="289a4-145">默认情况下，不 `New-ISESnippet` 会覆盖文件。</span><span class="sxs-lookup"><span data-stu-id="289a4-145">By default, `New-ISESnippet` does not overwrite files.</span></span>

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

### <span data-ttu-id="289a4-146">-文本</span><span class="sxs-lookup"><span data-stu-id="289a4-146">-Text</span></span>

<span data-ttu-id="289a4-147">指定在选择代码段时添加的文本值。</span><span class="sxs-lookup"><span data-stu-id="289a4-147">Specifies the text value that is added when you select the snippet.</span></span> <span data-ttu-id="289a4-148">当你在 Windows PowerShell ISE 中单击代码段名称时，将显示代码段文本。</span><span class="sxs-lookup"><span data-stu-id="289a4-148">The snippet text appears when you click the snippet name in Windows PowerShell ISE.</span></span> <span data-ttu-id="289a4-149">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="289a4-149">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="289a4-150">-Title</span><span class="sxs-lookup"><span data-stu-id="289a4-150">-Title</span></span>

<span data-ttu-id="289a4-151">指定代码段的标题或名称。</span><span class="sxs-lookup"><span data-stu-id="289a4-151">Specifies a title or name for the snippet.</span></span> <span data-ttu-id="289a4-152">标题还可命名代码段文件。</span><span class="sxs-lookup"><span data-stu-id="289a4-152">The title also names the snippet file.</span></span> <span data-ttu-id="289a4-153">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="289a4-153">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="289a4-154">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="289a4-154">CommonParameters</span></span>

<span data-ttu-id="289a4-155">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="289a4-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="289a4-156">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="289a4-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="289a4-157">输入</span><span class="sxs-lookup"><span data-stu-id="289a4-157">INPUTS</span></span>

### <span data-ttu-id="289a4-158">无</span><span class="sxs-lookup"><span data-stu-id="289a4-158">None</span></span>

<span data-ttu-id="289a4-159">此 cmdlet 不通过管道接受输入。</span><span class="sxs-lookup"><span data-stu-id="289a4-159">This cmdlet does not take input from the pipeline.</span></span>

## <span data-ttu-id="289a4-160">输出</span><span class="sxs-lookup"><span data-stu-id="289a4-160">OUTPUTS</span></span>

### <span data-ttu-id="289a4-161">无</span><span class="sxs-lookup"><span data-stu-id="289a4-161">None</span></span>

<span data-ttu-id="289a4-162">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="289a4-162">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="289a4-163">注释</span><span class="sxs-lookup"><span data-stu-id="289a4-163">NOTES</span></span>

<span data-ttu-id="289a4-164">`New-IseSnippet` 在 types.ps1xml 文件中存储新的用户创建的代码段。</span><span class="sxs-lookup"><span data-stu-id="289a4-164">`New-IseSnippet` stores new user-created snippets in unsigned .ps1xml files.</span></span> <span data-ttu-id="289a4-165">因此，Windows PowerShell 无法将其添加到执行策略为 **AllSigned** 或 **Restricted** 的会话中。</span><span class="sxs-lookup"><span data-stu-id="289a4-165">As such, Windows PowerShell cannot add them to a session in which the execution policy is **AllSigned** or **Restricted** .</span></span> <span data-ttu-id="289a4-166">在 **Restricted** 或 **AllSigned** 会话中，你可以创建、获取和导入用户创建的未签名代码段，但无法在会话中使用它们。</span><span class="sxs-lookup"><span data-stu-id="289a4-166">In a **Restricted** or **AllSigned** session, you can create, get, and import unsigned user-created snippets, but you cannot use them in the session.</span></span>

<span data-ttu-id="289a4-167">如果 `New-IseSnippet` 在 **受限** 或 **AllSigned** 会话中使用 cmdlet，则会创建代码段，但当 Windows PowerShell 尝试将新创建的代码段添加到会话时，将显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="289a4-167">If you use the `New-IseSnippet` cmdlet in a **Restricted** or **AllSigned** session, the snippet is created, but an error message appears when Windows PowerShell tries to add the newly created snippet to the session.</span></span> <span data-ttu-id="289a4-168">若要使用新代码段（以及用户创建的其他未签名代码段），请更改执行策略，然后重新启动 Windows PowerShell ISE。</span><span class="sxs-lookup"><span data-stu-id="289a4-168">To use the new snippet (and other unsigned user-created snippets), change the execution policy, and then restart Windows PowerShell ISE.</span></span>

<span data-ttu-id="289a4-169">有关 Windows PowerShell 执行策略的详细信息，请参阅 about_Execution_Policies。</span><span class="sxs-lookup"><span data-stu-id="289a4-169">For more information about Windows PowerShell execution policies, see about_Execution_Policies.</span></span>

- <span data-ttu-id="289a4-170">若要更改代码段，请编辑代码段文件。</span><span class="sxs-lookup"><span data-stu-id="289a4-170">To change a snippet, edit the snippet file.</span></span> <span data-ttu-id="289a4-171">可以在 Windows PowerShell ISE 的脚本窗格中编辑代码段文件。</span><span class="sxs-lookup"><span data-stu-id="289a4-171">You can edit snippet files in the Script pane of Windows PowerShell ISE.</span></span>
- <span data-ttu-id="289a4-172">若要删除已添加的代码段，请删除该代码段文件。</span><span class="sxs-lookup"><span data-stu-id="289a4-172">To delete a snippet that you added, delete the snippet file.</span></span>
- <span data-ttu-id="289a4-173">不能删除内置代码段，但可以使用 "$psise 隐藏所有内置代码段。ShowDefaultSnippets = $false "命令。</span><span class="sxs-lookup"><span data-stu-id="289a4-173">You cannot delete a built-in snippet, but you can hide all built-in snippets by using the "$psise.Options.ShowDefaultSnippets=$false" command.</span></span>
- <span data-ttu-id="289a4-174">你可以创建与内置代码段同名的代码段。</span><span class="sxs-lookup"><span data-stu-id="289a4-174">You can create a snippet that has the same name as a built-in snippet.</span></span> <span data-ttu-id="289a4-175">这两个代码段均显示在 Windows PowerShell ISE 的代码段菜单中。</span><span class="sxs-lookup"><span data-stu-id="289a4-175">Both snippets appear in the snippet menu in Windows PowerShell ISE.</span></span>

## <span data-ttu-id="289a4-176">相关链接</span><span class="sxs-lookup"><span data-stu-id="289a4-176">RELATED LINKS</span></span>

[<span data-ttu-id="289a4-177">Get-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="289a4-177">Get-IseSnippet</span></span>](Get-IseSnippet.md)

[<span data-ttu-id="289a4-178">Import-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="289a4-178">Import-IseSnippet</span></span>](Import-IseSnippet.md)
