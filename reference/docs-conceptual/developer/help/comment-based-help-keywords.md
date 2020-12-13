---
ms.date: 06/09/2020
ms.topic: reference
title: 基于注释的帮助关键字
description: 基于注释的帮助关键字
ms.openlocfilehash: d87dde8700813767f6c09cfce70ed06c7964ebc7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645470"
---
# <a name="comment-based-help-keywords"></a><span data-ttu-id="6c50e-103">基于注释的帮助关键字</span><span class="sxs-lookup"><span data-stu-id="6c50e-103">Comment-Based Help Keywords</span></span>

<span data-ttu-id="6c50e-104">本主题列出并描述了基于注释的帮助中的关键字。</span><span class="sxs-lookup"><span data-stu-id="6c50e-104">This topic lists and describes the keywords in comment-based help.</span></span>

## <a name="keywords-in-comment-based-help"></a><span data-ttu-id="6c50e-105">Comment-Based 帮助中的关键字</span><span class="sxs-lookup"><span data-stu-id="6c50e-105">Keywords in Comment-Based Help</span></span>

<span data-ttu-id="6c50e-106">下面是有效的基于注释的帮助关键字。</span><span class="sxs-lookup"><span data-stu-id="6c50e-106">The following are valid comment-based Help keywords.</span></span> <span data-ttu-id="6c50e-107">它们按其在帮助主题中通常出现的顺序列出，以及它们的预期用途。</span><span class="sxs-lookup"><span data-stu-id="6c50e-107">They are listed in the order in which they typically appear in a Help topic along with their intended use.</span></span> <span data-ttu-id="6c50e-108">这些关键字可以在基于注释的帮助中以任意顺序出现，它们不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="6c50e-108">These keywords can appear in any order in the comment-based Help, and they are not case-sensitive.</span></span>

<span data-ttu-id="6c50e-109">请注意， `.EXTERNALHELP` 关键字优先于所有其他基于注释的帮助关键字。</span><span class="sxs-lookup"><span data-stu-id="6c50e-109">Note that the `.EXTERNALHELP` keyword takes precedence over all other comment-based help keywords.</span></span>
<span data-ttu-id="6c50e-110">当 `.EXTERNALHELP` 存在时， [GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) cmdlet 不显示基于注释的帮助，即使找不到与关键字的值匹配的帮助文件也是如此。</span><span class="sxs-lookup"><span data-stu-id="6c50e-110">When `.EXTERNALHELP` is present, the [Microsoft.PowerShell.Commands.GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) cmdlet does not display comment-based help, even when it cannot find a help file that matches the value of the keyword.</span></span>

## <a name="synopsis"></a><span data-ttu-id="6c50e-111">.概要</span><span class="sxs-lookup"><span data-stu-id="6c50e-111">.SYNOPSIS</span></span>

<span data-ttu-id="6c50e-112">函数或脚本的简短说明。</span><span class="sxs-lookup"><span data-stu-id="6c50e-112">A brief description of the function or script.</span></span> <span data-ttu-id="6c50e-113">每个主题中只能使用一次此关键字。</span><span class="sxs-lookup"><span data-stu-id="6c50e-113">This keyword can be used only once in each topic.</span></span>

## <a name="description"></a><span data-ttu-id="6c50e-114">.2008</span><span class="sxs-lookup"><span data-stu-id="6c50e-114">.DESCRIPTION</span></span>

<span data-ttu-id="6c50e-115">函数或脚本的详细说明。</span><span class="sxs-lookup"><span data-stu-id="6c50e-115">A detailed description of the function or script.</span></span> <span data-ttu-id="6c50e-116">每个主题中只能使用一次此关键字。</span><span class="sxs-lookup"><span data-stu-id="6c50e-116">This keyword can be used only once in each topic.</span></span>

## <a name="parameter-parameter-name"></a><span data-ttu-id="6c50e-117">.参数 \<Parameter-Name></span><span class="sxs-lookup"><span data-stu-id="6c50e-117">.PARAMETER \<Parameter-Name></span></span>

