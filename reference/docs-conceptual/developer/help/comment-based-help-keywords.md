---
title: 基于注释的帮助关键字
ms.date: 06/09/2020
ms.openlocfilehash: fb737c19d7b7f4d003af3ba36bb396bac52d94e7
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893146"
---
# <a name="comment-based-help-keywords"></a>基于注释的帮助关键字

本主题列出并描述了基于注释的帮助中的关键字。

## <a name="keywords-in-comment-based-help"></a>基于注释的帮助中的关键字

下面是有效的基于注释的帮助关键字。 它们按其在帮助主题中通常出现的顺序列出，以及它们的预期用途。 这些关键字可以在基于注释的帮助中以任意顺序出现，它们不区分大小写。

请注意， `.EXTERNALHELP` 关键字优先于所有其他基于注释的帮助关键字。
当 `.EXTERNALHELP` 存在时， [GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) cmdlet 不显示基于注释的帮助，即使找不到与关键字的值匹配的帮助文件也是如此。

## <a name="synopsis"></a>.概要

函数或脚本的简短说明。 每个主题中只能使用一次此关键字。

## <a name="description"></a>.2008

函数或脚本的详细说明。 每个主题中只能使用一次此关键字。

## <a name="parameter-parameter-name"></a>.参数\<Parameter-Name>

参数的说明。 可以 `.PARAMETER` 在函数或脚本中包含每个参数的关键字。

`.PARAMETER`关键字可以在注释块中以任意顺序出现，但参数在语句或函数声明中的显示顺序 `Param` 决定了参数在帮助主题中的显示顺序。 若要更改帮助主题中参数的顺序，请更改 `Param` 语句或函数声明中参数的顺序。

您还可以通过将注释放在 `Param` 参数变量名称之前的语句中来指定参数说明。 如果同时使用 `Param` 语句注释和 `.PARAMETER` 关键字，则使用与关键字关联的说明 `.PARAMETER` ，并 `Param` 忽略语句注释。

## <a name="example"></a>.实例

使用函数或脚本的示例命令，可选择后跟示例输出和说明。 为每个示例重复此关键字。

## <a name="inputs"></a>.输入

可以通过管道传递给函数或脚本的对象的 Microsoft .NET 框架类型。 还可以包括对输入对象的描述。

## <a name="outputs"></a>.输出

Cmdlet 返回的对象的 .NET Framework 类型。 还可以包括返回对象的描述。

## <a name="notes"></a>.本票

有关函数或脚本的其他信息。

## <a name="link"></a>.连接

相关主题的名称。 为每个相关主题重复此关键字。 此内容显示在帮助主题的 "相关链接" 部分中。

`.LINK`关键字 content 还可以将统一资源标识符（URI）包含到同一个帮助主题的联机版本。 当你使用的参数时，将打开联机版本 `Online` `Get-Help` 。 URI 必须以 "http" 或 "https" 开头。

## <a name="component"></a>.组件

函数或脚本使用或与之相关的技术或功能的名称。
的**组件**参数 `Get-Help` 使用此值来筛选返回的搜索结果 `Get-Help` 。

## <a name="role"></a>.职位

帮助主题的用户角色的名称。 的**Role**参数 `Get-Help` 使用此值来筛选返回的搜索结果 `Get-Help` 。

## <a name="functionality"></a>.性能

描述函数的预期用途的关键字。 的**功能**参数 `Get-Help` 使用此值来筛选返回的搜索结果 `Get-Help` 。

## <a name="forwardhelptargetname-command-name"></a>.FORWARDHELPTARGETNAME\<Command-Name>

重定向到指定命令的帮助主题。 您可以将用户重定向到任何帮助主题，包括函数、脚本、cmdlet 或提供程序的帮助主题。

## <a name="forwardhelpcategory-category"></a>.FORWARDHELPCATEGORY\<Category>

指定中的项的帮助类别 `.FORWARDHELPTARGETNAME` 。 当存在具有相同名称的命令时，请使用此关键字避免冲突。

有效值是：

- Alias
- Cmdlet
- HelpFile
- 函数
- 提供程序
- 常规
- 常见问题解答
- 术语表
- ScriptCommand
- ExternalScript
- 筛选器
- 全部

## <a name="remotehelprunspace-pssession-variable"></a>.REMOTEHELPRUNSPACE\<PSSession-variable>

指定包含 "帮助" 主题的会话。 输入包含 PSSession 的变量。 Cmdlet 使用此关键字 `Export-PSSession` 查找导出的命令的帮助主题。

## <a name="externalhelp-xml-help-file"></a>..EXTERNALHELP\<XML Help File>

为脚本或函数指定基于 XML 的帮助文件的路径和/或名称。

`.EXTERNALHELP`关键字指示[GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) cmdlet 获取有关基于 XML 的文件中的脚本或函数的帮助。 `.EXTERNALHELP`对脚本或函数使用基于 XML 的帮助文件时，需要使用关键字。 如果没有此 `Get-Help` 功能，将找不到该函数或脚本的帮助文件。

`.EXTERNALHELP`关键字优先于所有其他基于注释的帮助关键字。 当 `.EXTERNALHELP` 存在时， [GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) cmdlet 不显示基于注释的帮助，即使找不到与关键字的值匹配的帮助文件也是如此。

当脚本模块导出函数时，的值 `.EXTERNALHELP` 应为不带路径的文件名。 `Get-Help`在模块目录的特定于区域设置的子目录中查找文件。 文件名没有任何要求，但最佳做法是使用以下文件名格式： `<ScriptModule>.psm1-help.xml` 。

如果函数不与模块相关联，请在关键字的值中包含路径和文件名 `.EXTERNALHELP` 。 如果 XML 文件的指定路径包含特定于 UI 区域性的子目录，则 `Get-Help` 会以递归方式搜索包含脚本或函数名称的 xml 文件的子目录，就像为 Windows 建立的语言回退标准一样。

有关 cmdlet 帮助基于 XML 的帮助文件格式的详细信息，请参阅[编写 Windows PowerShell Cmdlet 帮助](./writing-help-for-windows-powershell-cmdlets.md)。
