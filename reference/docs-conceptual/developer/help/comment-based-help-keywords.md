---
title: 基于注释的帮助关键字
ms.custom: ''
ms.date: 06/09/2020
ms.topic: article
ms.openlocfilehash: 674d0f99800595cbbd64a80d0e0c5aed22f3b45c
ms.sourcegitcommit: 4a283fe5419f47102e6c1de7060880a934842ee9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2020
ms.locfileid: "84671370"
---
# <a name="comment-based-help-keywords"></a><span data-ttu-id="cf5bd-102">基于注释的帮助关键字</span><span class="sxs-lookup"><span data-stu-id="cf5bd-102">Comment-Based Help Keywords</span></span>

<span data-ttu-id="cf5bd-103">本主题列出并描述了基于注释的帮助中的关键字。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-103">This topic lists and describes the keywords in comment-based help.</span></span>

## <a name="keywords-in-comment-based-help"></a><span data-ttu-id="cf5bd-104">基于注释的帮助中的关键字</span><span class="sxs-lookup"><span data-stu-id="cf5bd-104">Keywords in Comment-Based Help</span></span>

<span data-ttu-id="cf5bd-105">下面是有效的基于注释的帮助关键字。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-105">The following are valid comment-based Help keywords.</span></span> <span data-ttu-id="cf5bd-106">它们按其在帮助主题中通常出现的顺序列出，以及它们的预期用途。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-106">They are listed in the order in which they typically appear in a Help topic along with their intended use.</span></span> <span data-ttu-id="cf5bd-107">这些关键字可以在基于注释的帮助中以任意顺序出现，它们不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-107">These keywords can appear in any order in the comment-based Help, and they are not case-sensitive.</span></span>

<span data-ttu-id="cf5bd-108">请注意， `.EXTERNALHELP` 关键字优先于所有其他基于注释的帮助关键字。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-108">Note that the `.EXTERNALHELP` keyword takes precedence over all other comment-based help keywords.</span></span>
<span data-ttu-id="cf5bd-109">当 `.EXTERNALHELP` 存在时， [GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) cmdlet 不显示基于注释的帮助，即使找不到与关键字的值匹配的帮助文件也是如此。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-109">When `.EXTERNALHELP` is present, the [Microsoft.PowerShell.Commands.GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) cmdlet does not display comment-based help, even when it cannot find a help file that matches the value of the keyword.</span></span>

## <a name="synopsis"></a><span data-ttu-id="cf5bd-110">.概要</span><span class="sxs-lookup"><span data-stu-id="cf5bd-110">.SYNOPSIS</span></span>

<span data-ttu-id="cf5bd-111">函数或脚本的简短说明。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-111">A brief description of the function or script.</span></span> <span data-ttu-id="cf5bd-112">每个主题中只能使用一次此关键字。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-112">This keyword can be used only once in each topic.</span></span>

## <a name="description"></a><span data-ttu-id="cf5bd-113">.2008</span><span class="sxs-lookup"><span data-stu-id="cf5bd-113">.DESCRIPTION</span></span>

<span data-ttu-id="cf5bd-114">函数或脚本的详细说明。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-114">A detailed description of the function or script.</span></span> <span data-ttu-id="cf5bd-115">每个主题中只能使用一次此关键字。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-115">This keyword can be used only once in each topic.</span></span>

## <a name="parameter-parameter-name"></a><span data-ttu-id="cf5bd-116">.参数\<Parameter-Name></span><span class="sxs-lookup"><span data-stu-id="cf5bd-116">.PARAMETER \<Parameter-Name></span></span>

<span data-ttu-id="cf5bd-117">参数的说明。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-117">The description of a parameter.</span></span> <span data-ttu-id="cf5bd-118">可以 `.PARAMETER` 在函数或脚本中包含每个参数的关键字。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-118">You can include a `.PARAMETER` keyword for each parameter in the function or script.</span></span>

<span data-ttu-id="cf5bd-119">`.PARAMETER`关键字可以在注释块中以任意顺序出现，但参数在语句或函数声明中的显示顺序 `Param` 决定了参数在帮助主题中的显示顺序。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-119">The `.PARAMETER` keywords can appear in any order in the comment block, but the order in which the parameters appear in the `Param` statement or function declaration determines the order in which the parameters appear in Help topic.</span></span> <span data-ttu-id="cf5bd-120">若要更改帮助主题中参数的顺序，请更改 `Param` 语句或函数声明中参数的顺序。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-120">To change the order of parameters in the Help topic, change the order of the parameters in the `Param` statement or function declaration.</span></span>

