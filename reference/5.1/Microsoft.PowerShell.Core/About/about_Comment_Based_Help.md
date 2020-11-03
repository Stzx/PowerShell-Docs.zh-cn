---
description: 介绍如何为函数和脚本编写基于注释的帮助主题。
keywords: powershell,cmdlet
ms.date: 06/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_comment_based_help?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Comment_Based_Help
ms.openlocfilehash: eaf1ea3eaacf944e9489292ea46822d655f2068b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200129"
---
# <a name="about-comment-based-help"></a><span data-ttu-id="aac32-104">关于基于注释的帮助</span><span class="sxs-lookup"><span data-stu-id="aac32-104">About Comment-based Help</span></span>

## <a name="short-description"></a><span data-ttu-id="aac32-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="aac32-105">Short description</span></span>
<span data-ttu-id="aac32-106">介绍如何为函数和脚本编写基于注释的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="aac32-106">Describes how to write comment-based help topics for functions and scripts.</span></span>

## <a name="long-description"></a><span data-ttu-id="aac32-107">长说明</span><span class="sxs-lookup"><span data-stu-id="aac32-107">Long description</span></span>

<span data-ttu-id="aac32-108">您可以使用特殊的帮助注释关键字为函数和脚本编写基于注释的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="aac32-108">You can write comment-based help topics for functions and scripts by using special help comment keywords.</span></span>

<span data-ttu-id="aac32-109">[Get-help](xref:Microsoft.PowerShell.Core.Get-Help) cmdlet 显示基于注释的帮助，其格式与用于显示 XML 文件中生成的 cmdlet 帮助主题的格式相同。</span><span class="sxs-lookup"><span data-stu-id="aac32-109">The [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) cmdlet displays comment-based help in the same format in which it displays the cmdlet help topics that are generated from XML files.</span></span> <span data-ttu-id="aac32-110">用户可以使用的所有参数 `Get-Help` ，如 **详细** 、 **完整** 、 **示例** 和 **联机** ，以显示基于注释的帮助的内容。</span><span class="sxs-lookup"><span data-stu-id="aac32-110">Users can use all of the parameters of `Get-Help`, such as **Detailed** , **Full** , **Examples** , and **Online** , to display the contents of comment-based help.</span></span>

<span data-ttu-id="aac32-111">还可以为函数和脚本编写基于 XML 的帮助文件。</span><span class="sxs-lookup"><span data-stu-id="aac32-111">You can also write XML-based help files for functions and scripts.</span></span> <span data-ttu-id="aac32-112">若要使 `Get-Help` cmdlet 能够查找函数或脚本的基于 XML 的帮助文件，请使用 `.ExternalHelp` 关键字。</span><span class="sxs-lookup"><span data-stu-id="aac32-112">To enable the `Get-Help` cmdlet to find the XML-based help file for a function or script, use the `.ExternalHelp` keyword.</span></span> <span data-ttu-id="aac32-113">如果没有此关键字，则 `Get-Help` 无法找到函数或脚本的基于 XML 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="aac32-113">Without this keyword, `Get-Help` cannot find XML-based help topics for functions or scripts.</span></span>

<span data-ttu-id="aac32-114">本主题说明如何编写函数和脚本的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="aac32-114">This topic explains how to write help topics for functions and scripts.</span></span> <span data-ttu-id="aac32-115">有关如何显示有关函数和脚本的帮助主题的信息，请参阅 [get-help](xref:Microsoft.PowerShell.Core.Get-Help)。</span><span class="sxs-lookup"><span data-stu-id="aac32-115">For information about how to display help topics for functions and scripts, see [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help).</span></span>

<span data-ttu-id="aac32-116">[Update-help](xref:Microsoft.PowerShell.Core.Update-Help)和[get-help](xref:Microsoft.PowerShell.Core.Save-Help) CMDLET 仅适用于 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="aac32-116">The [Update-Help](xref:Microsoft.PowerShell.Core.Update-Help) and [Save-Help](xref:Microsoft.PowerShell.Core.Save-Help) cmdlets work only on XML files.</span></span> <span data-ttu-id="aac32-117">可更新的帮助不支持基于注释的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="aac32-117">Updatable Help does not support comment-based help topics.</span></span>

## <a name="syntax-for-comment-based-help"></a><span data-ttu-id="aac32-118">基于注释的帮助的语法</span><span class="sxs-lookup"><span data-stu-id="aac32-118">Syntax for comment-based help</span></span>

<span data-ttu-id="aac32-119">基于注释的帮助的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="aac32-119">The syntax for comment-based help is as follows:</span></span>

```
# .<help keyword>
# <help content>
```

<span data-ttu-id="aac32-120">或</span><span class="sxs-lookup"><span data-stu-id="aac32-120">or</span></span>

```
<#
.<help keyword>
<help content>
#>
```

<span data-ttu-id="aac32-121">基于注释的帮助以一系列注释形式编写。</span><span class="sxs-lookup"><span data-stu-id="aac32-121">Comment-based help is written as a series of comments.</span></span> <span data-ttu-id="aac32-122">你可以 `#` 在每个注释行之前键入注释符号，也可以使用 `<#` 和 `#>` 符号来创建注释块。</span><span class="sxs-lookup"><span data-stu-id="aac32-122">You can type a comment symbol `#` before each line of comments, or you can use the `<#` and `#>` symbols to create a comment block.</span></span> <span data-ttu-id="aac32-123">注释块内的所有行都解释为注释。</span><span class="sxs-lookup"><span data-stu-id="aac32-123">All the lines within the comment block are interpreted as comments.</span></span>

<span data-ttu-id="aac32-124">基于注释的帮助主题中的所有行都必须是连续的。</span><span class="sxs-lookup"><span data-stu-id="aac32-124">All of the lines in a comment-based help topic must be contiguous.</span></span> <span data-ttu-id="aac32-125">如果基于注释的帮助主题遵循的注释不是帮助主题的一部分，则最后一个非帮助注释行与基于注释的帮助的开头之间必须至少有一个空白行。</span><span class="sxs-lookup"><span data-stu-id="aac32-125">If a comment-based help topic follows a comment that is not part of the help topic, there must be at least one blank line between the last non-help comment line and the beginning of the comment-based help.</span></span>

<span data-ttu-id="aac32-126">关键字定义基于注释的帮助的每个部分。</span><span class="sxs-lookup"><span data-stu-id="aac32-126">Keywords define each section of comment-based help.</span></span> <span data-ttu-id="aac32-127">每个基于注释的帮助关键字之前都带有一个点 `.` 。</span><span class="sxs-lookup"><span data-stu-id="aac32-127">Each comment-based help keyword is preceded by a dot `.`.</span></span> <span data-ttu-id="aac32-128">关键字可以按任意顺序出现。</span><span class="sxs-lookup"><span data-stu-id="aac32-128">The keywords can appear in any order.</span></span> <span data-ttu-id="aac32-129">关键字名称不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="aac32-129">The keyword names are not case-sensitive.</span></span>