<span data-ttu-id="6c50e-118">参数的说明。</span><span class="sxs-lookup"><span data-stu-id="6c50e-118">The description of a parameter.</span></span> <span data-ttu-id="6c50e-119">可以 `.PARAMETER` 在函数或脚本中包含每个参数的关键字。</span><span class="sxs-lookup"><span data-stu-id="6c50e-119">You can include a `.PARAMETER` keyword for each parameter in the function or script.</span></span>

<span data-ttu-id="6c50e-120">`.PARAMETER`关键字可以在注释块中以任意顺序出现，但参数在语句或函数声明中的显示顺序 `Param` 决定了参数在帮助主题中的显示顺序。</span><span class="sxs-lookup"><span data-stu-id="6c50e-120">The `.PARAMETER` keywords can appear in any order in the comment block, but the order in which the parameters appear in the `Param` statement or function declaration determines the order in which the parameters appear in Help topic.</span></span> <span data-ttu-id="6c50e-121">若要更改帮助主题中参数的顺序，请更改 `Param` 语句或函数声明中参数的顺序。</span><span class="sxs-lookup"><span data-stu-id="6c50e-121">To change the order of parameters in the Help topic, change the order of the parameters in the `Param` statement or function declaration.</span></span>

<span data-ttu-id="6c50e-122">您还可以通过将注释放在 `Param` 参数变量名称之前的语句中来指定参数说明。</span><span class="sxs-lookup"><span data-stu-id="6c50e-122">You can also specify a parameter description by placing a comment in the `Param` statement immediately before the parameter variable name.</span></span> <span data-ttu-id="6c50e-123">如果同时使用 `Param` 语句注释和 `.PARAMETER` 关键字，则使用与关键字关联的说明 `.PARAMETER` ，并 `Param` 忽略语句注释。</span><span class="sxs-lookup"><span data-stu-id="6c50e-123">If you use both a `Param` statement comment and a `.PARAMETER` keyword, the description associated with the `.PARAMETER` keyword is used, and the `Param` statement comment is ignored.</span></span>

## <a name="example"></a><span data-ttu-id="6c50e-124">.实例</span><span class="sxs-lookup"><span data-stu-id="6c50e-124">.EXAMPLE</span></span>

<span data-ttu-id="6c50e-125">使用函数或脚本的示例命令，可选择后跟示例输出和说明。</span><span class="sxs-lookup"><span data-stu-id="6c50e-125">A sample command that uses the function or script, optionally followed by sample output and a description.</span></span> <span data-ttu-id="6c50e-126">为每个示例重复此关键字。</span><span class="sxs-lookup"><span data-stu-id="6c50e-126">Repeat this keyword for each example.</span></span>

## <a name="inputs"></a><span data-ttu-id="6c50e-127">.输入</span><span class="sxs-lookup"><span data-stu-id="6c50e-127">.INPUTS</span></span>

<span data-ttu-id="6c50e-128">可以通过管道传递给函数或脚本的对象的 Microsoft .NET 框架类型。</span><span class="sxs-lookup"><span data-stu-id="6c50e-128">The Microsoft .NET Framework types of objects that can be piped to the function or script.</span></span> <span data-ttu-id="6c50e-129">还可以包括对输入对象的描述。</span><span class="sxs-lookup"><span data-stu-id="6c50e-129">You can also include a description of the input objects.</span></span>

## <a name="outputs"></a><span data-ttu-id="6c50e-130">.输出</span><span class="sxs-lookup"><span data-stu-id="6c50e-130">.OUTPUTS</span></span>

<span data-ttu-id="6c50e-131">Cmdlet 返回的对象的 .NET Framework 类型。</span><span class="sxs-lookup"><span data-stu-id="6c50e-131">The .NET Framework type of the objects that the cmdlet returns.</span></span> <span data-ttu-id="6c50e-132">还可以包括返回对象的描述。</span><span class="sxs-lookup"><span data-stu-id="6c50e-132">You can also include a description of the returned objects.</span></span>

## <a name="notes"></a><span data-ttu-id="6c50e-133">.本票</span><span class="sxs-lookup"><span data-stu-id="6c50e-133">.NOTES</span></span>

<span data-ttu-id="6c50e-134">有关函数或脚本的其他信息。</span><span class="sxs-lookup"><span data-stu-id="6c50e-134">Additional information about the function or script.</span></span>