<span data-ttu-id="cf5bd-121">您还可以通过将注释放在 `Param` 参数变量名称之前的语句中来指定参数说明。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-121">You can also specify a parameter description by placing a comment in the `Param` statement immediately before the parameter variable name.</span></span> <span data-ttu-id="cf5bd-122">如果同时使用 `Param` 语句注释和 `.PARAMETER` 关键字，则使用与关键字关联的说明 `.PARAMETER` ，并 `Param` 忽略语句注释。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-122">If you use both a `Param` statement comment and a `.PARAMETER` keyword, the description associated with the `.PARAMETER` keyword is used, and the `Param` statement comment is ignored.</span></span>

## <a name="example"></a><span data-ttu-id="cf5bd-123">.实例</span><span class="sxs-lookup"><span data-stu-id="cf5bd-123">.EXAMPLE</span></span>

<span data-ttu-id="cf5bd-124">使用函数或脚本的示例命令，可选择后跟示例输出和说明。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-124">A sample command that uses the function or script, optionally followed by sample output and a description.</span></span> <span data-ttu-id="cf5bd-125">为每个示例重复此关键字。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-125">Repeat this keyword for each example.</span></span>

## <a name="inputs"></a><span data-ttu-id="cf5bd-126">.输入</span><span class="sxs-lookup"><span data-stu-id="cf5bd-126">.INPUTS</span></span>

<span data-ttu-id="cf5bd-127">可以通过管道传递给函数或脚本的对象的 Microsoft .NET 框架类型。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-127">The Microsoft .NET Framework types of objects that can be piped to the function or script.</span></span> <span data-ttu-id="cf5bd-128">还可以包括对输入对象的描述。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-128">You can also include a description of the input objects.</span></span>

## <a name="outputs"></a><span data-ttu-id="cf5bd-129">.输出</span><span class="sxs-lookup"><span data-stu-id="cf5bd-129">.OUTPUTS</span></span>

<span data-ttu-id="cf5bd-130">Cmdlet 返回的对象的 .NET Framework 类型。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-130">The .NET Framework type of the objects that the cmdlet returns.</span></span> <span data-ttu-id="cf5bd-131">还可以包括返回对象的描述。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-131">You can also include a description of the returned objects.</span></span>

## <a name="notes"></a><span data-ttu-id="cf5bd-132">.本票</span><span class="sxs-lookup"><span data-stu-id="cf5bd-132">.NOTES</span></span>

<span data-ttu-id="cf5bd-133">有关函数或脚本的其他信息。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-133">Additional information about the function or script.</span></span>

## <a name="link"></a><span data-ttu-id="cf5bd-134">.连接</span><span class="sxs-lookup"><span data-stu-id="cf5bd-134">.LINK</span></span>

<span data-ttu-id="cf5bd-135">相关主题的名称。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-135">The name of a related topic.</span></span> <span data-ttu-id="cf5bd-136">为每个相关主题重复此关键字。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-136">Repeat this keyword for each related topic.</span></span> <span data-ttu-id="cf5bd-137">此内容显示在帮助主题的 "相关链接" 部分中。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-137">This content appears in the Related Links section of the Help topic.</span></span>

<span data-ttu-id="cf5bd-138">`.LINK`关键字 content 还可以将统一资源标识符（URI）包含到同一个帮助主题的联机版本。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-138">The `.LINK` keyword content can also include a Uniform Resource Identifier (URI) to an online version of the same Help topic.</span></span> <span data-ttu-id="cf5bd-139">当你使用的参数时，将打开联机版本 `Online` `Get-Help` 。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-139">The online version opens when you use the `Online` parameter of `Get-Help`.</span></span> <span data-ttu-id="cf5bd-140">URI 必须以 "http" 或 "https" 开头。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-140">The URI must begin with "http" or "https".</span></span>

## <a name="component"></a><span data-ttu-id="cf5bd-141">.组件</span><span class="sxs-lookup"><span data-stu-id="cf5bd-141">.COMPONENT</span></span>

<span data-ttu-id="cf5bd-142">函数或脚本使用或与之相关的技术或功能的名称。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-142">The name of the technology or feature that the function or script uses, or to which it is related.</span></span>
<span data-ttu-id="cf5bd-143">的**组件**参数 `Get-Help` 使用此值来筛选返回的搜索结果 `Get-Help` 。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-143">The **Component** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

## <a name="role"></a><span data-ttu-id="cf5bd-144">.职位</span><span class="sxs-lookup"><span data-stu-id="cf5bd-144">.Role</span></span>