<span data-ttu-id="aac32-130">例如，关键字在 `.Description` 函数或脚本的说明之前。</span><span class="sxs-lookup"><span data-stu-id="aac32-130">For example, the `.Description` keyword precedes a description of a function or script.</span></span>

```
<#
.Description
Get-Function displays the name and syntax of all functions in the session.
#>
```

<span data-ttu-id="aac32-131">注释块必须包含至少一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aac32-131">The comment block must contain at least one keyword.</span></span> <span data-ttu-id="aac32-132">某些关键字（如 `.EXAMPLE` ）可以在同一注释块中出现多次。</span><span class="sxs-lookup"><span data-stu-id="aac32-132">Some of the keywords, such as `.EXAMPLE`, can appear many times in the same comment block.</span></span> <span data-ttu-id="aac32-133">每个关键字的帮助内容都从关键字后面的行开始，可以跨多行。</span><span class="sxs-lookup"><span data-stu-id="aac32-133">The help content for each keyword begins on the line after the keyword and can span multiple lines.</span></span>

## <a name="syntax-for-comment-based-help-in-functions"></a><span data-ttu-id="aac32-134">函数中基于注释的帮助的语法</span><span class="sxs-lookup"><span data-stu-id="aac32-134">Syntax for comment-based help in functions</span></span>

<span data-ttu-id="aac32-135">函数的基于注释的帮助可能出现在以下三个位置之一：</span><span class="sxs-lookup"><span data-stu-id="aac32-135">Comment-based help for a function can appear in one of three locations:</span></span>

- <span data-ttu-id="aac32-136">函数体的开头。</span><span class="sxs-lookup"><span data-stu-id="aac32-136">At the beginning of the function body.</span></span>
- <span data-ttu-id="aac32-137">函数体的末尾。</span><span class="sxs-lookup"><span data-stu-id="aac32-137">At the end of the function body.</span></span>
- <span data-ttu-id="aac32-138">关键字之前 `function` 。</span><span class="sxs-lookup"><span data-stu-id="aac32-138">Before the `function` keyword.</span></span> <span data-ttu-id="aac32-139">函数的最后一行与关键字之间不能有多个空行 `function` 。</span><span class="sxs-lookup"><span data-stu-id="aac32-139">There cannot be more than one blank line between the last line of the function help and the `function` keyword.</span></span>

<span data-ttu-id="aac32-140">例如：</span><span class="sxs-lookup"><span data-stu-id="aac32-140">For example:</span></span>

```powershell
function Get-Function
{
<#
.<help keyword>
<help content>
#>

  # function logic
}
```

<span data-ttu-id="aac32-141">或</span><span class="sxs-lookup"><span data-stu-id="aac32-141">or</span></span>

```powershell
function Get-Function
{
   # function logic

<#
.<help keyword>
<help content>
#>
}
```

<span data-ttu-id="aac32-142">或</span><span class="sxs-lookup"><span data-stu-id="aac32-142">or</span></span>

```powershell
<#
.<help keyword>
<help content>
#>
function Get-Function { }
```

## <a name="syntax-for-comment-based-help-in-scripts"></a><span data-ttu-id="aac32-143">脚本中基于注释的帮助的语法</span><span class="sxs-lookup"><span data-stu-id="aac32-143">Syntax for comment-based help in scripts</span></span>

<span data-ttu-id="aac32-144">脚本的基于注释的帮助可以显示在脚本中的以下两个位置之一。</span><span class="sxs-lookup"><span data-stu-id="aac32-144">Comment-based help for a script can appear in one of the following two locations in the script.</span></span>