## <a name="link"></a><span data-ttu-id="6c50e-135">.连接</span><span class="sxs-lookup"><span data-stu-id="6c50e-135">.LINK</span></span>

<span data-ttu-id="6c50e-136">相关主题的名称。</span><span class="sxs-lookup"><span data-stu-id="6c50e-136">The name of a related topic.</span></span> <span data-ttu-id="6c50e-137">为每个相关主题重复此关键字。</span><span class="sxs-lookup"><span data-stu-id="6c50e-137">Repeat this keyword for each related topic.</span></span> <span data-ttu-id="6c50e-138">此内容显示在帮助主题的 "相关链接" 部分中。</span><span class="sxs-lookup"><span data-stu-id="6c50e-138">This content appears in the Related Links section of the Help topic.</span></span>

<span data-ttu-id="6c50e-139">`.LINK`关键字内容还可以包含统一资源标识符 (URI) 到同一帮助主题的联机版本。</span><span class="sxs-lookup"><span data-stu-id="6c50e-139">The `.LINK` keyword content can also include a Uniform Resource Identifier (URI) to an online version of the same Help topic.</span></span> <span data-ttu-id="6c50e-140">当你使用的参数时，将打开联机版本 `Online` `Get-Help` 。</span><span class="sxs-lookup"><span data-stu-id="6c50e-140">The online version opens when you use the `Online` parameter of `Get-Help`.</span></span> <span data-ttu-id="6c50e-141">URI 必须以 "http" 或 "https" 开头。</span><span class="sxs-lookup"><span data-stu-id="6c50e-141">The URI must begin with "http" or "https".</span></span>

## <a name="component"></a><span data-ttu-id="6c50e-142">.组件</span><span class="sxs-lookup"><span data-stu-id="6c50e-142">.COMPONENT</span></span>

<span data-ttu-id="6c50e-143">函数或脚本使用或与之相关的技术或功能的名称。</span><span class="sxs-lookup"><span data-stu-id="6c50e-143">The name of the technology or feature that the function or script uses, or to which it is related.</span></span>
<span data-ttu-id="6c50e-144">的 **组件** 参数 `Get-Help` 使用此值来筛选返回的搜索结果 `Get-Help` 。</span><span class="sxs-lookup"><span data-stu-id="6c50e-144">The **Component** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

## <a name="role"></a><span data-ttu-id="6c50e-145">.职位</span><span class="sxs-lookup"><span data-stu-id="6c50e-145">.Role</span></span>

<span data-ttu-id="6c50e-146">帮助主题的用户角色的名称。</span><span class="sxs-lookup"><span data-stu-id="6c50e-146">The name of the user role for the help topic.</span></span> <span data-ttu-id="6c50e-147">的 **Role** 参数 `Get-Help` 使用此值来筛选返回的搜索结果 `Get-Help` 。</span><span class="sxs-lookup"><span data-stu-id="6c50e-147">The **Role** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

## <a name="functionality"></a><span data-ttu-id="6c50e-148">.性能</span><span class="sxs-lookup"><span data-stu-id="6c50e-148">.FUNCTIONALITY</span></span>

<span data-ttu-id="6c50e-149">描述函数的预期用途的关键字。</span><span class="sxs-lookup"><span data-stu-id="6c50e-149">The keywords that describe the intended use of the function.</span></span> <span data-ttu-id="6c50e-150">的 **功能** 参数 `Get-Help` 使用此值来筛选返回的搜索结果 `Get-Help` 。</span><span class="sxs-lookup"><span data-stu-id="6c50e-150">The **Functionality** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

## <a name="forwardhelptargetname-command-name"></a><span data-ttu-id="6c50e-151">.FORWARDHELPTARGETNAME \<Command-Name></span><span class="sxs-lookup"><span data-stu-id="6c50e-151">.FORWARDHELPTARGETNAME \<Command-Name></span></span>

<span data-ttu-id="6c50e-152">重定向到指定命令的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="6c50e-152">Redirects to the Help topic for the specified command.</span></span> <span data-ttu-id="6c50e-153">您可以将用户重定向到任何帮助主题，包括函数、脚本、cmdlet 或提供程序的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="6c50e-153">You can redirect users to any Help topic, including Help topics for a function, script, cmdlet, or provider.</span></span>

