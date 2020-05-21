---
title: 基于注释的帮助关键字 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab90ec96-77f5-42e3-9c7e-2f4156ec207f
caps.latest.revision: 6
ms.openlocfilehash: 3c5736be7066a749744482cb79edad2f53705f07
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83564112"
---
# <a name="comment-based-help-keywords"></a>基于注释的帮助关键字

本主题列出并描述了基于注释的帮助中的关键字。

## <a name="keywords-in-comment-based-help"></a>基于注释的帮助中的关键字

下面是有效的基于注释的帮助关键字。 它们按其在帮助主题中通常出现的顺序列出，以及它们的预期用途。 这些关键字可以在基于注释的帮助中以任意顺序出现，它们不区分大小写。

请注意， `.ExternalHelp` 关键字优先于所有其他基于注释的帮助关键字。 当 `.ExternalHelp` 存在时， [GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) cmdlet 不显示基于注释的帮助，即使找不到与关键字的值匹配的帮助文件也是如此。

`.Synopsis`函数或脚本的简短说明。 每个主题中只能使用一次此关键字。

`.Description`函数或脚本的详细说明。 每个主题中只能使用一次此关键字。

`.Parameter`* \< 参数-名称>* 参数说明。 可以 `.Parameter` 在函数或脚本中包含每个参数的关键字。

`.Parameter`关键字可以在注释块中以任意顺序出现，但参数在语句或函数声明中的显示顺序 `Param` 决定了参数在帮助主题中的显示顺序。 若要更改帮助主题中参数的顺序，请更改 `Param` 语句或函数声明中参数的顺序。

您还可以通过将注释放在 `Param` 参数变量名称之前的语句中来指定参数说明。 如果同时使用 `Param` 语句注释和 `.Parameter` 关键字，则使用与关键字关联的说明 `.Parameter` ，并 `Param` 忽略语句注释。

`.Example`使用函数或脚本的示例命令，可选择后跟示例输出和说明。 为每个示例重复此关键字。

`.Inputs`可以通过管道传递给函数或脚本的对象的 Microsoft .NET 框架类型。 还可以包括对输入对象的描述。

`.Outputs`Cmdlet 返回的对象的 .NET Framework 类型。 还可以包括返回对象的描述。

`.Notes`有关函数或脚本的其他信息。

`.Link`相关主题的名称。 为每个相关主题重复此关键字。 此内容显示在帮助主题的 "相关链接" 部分中。

`.Link`关键字 content 还可以将统一资源标识符（URI）包含到同一个帮助主题的联机版本。 当你使用 Get-help 的参数时，将打开联机版本 `Online` 。 URI 必须以 "http" 或 "https" 开头。

`.Component`函数或脚本使用或与之相关的技术或功能。 当 Get-help 命令包含 Get-help 的参数时，将显示此内容 `Component` 。

`.Role`帮助主题的用户角色。 当 Get-help 命令包含 Get-help 的参数时，将显示此内容 `Role` 。

`.Functionality`函数的预期用途。 当 Get-help 命令包含 Get-help 的参数时，将显示此内容 `Functionality` 。

`.ForwardHelpTargetName``<Command-Name>`重定向到指定命令的帮助主题。 您可以将用户重定向到任何帮助主题，包括函数、脚本、cmdlet 或提供程序的帮助主题。

`.ForwardHelpCategory``<Category>`指定 ForwardHelpTargetName 中项的帮助类别。 有效值为 Alias、Cmdlet、提供程序、函数、提供程序、常规、FAQ、术语表、ScriptCommand、ExternalScript、筛选器或全部。 当存在具有相同名称的命令时，请使用此关键字避免冲突。

`.RemoteHelpRunspace``<PSSession-variable>`指定包含 "帮助" 主题的会话。 输入包含 PSSession 的变量。 Cmdlet 使用此关键字 `Export-PSSession` 查找导出的命令的帮助主题。

`.ExternalHelp``<XML Help File>`为脚本或函数指定基于 XML 的帮助文件的路径和/或名称。

`.ExternalHelp`关键字指示[GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) cmdlet 获取有关基于 XML 的文件中的脚本或函数的帮助。 **。** 对于脚本或函数使用基于 XML 的帮助文件时，需要使用 .externalhelp 关键字。 如果没有此 `Get-Help` 功能，将找不到该函数或脚本的帮助文件。

`.ExternalHelp`关键字优先于所有其他基于注释的帮助关键字。 当 `.ExternalHelp` 存在时， [GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) cmdlet 不显示基于注释的帮助，即使找不到与关键字的值匹配的帮助文件也是如此。

当脚本模块导出函数时，的值 `.ExternalHelp` 应为不带路径的文件名。 `Get-Help`在模块目录的特定于区域设置的子目录中查找文件。 不需要文件名，但最佳做法是使用以下文件名格式： `<ScriptModule>.psm1-help.xml` 。

如果该函数未与模块相关联，则在的值中包含路径和文件名 **。.Externalhelp**关键字。 如果 XML 文件的指定路径包含特定于 UI 区域性的子目录，则 `Get-Help` 会以递归方式搜索包含脚本或函数名称的 xml 文件的子目录，就像为 Windows 建立的语言回退标准一样。

有关 cmdlet 帮助基于 XML 的帮助文件格式的详细信息，请参阅[编写 Windows PowerShell Cmdlet 帮助](./writing-help-for-windows-powershell-cmdlets.md)。