- <span data-ttu-id="aac32-145">位于脚本文件的开头。</span><span class="sxs-lookup"><span data-stu-id="aac32-145">At the beginning of the script file.</span></span> <span data-ttu-id="aac32-146">脚本帮助的前面只能是注释和空行。</span><span class="sxs-lookup"><span data-stu-id="aac32-146">Script help can be preceded in the script only by comments and blank lines.</span></span>

  <span data-ttu-id="aac32-147">如果在 "帮助") 后 (脚本正文中的第一项是函数声明，则脚本的末尾和函数声明之间必须至少有两个空行。</span><span class="sxs-lookup"><span data-stu-id="aac32-147">If the first item in the script body (after the help) is a function declaration, there must be at least two blank lines between the end of the script help and the function declaration.</span></span> <span data-ttu-id="aac32-148">否则，"帮助" 将被解释为该函数的帮助，而不是脚本的帮助。</span><span class="sxs-lookup"><span data-stu-id="aac32-148">Otherwise, the help is interpreted as being help for the function, not help for the script.</span></span>

- <span data-ttu-id="aac32-149">脚本文件末尾。</span><span class="sxs-lookup"><span data-stu-id="aac32-149">At the end of the script file.</span></span> <span data-ttu-id="aac32-150">但是，如果对脚本进行了签名，请在脚本文件的开头放置基于注释的帮助。</span><span class="sxs-lookup"><span data-stu-id="aac32-150">However, if the script is signed, place Comment-based help at the beginning of the script file.</span></span> <span data-ttu-id="aac32-151">脚本的末尾由签名块占用。</span><span class="sxs-lookup"><span data-stu-id="aac32-151">The end of the script is occupied by the signature block.</span></span>

<span data-ttu-id="aac32-152">例如：</span><span class="sxs-lookup"><span data-stu-id="aac32-152">For example:</span></span>

```powershell
<#
.<help keyword>
<help content>
#>


function Get-Function { }
```

<span data-ttu-id="aac32-153">或</span><span class="sxs-lookup"><span data-stu-id="aac32-153">or</span></span>

```powershell
function Get-Function { }

<#
.<help keyword>
<help content>
#>
```

## <a name="syntax-for-comment-based-help-in-script-modules"></a><span data-ttu-id="aac32-154">脚本模块中基于注释的帮助的语法</span><span class="sxs-lookup"><span data-stu-id="aac32-154">Syntax for comment-based help in script modules</span></span>

<span data-ttu-id="aac32-155">在脚本模块中 `.psm1` ，基于注释的帮助使用函数的语法，而不是脚本的语法。</span><span class="sxs-lookup"><span data-stu-id="aac32-155">In a script module `.psm1`, comment-based help uses the syntax for functions, not the syntax for scripts.</span></span> <span data-ttu-id="aac32-156">不能使用脚本语法为脚本模块中定义的所有函数提供帮助。</span><span class="sxs-lookup"><span data-stu-id="aac32-156">You cannot use the script syntax to provide help for all functions defined in a script module.</span></span>

<span data-ttu-id="aac32-157">例如，如果要使用 `.ExternalHelp` 关键字来标识脚本模块中函数的基于 XML 的帮助文件，则必须向 `.ExternalHelp` 每个函数添加注释。</span><span class="sxs-lookup"><span data-stu-id="aac32-157">For example, if you are using the `.ExternalHelp` keyword to identify the XML-based help files for the functions in a script module, you must add an `.ExternalHelp` comment to each function.</span></span>

```powershell
# .ExternalHelp <XML-file-name>
function <function-name>
{
  ...
}
```

## <a name="comment-based-help-keywords"></a><span data-ttu-id="aac32-158">基于注释的帮助关键字</span><span class="sxs-lookup"><span data-stu-id="aac32-158">Comment-based help keywords</span></span>

<span data-ttu-id="aac32-159">下面是有效的基于注释的帮助关键字。</span><span class="sxs-lookup"><span data-stu-id="aac32-159">The following are valid comment-based help keywords.</span></span> <span data-ttu-id="aac32-160">它们按其在帮助主题中通常出现的顺序列出，以及它们的预期用途。</span><span class="sxs-lookup"><span data-stu-id="aac32-160">They are listed in the order in which they typically appear in a help topic along with their intended use.</span></span> <span data-ttu-id="aac32-161">这些关键字可以在基于注释的帮助中以任意顺序出现，它们不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="aac32-161">These keywords can appear in any order in the comment-based help, and they are not case-sensitive.</span></span>

### <a name="synopsis"></a><span data-ttu-id="aac32-162">.概要</span><span class="sxs-lookup"><span data-stu-id="aac32-162">.SYNOPSIS</span></span>

<span data-ttu-id="aac32-163">函数或脚本的简短说明。</span><span class="sxs-lookup"><span data-stu-id="aac32-163">A brief description of the function or script.</span></span> <span data-ttu-id="aac32-164">每个主题中只能使用一次此关键字。</span><span class="sxs-lookup"><span data-stu-id="aac32-164">This keyword can be used only once in each topic.</span></span>

### <a name="description"></a><span data-ttu-id="aac32-165">.2008</span><span class="sxs-lookup"><span data-stu-id="aac32-165">.DESCRIPTION</span></span>

<span data-ttu-id="aac32-166">函数或脚本的详细说明。</span><span class="sxs-lookup"><span data-stu-id="aac32-166">A detailed description of the function or script.</span></span> <span data-ttu-id="aac32-167">每个主题中只能使用一次此关键字。</span><span class="sxs-lookup"><span data-stu-id="aac32-167">This keyword can be used only once in each topic.</span></span>

### <a name="parameter"></a><span data-ttu-id="aac32-168">.参数</span><span class="sxs-lookup"><span data-stu-id="aac32-168">.PARAMETER</span></span>

<span data-ttu-id="aac32-169">参数的说明。</span><span class="sxs-lookup"><span data-stu-id="aac32-169">The description of a parameter.</span></span> <span data-ttu-id="aac32-170">`.PARAMETER`在函数或脚本语法中为每个参数添加关键字。</span><span class="sxs-lookup"><span data-stu-id="aac32-170">Add a `.PARAMETER` keyword for each parameter in the function or script syntax.</span></span>

<span data-ttu-id="aac32-171">键入与关键字相同的行中的参数名称 `.PARAMETER` 。</span><span class="sxs-lookup"><span data-stu-id="aac32-171">Type the parameter name on the same line as the `.PARAMETER` keyword.</span></span> <span data-ttu-id="aac32-172">在关键字后面的行上键入参数说明 `.PARAMETER` 。</span><span class="sxs-lookup"><span data-stu-id="aac32-172">Type the parameter description on the lines following the `.PARAMETER` keyword.</span></span> <span data-ttu-id="aac32-173">Windows PowerShell 会将 `.PARAMETER` 行和下一关键字之间的所有文本解释为参数说明的一部分。</span><span class="sxs-lookup"><span data-stu-id="aac32-173">Windows PowerShell interprets all text between the `.PARAMETER` line and the next keyword or the end of the comment block as part of the parameter description.</span></span>
<span data-ttu-id="aac32-174">说明可以包括分段符。</span><span class="sxs-lookup"><span data-stu-id="aac32-174">The description can include paragraph breaks.</span></span>

```
.PARAMETER  <Parameter-Name>
```

<span data-ttu-id="aac32-175">参数关键字可以在注释块中以任意顺序出现，但是函数或脚本语法将确定参数 (的顺序及其说明) 出现在帮助主题中。</span><span class="sxs-lookup"><span data-stu-id="aac32-175">The Parameter keywords can appear in any order in the comment block, but the function or script syntax determines the order in which the parameters (and their descriptions) appear in help topic.</span></span> <span data-ttu-id="aac32-176">若要更改顺序，请更改语法。</span><span class="sxs-lookup"><span data-stu-id="aac32-176">To change the order, change the syntax.</span></span>

<span data-ttu-id="aac32-177">还可以指定参数说明，方法是将注释放在函数或脚本语法中紧靠在参数变量名称之前。</span><span class="sxs-lookup"><span data-stu-id="aac32-177">You can also specify a parameter description by placing a comment in the function or script syntax immediately before the parameter variable name.</span></span> <span data-ttu-id="aac32-178">为此，您还必须具有至少一个关键字的注释块。</span><span class="sxs-lookup"><span data-stu-id="aac32-178">For this to work, you must also have a comment block with at least one keyword.</span></span>

<span data-ttu-id="aac32-179">如果同时使用语法注释和 `.PARAMETER` 关键字，则使用与关键字关联的说明 `.PARAMETER` ，并忽略语法注释。</span><span class="sxs-lookup"><span data-stu-id="aac32-179">If you use both a syntax comment and a `.PARAMETER` keyword, the description associated with the `.PARAMETER` keyword is used, and the syntax comment is ignored.</span></span>

```powershell
<#
.SYNOPSIS
    Short description here
#>
function Verb-Noun {
    [CmdletBinding()]
    param (
        # This is the same as .Parameter
        [string]$Computername
    )
    # Verb the Noun on the computer
}
```

### <a name="example"></a><span data-ttu-id="aac32-180">.实例</span><span class="sxs-lookup"><span data-stu-id="aac32-180">.EXAMPLE</span></span>

<span data-ttu-id="aac32-181">使用函数或脚本的示例命令，可选择后跟示例输出和说明。</span><span class="sxs-lookup"><span data-stu-id="aac32-181">A sample command that uses the function or script, optionally followed by sample output and a description.</span></span> <span data-ttu-id="aac32-182">为每个示例重复此关键字。</span><span class="sxs-lookup"><span data-stu-id="aac32-182">Repeat this keyword for each example.</span></span>

### <a name="inputs"></a><span data-ttu-id="aac32-183">.输入</span><span class="sxs-lookup"><span data-stu-id="aac32-183">.INPUTS</span></span>

<span data-ttu-id="aac32-184">可以通过管道传递给函数或脚本的 .NET 类型的对象。</span><span class="sxs-lookup"><span data-stu-id="aac32-184">The .NET types of objects that can be piped to the function or script.</span></span> <span data-ttu-id="aac32-185">还可以包括对输入对象的描述。</span><span class="sxs-lookup"><span data-stu-id="aac32-185">You can also include a description of the input objects.</span></span>

### <a name="outputs"></a><span data-ttu-id="aac32-186">.输出</span><span class="sxs-lookup"><span data-stu-id="aac32-186">.OUTPUTS</span></span>

<span data-ttu-id="aac32-187">Cmdlet 返回的对象的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="aac32-187">The .NET type of the objects that the cmdlet returns.</span></span> <span data-ttu-id="aac32-188">还可以包括返回对象的描述。</span><span class="sxs-lookup"><span data-stu-id="aac32-188">You can also include a description of the returned objects.</span></span>

### <a name="notes"></a><span data-ttu-id="aac32-189">.本票</span><span class="sxs-lookup"><span data-stu-id="aac32-189">.NOTES</span></span>

<span data-ttu-id="aac32-190">有关函数或脚本的其他信息。</span><span class="sxs-lookup"><span data-stu-id="aac32-190">Additional information about the function or script.</span></span>

### <a name="link"></a><span data-ttu-id="aac32-191">.连接</span><span class="sxs-lookup"><span data-stu-id="aac32-191">.LINK</span></span>

<span data-ttu-id="aac32-192">相关主题的名称。</span><span class="sxs-lookup"><span data-stu-id="aac32-192">The name of a related topic.</span></span> <span data-ttu-id="aac32-193">该值将显示在 "" 下的行中。LINK "关键字和前面必须是注释符号 `#` 或包含在注释块中。</span><span class="sxs-lookup"><span data-stu-id="aac32-193">The value appears on the line below the ".LINK" keyword and must be preceded by a comment symbol `#` or included in the comment block.</span></span>

<span data-ttu-id="aac32-194">`.LINK`对每个相关主题重复关键字。</span><span class="sxs-lookup"><span data-stu-id="aac32-194">Repeat the `.LINK` keyword for each related topic.</span></span>

<span data-ttu-id="aac32-195">此内容显示在帮助主题的 "相关链接" 部分中。</span><span class="sxs-lookup"><span data-stu-id="aac32-195">This content appears in the Related Links section of the help topic.</span></span>

<span data-ttu-id="aac32-196">`.Link`关键字内容还可以包含统一资源标识符 (URI) 到同一帮助主题的联机版本。</span><span class="sxs-lookup"><span data-stu-id="aac32-196">The `.Link` keyword content can also include a Uniform Resource Identifier (URI) to an online version of the same help topic.</span></span> <span data-ttu-id="aac32-197">当你使用的 **联机** 参数时，将打开联机版本 `Get-Help` 。</span><span class="sxs-lookup"><span data-stu-id="aac32-197">The online version opens when you use the **Online** parameter of `Get-Help`.</span></span> <span data-ttu-id="aac32-198">URI 必须以 "http" 或 "https" 开头。</span><span class="sxs-lookup"><span data-stu-id="aac32-198">The URI must begin with "http" or "https".</span></span>

### <a name="component"></a><span data-ttu-id="aac32-199">.组件</span><span class="sxs-lookup"><span data-stu-id="aac32-199">.COMPONENT</span></span>

<span data-ttu-id="aac32-200">函数或脚本使用或与之相关的技术或功能的名称。</span><span class="sxs-lookup"><span data-stu-id="aac32-200">The name of the technology or feature that the function or script uses, or to which it is related.</span></span> <span data-ttu-id="aac32-201">的 **组件** 参数 `Get-Help` 使用此值来筛选返回的搜索结果 `Get-Help` 。</span><span class="sxs-lookup"><span data-stu-id="aac32-201">The **Component** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

### <a name="role"></a><span data-ttu-id="aac32-202">.职位</span><span class="sxs-lookup"><span data-stu-id="aac32-202">.ROLE</span></span>

<span data-ttu-id="aac32-203">帮助主题的用户角色的名称。</span><span class="sxs-lookup"><span data-stu-id="aac32-203">The name of the user role for the help topic.</span></span> <span data-ttu-id="aac32-204">的 **Role** 参数 `Get-Help` 使用此值来筛选返回的搜索结果 `Get-Help` 。</span><span class="sxs-lookup"><span data-stu-id="aac32-204">The **Role** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

### <a name="functionality"></a><span data-ttu-id="aac32-205">.性能</span><span class="sxs-lookup"><span data-stu-id="aac32-205">.FUNCTIONALITY</span></span>

<span data-ttu-id="aac32-206">描述函数的预期用途的关键字。</span><span class="sxs-lookup"><span data-stu-id="aac32-206">The keywords that describe the intended use of the function.</span></span> <span data-ttu-id="aac32-207">的 **功能** 参数 `Get-Help` 使用此值来筛选返回的搜索结果 `Get-Help` 。</span><span class="sxs-lookup"><span data-stu-id="aac32-207">The **Functionality** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

### <a name="forwardhelptargetname"></a><span data-ttu-id="aac32-208">.FORWARDHELPTARGETNAME</span><span class="sxs-lookup"><span data-stu-id="aac32-208">.FORWARDHELPTARGETNAME</span></span>

<span data-ttu-id="aac32-209">重定向到指定命令的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="aac32-209">Redirects to the help topic for the specified command.</span></span> <span data-ttu-id="aac32-210">您可以将用户重定向到任何帮助主题，包括函数、脚本、cmdlet 或提供程序的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="aac32-210">You can redirect users to any help topic, including help topics for a function, script, cmdlet, or provider.</span></span>

```powershell
# .FORWARDHELPTARGETNAME <Command-Name>
```

### <a name="forwardhelpcategory"></a><span data-ttu-id="aac32-211">.FORWARDHELPCATEGORY</span><span class="sxs-lookup"><span data-stu-id="aac32-211">.FORWARDHELPCATEGORY</span></span>

<span data-ttu-id="aac32-212">指定中的项的帮助类别 `.ForwardHelpTargetName` 。</span><span class="sxs-lookup"><span data-stu-id="aac32-212">Specifies the help category of the item in `.ForwardHelpTargetName`.</span></span> <span data-ttu-id="aac32-213">有效值为 `Alias` 、、 `Cmdlet` 、 `HelpFile` `Function` 、 `Provider` 、、 `General` 、、、、 `FAQ` `Glossary` `ScriptCommand` `ExternalScript` `Filter` 或 `All` 。</span><span class="sxs-lookup"><span data-stu-id="aac32-213">Valid values are `Alias`, `Cmdlet`, `HelpFile`, `Function`, `Provider`, `General`, `FAQ`, `Glossary`, `ScriptCommand`, `ExternalScript`, `Filter`, or `All`.</span></span> <span data-ttu-id="aac32-214">当存在具有相同名称的命令时，请使用此关键字避免冲突。</span><span class="sxs-lookup"><span data-stu-id="aac32-214">Use this keyword to avoid conflicts when there are commands with the same name.</span></span>

```powershell
# .FORWARDHELPCATEGORY <Category>
```

### <a name="remotehelprunspace"></a><span data-ttu-id="aac32-215">.REMOTEHELPRUNSPACE</span><span class="sxs-lookup"><span data-stu-id="aac32-215">.REMOTEHELPRUNSPACE</span></span>

<span data-ttu-id="aac32-216">指定包含 "帮助" 主题的会话。</span><span class="sxs-lookup"><span data-stu-id="aac32-216">Specifies a session that contains the help topic.</span></span> <span data-ttu-id="aac32-217">输入包含 **PSSession** 对象的变量。</span><span class="sxs-lookup"><span data-stu-id="aac32-217">Enter a variable that contains a **PSSession** object.</span></span> <span data-ttu-id="aac32-218">此关键字由 [Export-PSSession](xref:Microsoft.PowerShell.Utility.Export-PSSession) cmdlet 用于查找有关导出的命令的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="aac32-218">This keyword is used by the [Export-PSSession](xref:Microsoft.PowerShell.Utility.Export-PSSession) cmdlet to find the help topics for the exported commands.</span></span>

```powershell
# .REMOTEHELPRUNSPACE <PSSession-variable>
```

### <a name="externalhelp"></a><span data-ttu-id="aac32-219">..EXTERNALHELP</span><span class="sxs-lookup"><span data-stu-id="aac32-219">.EXTERNALHELP</span></span>

<span data-ttu-id="aac32-220">为脚本或函数指定基于 XML 的帮助文件。</span><span class="sxs-lookup"><span data-stu-id="aac32-220">Specifies an XML-based help file for the script or function.</span></span>

```powershell
# .EXTERNALHELP <XML Help File>
```

<span data-ttu-id="aac32-221">在 `.ExternalHelp` XML 文件中记录函数或脚本时，需要使用关键字。</span><span class="sxs-lookup"><span data-stu-id="aac32-221">The `.ExternalHelp` keyword is required when a function or script is documented in XML files.</span></span> <span data-ttu-id="aac32-222">如果没有此关键字，则找 `Get-Help` 不到函数或脚本的基于 XML 的帮助文件。</span><span class="sxs-lookup"><span data-stu-id="aac32-222">Without this keyword, `Get-Help` cannot find the XML-based help file for the function or script.</span></span>

<span data-ttu-id="aac32-223">`.ExternalHelp`关键字优先于其他基于注释的帮助关键字。</span><span class="sxs-lookup"><span data-stu-id="aac32-223">The `.ExternalHelp` keyword takes precedence over other comment-based help keywords.</span></span> <span data-ttu-id="aac32-224">如果 `.ExternalHelp` 存在，则不 `Get-Help` 会显示基于注释的帮助，即使找不到与关键字的值匹配的帮助主题 `.ExternalHelp` 。</span><span class="sxs-lookup"><span data-stu-id="aac32-224">If `.ExternalHelp` is present, `Get-Help` does not display comment-based help, even if it cannot find a help topic that matches the value of the `.ExternalHelp` keyword.</span></span>

<span data-ttu-id="aac32-225">如果函数是由模块导出的，请将关键字的值设置 `.ExternalHelp` 为不带路径的文件名。</span><span class="sxs-lookup"><span data-stu-id="aac32-225">If the function is exported by a module, set the value of the `.ExternalHelp` keyword to a filename without a path.</span></span> <span data-ttu-id="aac32-226">`Get-Help` 在模块目录的特定于语言的子目录中查找指定的文件名。</span><span class="sxs-lookup"><span data-stu-id="aac32-226">`Get-Help` looks for the specified file name in a language-specific subdirectory of the module directory.</span></span> <span data-ttu-id="aac32-227">对于函数，不需要提供基于 XML 的帮助文件的名称，但最佳做法是使用以下格式：</span><span class="sxs-lookup"><span data-stu-id="aac32-227">There are no requirements for the name of the XML-based help file for a function, but a best practice is to use the following format:</span></span>

```
<ScriptModule.psm1>-help.xml
```

<span data-ttu-id="aac32-228">如果该函数未包含在模块中，则包含基于 XML 的帮助文件的路径。</span><span class="sxs-lookup"><span data-stu-id="aac32-228">If the function is not included in a module, include a path to the XML-based help file.</span></span> <span data-ttu-id="aac32-229">如果值包含路径，并且路径包含 UI 区域性特定的子目录，则会以 `Get-Help` 递归方式搜索包含脚本或函数名称的 XML 文件的子目录，就像在模块目录中那样。</span><span class="sxs-lookup"><span data-stu-id="aac32-229">If the value includes a path and the path contains UI-culture-specific subdirectories, `Get-Help` searches the subdirectories recursively for an XML file with the name of the script or function in accordance with the language fallback standards established for Windows, just as it does in a module directory.</span></span>

<span data-ttu-id="aac32-230">有关 cmdlet 的帮助文件格式的详细信息，请参阅 MSDN library 中的 how [To Write Cmdlet help （如何编写 Cmdlet 帮助](https://go.microsoft.com/fwlink/?LinkID=123415) ）。</span><span class="sxs-lookup"><span data-stu-id="aac32-230">For more information about the cmdlet help XML-based help file format, see [How to Write Cmdlet Help](https://go.microsoft.com/fwlink/?LinkID=123415) in the MSDN library.</span></span>

## <a name="autogenerated-content"></a><span data-ttu-id="aac32-231">自动生成内容</span><span class="sxs-lookup"><span data-stu-id="aac32-231">Autogenerated content</span></span>

<span data-ttu-id="aac32-232">Cmdlet 自动生成名称、语法、参数列表、参数属性表、通用参数和备注 `Get-Help` 。</span><span class="sxs-lookup"><span data-stu-id="aac32-232">The name, syntax, parameter list, parameter attribute table, common parameters, and remarks are automatically generated by the `Get-Help` cmdlet.</span></span>

### <a name="name"></a><span data-ttu-id="aac32-233">名称</span><span class="sxs-lookup"><span data-stu-id="aac32-233">Name</span></span>

<span data-ttu-id="aac32-234">函数帮助主题的 **name** 节取自函数语法中的函数名称。</span><span class="sxs-lookup"><span data-stu-id="aac32-234">The **Name** section of a function help topic is taken from the function name in the function syntax.</span></span> <span data-ttu-id="aac32-235">脚本帮助主题的 **名称** 取自脚本文件名。</span><span class="sxs-lookup"><span data-stu-id="aac32-235">The **Name** of a script help topic is taken from the script filename.</span></span> <span data-ttu-id="aac32-236">若要更改名称或其大小写，请更改函数语法或脚本文件名。</span><span class="sxs-lookup"><span data-stu-id="aac32-236">To change the name or its capitalization, change the function syntax or the script filename.</span></span>

### <a name="syntax"></a><span data-ttu-id="aac32-237">语法</span><span class="sxs-lookup"><span data-stu-id="aac32-237">Syntax</span></span>

<span data-ttu-id="aac32-238">帮助主题的 **语法** 部分是从函数或脚本语法生成的。</span><span class="sxs-lookup"><span data-stu-id="aac32-238">The **Syntax** section of the help topic is generated from the function or script syntax.</span></span> <span data-ttu-id="aac32-239">若要将详细信息添加到帮助主题语法（如参数的 .NET 类型），请将详细信息添加到语法中。</span><span class="sxs-lookup"><span data-stu-id="aac32-239">To add detail to the help topic syntax, such as the .NET type of a parameter, add the detail to the syntax.</span></span> <span data-ttu-id="aac32-240">如果未指定参数类型，则会将该 **对象** 类型作为默认值插入。</span><span class="sxs-lookup"><span data-stu-id="aac32-240">If you do not specify a parameter type, the **Object** type is inserted as the default value.</span></span>

### <a name="parameter-list"></a><span data-ttu-id="aac32-241">参数列表</span><span class="sxs-lookup"><span data-stu-id="aac32-241">Parameter List</span></span>

<span data-ttu-id="aac32-242">帮助主题中的参数列表是从函数或脚本语法以及使用关键字添加的说明生成的 `.Parameter` 。</span><span class="sxs-lookup"><span data-stu-id="aac32-242">The parameter list in the help topic is generated from the function or script syntax and from the descriptions that you add by using the `.Parameter` keyword.</span></span> <span data-ttu-id="aac32-243">函数参数显示在帮助主题的 **parameters** 节中，其顺序与它们在函数或脚本语法中出现的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="aac32-243">The function parameters appear in the **Parameters** section of the help topic in the same order that they appear in the function or script syntax.</span></span> <span data-ttu-id="aac32-244">参数名称的拼写和大小写也是从语法中获取的。</span><span class="sxs-lookup"><span data-stu-id="aac32-244">The spelling and capitalization of parameter names is also taken from the syntax.</span></span> <span data-ttu-id="aac32-245">它不受关键字指定的参数名称的影响 `.Parameter` 。</span><span class="sxs-lookup"><span data-stu-id="aac32-245">It is not affected by the parameter name specified by the `.Parameter` keyword.</span></span>

### <a name="common-parameters"></a><span data-ttu-id="aac32-246">通用参数</span><span class="sxs-lookup"><span data-stu-id="aac32-246">Common Parameters</span></span>

<span data-ttu-id="aac32-247">**公用参数** 将添加到帮助主题的语法和参数列表中，即使它们不起作用也是如此。</span><span class="sxs-lookup"><span data-stu-id="aac32-247">The **Common parameters** are added to the syntax and parameter list of the help topic, even if they have no effect.</span></span> <span data-ttu-id="aac32-248">有关常见参数的详细信息，请参阅 [about_CommonParameters](about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="aac32-248">For more information about the common parameters, see [about_CommonParameters](about_CommonParameters.md).</span></span>

### <a name="parameter-attribute-table"></a><span data-ttu-id="aac32-249">参数属性表</span><span class="sxs-lookup"><span data-stu-id="aac32-249">Parameter Attribute Table</span></span>

<span data-ttu-id="aac32-250">`Get-Help` 生成在使用的 **完整** 参数或 **参数** 参数时显示的参数属性表 `Get-Help` 。</span><span class="sxs-lookup"><span data-stu-id="aac32-250">`Get-Help` generates the table of parameter attributes that appears when you use the **Full** or **Parameter** parameter of `Get-Help`.</span></span> <span data-ttu-id="aac32-251">" **必需** "、" **位置** " 和 " **默认** 值" 属性的值取自函数或脚本语法。</span><span class="sxs-lookup"><span data-stu-id="aac32-251">The value of the **Required** , **Position** , and **Default** value attributes is taken from the function or script syntax.</span></span>

<span data-ttu-id="aac32-252">即使在函数或脚本中定义了默认值和 " **接受通配符** " 的值，也不会显示在参数属性表中。</span><span class="sxs-lookup"><span data-stu-id="aac32-252">Default values and a value for **Accept Wildcard characters** do not appear in the parameter attribute table even when they are defined in the function or script.</span></span> <span data-ttu-id="aac32-253">若要帮助用户，请在参数说明中提供此信息。</span><span class="sxs-lookup"><span data-stu-id="aac32-253">To help users, provide this information in the parameter description.</span></span>

### <a name="remarks"></a><span data-ttu-id="aac32-254">备注</span><span class="sxs-lookup"><span data-stu-id="aac32-254">Remarks</span></span>

<span data-ttu-id="aac32-255">"帮助" 主题的 " **备注** " 部分是从函数或脚本名称自动生成的。</span><span class="sxs-lookup"><span data-stu-id="aac32-255">The **Remarks** section of the help topic is automatically generated from the function or script name.</span></span> <span data-ttu-id="aac32-256">不能更改或影响其内容。</span><span class="sxs-lookup"><span data-stu-id="aac32-256">You cannot change or affect its content.</span></span>

## <a name="examples"></a><span data-ttu-id="aac32-257">示例</span><span class="sxs-lookup"><span data-stu-id="aac32-257">Examples</span></span>

### <a name="comment-based-help-for-a-function"></a><span data-ttu-id="aac32-258">函数的基于注释的帮助</span><span class="sxs-lookup"><span data-stu-id="aac32-258">Comment-based Help for a Function</span></span>

<span data-ttu-id="aac32-259">以下示例函数包含基于注释的帮助：</span><span class="sxs-lookup"><span data-stu-id="aac32-259">The following sample function includes comment-based help:</span></span>

```powershell
function Add-Extension
{
param ([string]$Name,[string]$Extension = "txt")
$name = $name + "." + $extension
$name

<#
.SYNOPSIS

Adds a file name extension to a supplied name.

.DESCRIPTION

Adds a file name extension to a supplied name.
Takes any strings for the file name or extension.

.PARAMETER Name
Specifies the file name.

.PARAMETER Extension
Specifies the extension. "Txt" is the default.

.INPUTS

None. You cannot pipe objects to Add-Extension.

.OUTPUTS

System.String. Add-Extension returns a string with the extension
or file name.

.EXAMPLE

PS> extension -name "File"
File.txt

.EXAMPLE

PS> extension -name "File" -extension "doc"
File.doc

.EXAMPLE

PS> extension "File" "doc"
File.doc

.LINK

http://www.fabrikam.com/extension.html

.LINK

Set-Item
#>
}
```

<span data-ttu-id="aac32-260">结果如下所示：</span><span class="sxs-lookup"><span data-stu-id="aac32-260">The results are as follows:</span></span>

```powershell
Get-Help -Name "Add-Extension" -Full
```

```Output
NAME

Add-Extension

SYNOPSIS

Adds a file name extension to a supplied name.

SYNTAX

Add-Extension [[-Name] <String>] [[-Extension] <String>]
[<CommonParameters>]

DESCRIPTION

Adds a file name extension to a supplied name. Takes any strings for the
file name or extension.

PARAMETERS

-Name
Specifies the file name.

Required?                    false
Position?                    0
Default value
Accept pipeline input?       false
Accept wildcard characters?

-Extension
Specifies the extension. "Txt" is the default.

Required?                    false
Position?                    1
Default value
Accept pipeline input?       false
Accept wildcard characters?

<CommonParameters>
This cmdlet supports the common parameters: -Verbose, -Debug,
-ErrorAction, -ErrorVariable, -WarningAction, -WarningVariable,
-OutBuffer and -OutVariable. For more information, type
"get-help about_commonparameters".

INPUTS
None. You cannot pipe objects to Add-Extension.

OUTPUTS

System.String. Add-Extension returns a string with the extension or
file name.

Example 1

PS> extension -name "File"
File.txt

Example 2

PS> extension -name "File" -extension "doc"
File.doc

Example 3

PS> extension "File" "doc"
File.doc

RELATED LINKS

http://www.fabrikam.com/extension.html
Set-Item
```

### <a name="parameter-descriptions-in-function-syntax"></a><span data-ttu-id="aac32-261">函数语法中的参数说明</span><span class="sxs-lookup"><span data-stu-id="aac32-261">Parameter Descriptions in Function Syntax</span></span>

<span data-ttu-id="aac32-262">此示例与上一个示例相同，不同之处在于参数说明插入函数语法。</span><span class="sxs-lookup"><span data-stu-id="aac32-262">This example is the same as the previous one, except that the parameter descriptions are inserted in the function syntax.</span></span> <span data-ttu-id="aac32-263">当说明简短时，此格式最为有用。</span><span class="sxs-lookup"><span data-stu-id="aac32-263">This format is most useful when the descriptions are brief.</span></span>

```powershell
function Add-Extension
{
param
(

[string]
#Specifies the file name.
$name,

[string]
#Specifies the file name extension. "Txt" is the default.
$extension = "txt"
)

$name = $name + "." + $extension
$name

<#
.SYNOPSIS

Adds a file name extension to a supplied name.

.DESCRIPTION

Adds a file name extension to a supplied name. Takes any strings for the
file name or extension.

.INPUTS

None. You cannot pipe objects to Add-Extension.

.OUTPUTS

System.String. Add-Extension returns a string with the extension or
file name.

.EXAMPLE

PS> extension -name "File"
File.txt

.EXAMPLE

PS> extension -name "File" -extension "doc"
File.doc

.EXAMPLE

PS> extension "File" "doc"
File.doc

.LINK

http://www.fabrikam.com/extension.html

.LINK

Set-Item
#>
}
```

### <a name="comment-based-help-for-a-script"></a><span data-ttu-id="aac32-264">脚本的基于注释的帮助</span><span class="sxs-lookup"><span data-stu-id="aac32-264">Comment-based Help for a Script</span></span>

<span data-ttu-id="aac32-265">下面的示例脚本包含基于注释的帮助。</span><span class="sxs-lookup"><span data-stu-id="aac32-265">The following sample script includes comment-based help.</span></span> <span data-ttu-id="aac32-266">请注意结束 `#>` 语句和语句之间的空行 `Param` 。</span><span class="sxs-lookup"><span data-stu-id="aac32-266">Notice the blank lines between the closing `#>` and the `Param` statement.</span></span> <span data-ttu-id="aac32-267">在不包含语句的脚本中 `Param` ，"帮助" 主题中的最后一个注释和第一个函数声明之间必须至少有两个空行。</span><span class="sxs-lookup"><span data-stu-id="aac32-267">In a script that does not have a `Param` statement, there must be at least two blank lines between the final comment in the help topic and the first function declaration.</span></span> <span data-ttu-id="aac32-268">如果没有这些空白行，请将 `Get-Help` 帮助主题与函数（而不是脚本）相关联。</span><span class="sxs-lookup"><span data-stu-id="aac32-268">Without these blank lines, `Get-Help` associates the help topic with the function, not the script.</span></span>

```powershell
<#
.SYNOPSIS

Performs monthly data updates.

.DESCRIPTION

The Update-Month.ps1 script updates the registry with new data generated
during the past month and generates a report.

.PARAMETER InputPath
Specifies the path to the CSV-based input file.

.PARAMETER OutputPath
Specifies the name and path for the CSV-based output file. By default,
MonthlyUpdates.ps1 generates a name from the date and time it runs, and
saves the output in the local directory.

.INPUTS

None. You cannot pipe objects to Update-Month.ps1.

.OUTPUTS

None. Update-Month.ps1 does not generate any output.

.EXAMPLE

PS> .\Update-Month.ps1

.EXAMPLE

PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv

.EXAMPLE

PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv -outputPath `
C:\Reports\2009\January.csv
#>

param ([string]$InputPath, [string]$OutPutPath)

function Get-Data { }
...
```

<span data-ttu-id="aac32-269">以下命令获取脚本帮助。</span><span class="sxs-lookup"><span data-stu-id="aac32-269">The following command gets the script help.</span></span> <span data-ttu-id="aac32-270">由于脚本不在环境变量中列出的目录中，因此 `$env:Path` `Get-Help` 获取脚本帮助的命令必须指定脚本路径。</span><span class="sxs-lookup"><span data-stu-id="aac32-270">Because the script is not in a directory that is listed in the `$env:Path` environment variable, the `Get-Help` command that gets the script help must specify the script path.</span></span>

```powershell
Get-Help -Path .\update-month.ps1 -Full
```

```Output
# NAME

C:\ps-test\Update-Month.ps1

# SYNOPSIS

Performs monthly data updates.

# SYNTAX

C:\ps-test\Update-Month.ps1 [-InputPath] <String> [[-OutputPath]
<String>] [<CommonParameters>]

# DESCRIPTION

The Update-Month.ps1 script updates the registry with new data
generated during the past month and generates a report.

# PARAMETERS

-InputPath
Specifies the path to the CSV-based input file.

Required?                    true
Position?                    0
Default value
Accept pipeline input?       false
Accept wildcard characters?

-OutputPath
Specifies the name and path for the CSV-based output file. By
default, MonthlyUpdates.ps1 generates a name from the date
and time it runs, and saves the output in the local directory.

Required?                    false
Position?                    1
Default value
Accept pipeline input?       false
Accept wildcard characters?

<CommonParameters>
This cmdlet supports the common parameters: -Verbose, -Debug,
-ErrorAction, -ErrorVariable, -WarningAction, -WarningVariable,
-OutBuffer and -OutVariable. For more information, type,
"get-help about_commonparameters".

# INPUTS

None. You cannot pipe objects to Update-Month.ps1.

# OUTPUTS

None. Update-Month.ps1 does not generate any output.

Example 1

PS> .\Update-Month.ps1

Example 2

PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv

Example 3

PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv -outputPath
C:\Reports\2009\January.csv

# RELATED LINKS
```

### <a name="redirecting-to-an-xml-file"></a><span data-ttu-id="aac32-271">重定向到 XML 文件</span><span class="sxs-lookup"><span data-stu-id="aac32-271">Redirecting to an XML File</span></span>

<span data-ttu-id="aac32-272">您可以为函数和脚本编写基于 XML 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="aac32-272">You can write XML-based help topics for functions and scripts.</span></span> <span data-ttu-id="aac32-273">尽管基于注释的帮助更容易实现，但可更新帮助和提供多种语言的帮助主题需要基于 XML 的帮助。</span><span class="sxs-lookup"><span data-stu-id="aac32-273">Although comment-based help is easier to implement, XML-based help is required for Updatable Help and to provide help topics in multiple languages.</span></span>

<span data-ttu-id="aac32-274">下面的示例演示 Update-Month.ps1 脚本的前几行。</span><span class="sxs-lookup"><span data-stu-id="aac32-274">The following example shows the first few lines of the Update-Month.ps1 script.</span></span>
<span data-ttu-id="aac32-275">脚本使用关键字为 `.ExternalHelp` 脚本指定基于 XML 的帮助主题的路径。</span><span class="sxs-lookup"><span data-stu-id="aac32-275">The script uses the `.ExternalHelp` keyword to specify the path to an XML-based help topic for the script.</span></span>

<span data-ttu-id="aac32-276">请注意，关键字的值与 `.ExternalHelp` 关键字显示在同一行中。</span><span class="sxs-lookup"><span data-stu-id="aac32-276">Note that the value of the `.ExternalHelp` keyword appears on the same line as the keyword.</span></span> <span data-ttu-id="aac32-277">任何其他放置都是无效的。</span><span class="sxs-lookup"><span data-stu-id="aac32-277">Any other placement is ineffective.</span></span>

```powershell
# .ExternalHelp C:\MyScripts\Update-Month-Help.xml

param ([string]$InputPath, [string]$OutPutPath)
function Get-Data { }
...
```

<span data-ttu-id="aac32-278">下面的示例在函数中显示了三个有效的 `.ExternalHelp` 关键字位置。</span><span class="sxs-lookup"><span data-stu-id="aac32-278">The following examples show three valid placements of the `.ExternalHelp` keyword in a function.</span></span>

```powershell
function Add-Extension
{
# .ExternalHelp C:\ps-test\Add-Extension.xml

param ([string] $name, [string]$extension = "txt")
$name = $name + "." + $extension
$name
}
```

```powershell
function Add-Extension
{
param ([string] $name, [string]$extension = "txt")
$name = $name + "." + $extension
$name

# .ExternalHelp C:\ps-test\Add-Extension.xml
}
```

```powershell
# .ExternalHelp C:\ps-test\Add-Extension.xml
function Add-Extension
{
param ([string] $name, [string]$extension = "txt")
$name = $name + "." + $extension
$name
}
```

### <a name="redirecting-to-a-different-help-topic"></a><span data-ttu-id="aac32-279">重定向到其他帮助主题</span><span class="sxs-lookup"><span data-stu-id="aac32-279">Redirecting to a Different Help Topic</span></span>

<span data-ttu-id="aac32-280">下面的代码摘自 PowerShell 中内置帮助函数的开头部分，该函数一次显示一个屏幕帮助文本。</span><span class="sxs-lookup"><span data-stu-id="aac32-280">The following code is an excerpt from the beginning of the built-in help function in PowerShell, which displays one screen of help text at a time.</span></span>
<span data-ttu-id="aac32-281">由于 cmdlet 的帮助主题 `Get-Help` 描述了 help 函数，因此 help 函数使用 `.ForwardHelpTargetName` 和 `.ForwardHelpCategory` 关键字将用户重定向到 `Get-Help` cmdlet 帮助主题。</span><span class="sxs-lookup"><span data-stu-id="aac32-281">Because the help topic for the `Get-Help` cmdlet describes the help function, the help function uses the `.ForwardHelpTargetName` and `.ForwardHelpCategory` keywords to redirect the user to the `Get-Help` cmdlet help topic.</span></span>

```powershell
function help
{

<#
.FORWARDHELPTARGETNAME Get-Help
.FORWARDHELPCATEGORY Cmdlet
#>
[CmdletBinding(DefaultParameterSetName='AllUsersView')]
param(
[Parameter(Position=0, ValueFromPipelineByPropertyName=$true)]
[System.String]
${Name},
...
```

<span data-ttu-id="aac32-282">以下命令使用此功能：</span><span class="sxs-lookup"><span data-stu-id="aac32-282">The following command uses this feature:</span></span>

```powershell
Get-Help -Name help
```

```Output
NAME

Get-Help

SYNOPSIS

Displays information about PowerShell cmdlets and concepts.
...
```

## <a name="see-also"></a><span data-ttu-id="aac32-283">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aac32-283">See also</span></span>

[<span data-ttu-id="aac32-284">about_Functions</span><span class="sxs-lookup"><span data-stu-id="aac32-284">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="aac32-285">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="aac32-285">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="aac32-286">about_Scripts</span><span class="sxs-lookup"><span data-stu-id="aac32-286">about_Scripts</span></span>](about_Scripts.md)

[<span data-ttu-id="aac32-287">如何编写 Cmdlet 帮助</span><span class="sxs-lookup"><span data-stu-id="aac32-287">How to Write Cmdlet Help</span></span>](https://go.microsoft.com/fwlink/?LinkID=123415)