## <a name="forwardhelpcategory-category"></a><span data-ttu-id="6c50e-154">.FORWARDHELPCATEGORY \<Category></span><span class="sxs-lookup"><span data-stu-id="6c50e-154">.FORWARDHELPCATEGORY \<Category></span></span>

<span data-ttu-id="6c50e-155">指定中的项的帮助类别 `.FORWARDHELPTARGETNAME` 。</span><span class="sxs-lookup"><span data-stu-id="6c50e-155">Specifies the Help category of the item in `.FORWARDHELPTARGETNAME`.</span></span> <span data-ttu-id="6c50e-156">当存在具有相同名称的命令时，请使用此关键字避免冲突。</span><span class="sxs-lookup"><span data-stu-id="6c50e-156">Use this keyword to avoid conflicts when there are commands with the same name.</span></span>

<span data-ttu-id="6c50e-157">有效值是：</span><span class="sxs-lookup"><span data-stu-id="6c50e-157">Valid values are:</span></span>

- <span data-ttu-id="6c50e-158">Alias</span><span class="sxs-lookup"><span data-stu-id="6c50e-158">Alias</span></span>
- <span data-ttu-id="6c50e-159">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="6c50e-159">Cmdlet</span></span>
- <span data-ttu-id="6c50e-160">HelpFile</span><span class="sxs-lookup"><span data-stu-id="6c50e-160">HelpFile</span></span>
- <span data-ttu-id="6c50e-161">函数</span><span class="sxs-lookup"><span data-stu-id="6c50e-161">Function</span></span>
- <span data-ttu-id="6c50e-162">提供程序</span><span class="sxs-lookup"><span data-stu-id="6c50e-162">Provider</span></span>
- <span data-ttu-id="6c50e-163">常规</span><span class="sxs-lookup"><span data-stu-id="6c50e-163">General</span></span>
- <span data-ttu-id="6c50e-164">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="6c50e-164">FAQ</span></span>
- <span data-ttu-id="6c50e-165">术语表</span><span class="sxs-lookup"><span data-stu-id="6c50e-165">Glossary</span></span>
- <span data-ttu-id="6c50e-166">ScriptCommand</span><span class="sxs-lookup"><span data-stu-id="6c50e-166">ScriptCommand</span></span>
- <span data-ttu-id="6c50e-167">ExternalScript</span><span class="sxs-lookup"><span data-stu-id="6c50e-167">ExternalScript</span></span>
- <span data-ttu-id="6c50e-168">筛选器</span><span class="sxs-lookup"><span data-stu-id="6c50e-168">Filter</span></span>
- <span data-ttu-id="6c50e-169">全部</span><span class="sxs-lookup"><span data-stu-id="6c50e-169">All</span></span>

## <a name="remotehelprunspace-pssession-variable"></a><span data-ttu-id="6c50e-170">.REMOTEHELPRUNSPACE \<PSSession-variable></span><span class="sxs-lookup"><span data-stu-id="6c50e-170">.REMOTEHELPRUNSPACE \<PSSession-variable></span></span>

<span data-ttu-id="6c50e-171">指定包含 "帮助" 主题的会话。</span><span class="sxs-lookup"><span data-stu-id="6c50e-171">Specifies a session that contains the Help topic.</span></span> <span data-ttu-id="6c50e-172">输入包含 PSSession 的变量。</span><span class="sxs-lookup"><span data-stu-id="6c50e-172">Enter a variable that contains a PSSession.</span></span> <span data-ttu-id="6c50e-173">Cmdlet 使用此关键字 `Export-PSSession` 查找导出的命令的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="6c50e-173">This keyword is used by the `Export-PSSession` cmdlet to find the Help topics for the exported commands.</span></span>

## <a name="externalhelp-xml-help-file"></a><span data-ttu-id="6c50e-174">..EXTERNALHELP \<XML Help File></span><span class="sxs-lookup"><span data-stu-id="6c50e-174">.EXTERNALHELP \<XML Help File></span></span>

<span data-ttu-id="6c50e-175">为脚本或函数指定基于 XML 的帮助文件的路径和/或名称。</span><span class="sxs-lookup"><span data-stu-id="6c50e-175">Specifies the path and/or name of an XML-based Help file for the script or function.</span></span>