<span data-ttu-id="cf5bd-145">帮助主题的用户角色的名称。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-145">The name of the user role for the help topic.</span></span> <span data-ttu-id="cf5bd-146">的**Role**参数 `Get-Help` 使用此值来筛选返回的搜索结果 `Get-Help` 。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-146">The **Role** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

## <a name="functionality"></a><span data-ttu-id="cf5bd-147">.性能</span><span class="sxs-lookup"><span data-stu-id="cf5bd-147">.FUNCTIONALITY</span></span>

<span data-ttu-id="cf5bd-148">描述函数的预期用途的关键字。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-148">The keywords that describe the intended use of the function.</span></span> <span data-ttu-id="cf5bd-149">的**功能**参数 `Get-Help` 使用此值来筛选返回的搜索结果 `Get-Help` 。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-149">The **Functionality** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

## <a name="forwardhelptargetname-command-name"></a><span data-ttu-id="cf5bd-150">.FORWARDHELPTARGETNAME\<Command-Name></span><span class="sxs-lookup"><span data-stu-id="cf5bd-150">.FORWARDHELPTARGETNAME \<Command-Name></span></span>

<span data-ttu-id="cf5bd-151">重定向到指定命令的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-151">Redirects to the Help topic for the specified command.</span></span> <span data-ttu-id="cf5bd-152">您可以将用户重定向到任何帮助主题，包括函数、脚本、cmdlet 或提供程序的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-152">You can redirect users to any Help topic, including Help topics for a function, script, cmdlet, or provider.</span></span>

## <a name="forwardhelpcategory-category"></a><span data-ttu-id="cf5bd-153">.FORWARDHELPCATEGORY\<Category></span><span class="sxs-lookup"><span data-stu-id="cf5bd-153">.FORWARDHELPCATEGORY \<Category></span></span>

<span data-ttu-id="cf5bd-154">指定中的项的帮助类别 `.FORWARDHELPTARGETNAME` 。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-154">Specifies the Help category of the item in `.FORWARDHELPTARGETNAME`.</span></span> <span data-ttu-id="cf5bd-155">当存在具有相同名称的命令时，请使用此关键字避免冲突。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-155">Use this keyword to avoid conflicts when there are commands with the same name.</span></span>

<span data-ttu-id="cf5bd-156">有效值是：</span><span class="sxs-lookup"><span data-stu-id="cf5bd-156">Valid values are:</span></span>

- <span data-ttu-id="cf5bd-157">别名</span><span class="sxs-lookup"><span data-stu-id="cf5bd-157">Alias</span></span>
- <span data-ttu-id="cf5bd-158">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="cf5bd-158">Cmdlet</span></span>
- <span data-ttu-id="cf5bd-159">HelpFile</span><span class="sxs-lookup"><span data-stu-id="cf5bd-159">HelpFile</span></span>
- <span data-ttu-id="cf5bd-160">函数</span><span class="sxs-lookup"><span data-stu-id="cf5bd-160">Function</span></span>
- <span data-ttu-id="cf5bd-161">提供程序</span><span class="sxs-lookup"><span data-stu-id="cf5bd-161">Provider</span></span>
- <span data-ttu-id="cf5bd-162">常规</span><span class="sxs-lookup"><span data-stu-id="cf5bd-162">General</span></span>
- <span data-ttu-id="cf5bd-163">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="cf5bd-163">FAQ</span></span>
- <span data-ttu-id="cf5bd-164">术语表</span><span class="sxs-lookup"><span data-stu-id="cf5bd-164">Glossary</span></span>
- <span data-ttu-id="cf5bd-165">ScriptCommand</span><span class="sxs-lookup"><span data-stu-id="cf5bd-165">ScriptCommand</span></span>
- <span data-ttu-id="cf5bd-166">ExternalScript</span><span class="sxs-lookup"><span data-stu-id="cf5bd-166">ExternalScript</span></span>
- <span data-ttu-id="cf5bd-167">筛选器</span><span class="sxs-lookup"><span data-stu-id="cf5bd-167">Filter</span></span>
- <span data-ttu-id="cf5bd-168">全部</span><span class="sxs-lookup"><span data-stu-id="cf5bd-168">All</span></span>

## <a name="remotehelprunspace-pssession-variable"></a><span data-ttu-id="cf5bd-169">.REMOTEHELPRUNSPACE\<PSSession-variable></span><span class="sxs-lookup"><span data-stu-id="cf5bd-169">.REMOTEHELPRUNSPACE \<PSSession-variable></span></span>

<span data-ttu-id="cf5bd-170">指定包含 "帮助" 主题的会话。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-170">Specifies a session that contains the Help topic.</span></span> <span data-ttu-id="cf5bd-171">输入包含 PSSession 的变量。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-171">Enter a variable that contains a PSSession.</span></span> <span data-ttu-id="cf5bd-172">Cmdlet 使用此关键字 `Export-PSSession` 查找导出的命令的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-172">This keyword is used by the `Export-PSSession` cmdlet to find the Help topics for the exported commands.</span></span>

## <a name="externalhelp-xml-help-file"></a><span data-ttu-id="cf5bd-173">..EXTERNALHELP\<XML Help File></span><span class="sxs-lookup"><span data-stu-id="cf5bd-173">.EXTERNALHELP \<XML Help File></span></span>

<span data-ttu-id="cf5bd-174">为脚本或函数指定基于 XML 的帮助文件的路径和/或名称。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-174">Specifies the path and/or name of an XML-based Help file for the script or function.</span></span>

<span data-ttu-id="cf5bd-175">`.EXTERNALHELP`关键字指示[GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) cmdlet 获取有关基于 XML 的文件中的脚本或函数的帮助。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-175">The `.EXTERNALHELP` keyword tells the [Microsoft.PowerShell.Commands.GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) cmdlet to get help for the script or function in an XML-based file.</span></span> <span data-ttu-id="cf5bd-176">`.EXTERNALHELP`对脚本或函数使用基于 XML 的帮助文件时，需要使用关键字。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-176">The `.EXTERNALHELP` keyword is required when using an XML-based help file for a script or function.</span></span> <span data-ttu-id="cf5bd-177">如果没有此 `Get-Help` 功能，将找不到该函数或脚本的帮助文件。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-177">Without it, `Get-Help` will not find a help file for the function or script.</span></span>

<span data-ttu-id="cf5bd-178">`.EXTERNALHELP`关键字优先于所有其他基于注释的帮助关键字。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-178">The `.EXTERNALHELP` keyword takes precedence over all other comment-based help keywords.</span></span> <span data-ttu-id="cf5bd-179">当 `.EXTERNALHELP` 存在时， [GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) cmdlet 不显示基于注释的帮助，即使找不到与关键字的值匹配的帮助文件也是如此。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-179">When `.EXTERNALHELP` is present, the [Microsoft.PowerShell.Commands.GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) cmdlet does not display comment-based help, even when it cannot find a help file that matches the value of the keyword.</span></span>

<span data-ttu-id="cf5bd-180">当脚本模块导出函数时，的值 `.EXTERNALHELP` 应为不带路径的文件名。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-180">When the function is exported by a script module, the value of `.EXTERNALHELP` should be a filename without a path.</span></span> <span data-ttu-id="cf5bd-181">`Get-Help`在模块目录的特定于区域设置的子目录中查找文件。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-181">`Get-Help` looks for the file in a locale-specific subdirectory of the module directory.</span></span> <span data-ttu-id="cf5bd-182">文件名没有任何要求，但最佳做法是使用以下文件名格式： `<ScriptModule>.psm1-help.xml` 。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-182">There are no requirements for the filename, but a best practice is to use the following filename format: `<ScriptModule>.psm1-help.xml`.</span></span>

<span data-ttu-id="cf5bd-183">如果函数不与模块相关联，请在关键字的值中包含路径和文件名 `.EXTERNALHELP` 。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-183">When the function is not associated with a module, include a path and filename in the value of the `.EXTERNALHELP` keyword.</span></span> <span data-ttu-id="cf5bd-184">如果 XML 文件的指定路径包含特定于 UI 区域性的子目录，则 `Get-Help` 会以递归方式搜索包含脚本或函数名称的 xml 文件的子目录，就像为 Windows 建立的语言回退标准一样。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-184">If the specified path to the XML file contains UI-culture-specific subdirectories, `Get-Help` searches the subdirectories recursively for an XML file with the name of the script or function in accordance with the language fallback standards established for Windows, just as it does for all XML-based Help topics.</span></span>

<span data-ttu-id="cf5bd-185">有关 cmdlet 帮助基于 XML 的帮助文件格式的详细信息，请参阅[编写 Windows PowerShell Cmdlet 帮助](./writing-help-for-windows-powershell-cmdlets.md)。</span><span class="sxs-lookup"><span data-stu-id="cf5bd-185">For more information about the cmdlet Help XML-based Help file format, see [Writing Windows PowerShell Cmdlet Help](./writing-help-for-windows-powershell-cmdlets.md).</span></span>