<span data-ttu-id="6c50e-176">`.EXTERNALHELP`关键字指示[GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) cmdlet 获取有关基于 XML 的文件中的脚本或函数的帮助。</span><span class="sxs-lookup"><span data-stu-id="6c50e-176">The `.EXTERNALHELP` keyword tells the [Microsoft.PowerShell.Commands.GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) cmdlet to get help for the script or function in an XML-based file.</span></span> <span data-ttu-id="6c50e-177">`.EXTERNALHELP`对脚本或函数使用基于 XML 的帮助文件时，需要使用关键字。</span><span class="sxs-lookup"><span data-stu-id="6c50e-177">The `.EXTERNALHELP` keyword is required when using an XML-based help file for a script or function.</span></span> <span data-ttu-id="6c50e-178">如果没有此 `Get-Help` 功能，将找不到该函数或脚本的帮助文件。</span><span class="sxs-lookup"><span data-stu-id="6c50e-178">Without it, `Get-Help` will not find a help file for the function or script.</span></span>

<span data-ttu-id="6c50e-179">`.EXTERNALHELP`关键字优先于所有其他基于注释的帮助关键字。</span><span class="sxs-lookup"><span data-stu-id="6c50e-179">The `.EXTERNALHELP` keyword takes precedence over all other comment-based help keywords.</span></span> <span data-ttu-id="6c50e-180">当 `.EXTERNALHELP` 存在时， [GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) cmdlet 不显示基于注释的帮助，即使找不到与关键字的值匹配的帮助文件也是如此。</span><span class="sxs-lookup"><span data-stu-id="6c50e-180">When `.EXTERNALHELP` is present, the [Microsoft.PowerShell.Commands.GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) cmdlet does not display comment-based help, even when it cannot find a help file that matches the value of the keyword.</span></span>

<span data-ttu-id="6c50e-181">当脚本模块导出函数时，的值 `.EXTERNALHELP` 应为不带路径的文件名。</span><span class="sxs-lookup"><span data-stu-id="6c50e-181">When the function is exported by a script module, the value of `.EXTERNALHELP` should be a filename without a path.</span></span> <span data-ttu-id="6c50e-182">`Get-Help` 在模块目录的特定于区域设置的子目录中查找文件。</span><span class="sxs-lookup"><span data-stu-id="6c50e-182">`Get-Help` looks for the file in a locale-specific subdirectory of the module directory.</span></span> <span data-ttu-id="6c50e-183">文件名没有任何要求，但最佳做法是使用以下文件名格式： `<ScriptModule>.psm1-help.xml` 。</span><span class="sxs-lookup"><span data-stu-id="6c50e-183">There are no requirements for the filename, but a best practice is to use the following filename format: `<ScriptModule>.psm1-help.xml`.</span></span>

<span data-ttu-id="6c50e-184">如果函数不与模块相关联，请在关键字的值中包含路径和文件名 `.EXTERNALHELP` 。</span><span class="sxs-lookup"><span data-stu-id="6c50e-184">When the function is not associated with a module, include a path and filename in the value of the `.EXTERNALHELP` keyword.</span></span> <span data-ttu-id="6c50e-185">如果 XML 文件的指定路径包含特定于 UI 区域性的子目录，则 `Get-Help` 会以递归方式搜索包含脚本或函数名称的 xml 文件的子目录，就像为 Windows 建立的语言回退标准一样。</span><span class="sxs-lookup"><span data-stu-id="6c50e-185">If the specified path to the XML file contains UI-culture-specific subdirectories, `Get-Help` searches the subdirectories recursively for an XML file with the name of the script or function in accordance with the language fallback standards established for Windows, just as it does for all XML-based Help topics.</span></span>

<span data-ttu-id="6c50e-186">有关 cmdlet 帮助基于 XML 的帮助文件格式的详细信息，请参阅 [编写 Windows PowerShell Cmdlet 帮助](./writing-help-for-windows-powershell-cmdlets.md)。</span><span class="sxs-lookup"><span data-stu-id="6c50e-186">For more information about the cmdlet Help XML-based Help file format, see [Writing Windows PowerShell Cmdlet Help](./writing-help-for-windows-powershell-cmdlets.md).</span></span>
