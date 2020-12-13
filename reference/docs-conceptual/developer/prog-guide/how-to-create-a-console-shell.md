---
ms.date: 09/13/2016
ms.topic: reference
title: 如何创建控制台 Shell
description: 如何创建控制台 Shell
ms.openlocfilehash: 9ea67c43b1ee35b1fbfc553b22a1423419317ca2
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657227"
---
# <a name="how-to-create-a-console-shell"></a>如何创建控制台 Shell

Windows PowerShell 提供了一个 Make-Shell 工具（也称为 "生成套件"），用于创建不可扩展的控制台 shell。 以后使用此新工具创建的 shell 无法通过 Windows PowerShell 管理单元进行扩展。

## <a name="syntax"></a>语法

下面是用于从文件中运行 Make-Shell 的语法。

```
make-shell
  -out n.exe
  -namespace ns
  [ -lib libdirectory1[,libdirectory2,..] ]
  [ -reference ca1.dll[,ca2.dll,...] ]
  [ -formatdata fd1.format.ps1xml[,fd2.format.ps1xml,...] ]
  [ -typedata td1.type.ps1xml[,td2.type.ps1xml,...] ]
  [ -source c1.cs [,c2.cs,...] ]
  [ -authorizationmanager authorizationManagerType ]
  [ -win32icon i.ico ]
  [ -initscript p.ps1 ]
  [ -builtinscript s1.ps1[,s2.ps1,...] ]
  [ -resource resourcefile.txt ]
  [ -cscflags cscFlags ]
  [ -? | -help ]
```

## <a name="parameters"></a>parameters

下面是有关 Make Shell 的参数的简短说明。

> [!CAUTION]
> Make Shell 不支持程序集的 UNC 路径。

|参数|描述|
|---------------|-----------------|
|-out n.exe|必需。 要生成的 shell 的名称。 该路径指定为此参数的一部分。<br /><br /> 如果未指定此值，则会将 ".exe" 追加到此值。 **警告：**  不要使用与所引用 .dll 文件相同的名称来创建输出文件。 如果尝试这样做，Make-Shell 工具会创建一个具有相同名称的 .cs 文件，该文件将覆盖包含 cmdlet 源代码的 .cs 文件。|
|-命名空间 ns|必需。 生成和编译生成和编译的派生的 [Runspaceconfiguration](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConfiguration) 类所使用的命名空间。|
|-lib libdirectory1 [，libdirectory2,..]|搜索 .NET 程序集的目录，包括 Windows PowerShell 程序集、参数指定的程序集 `reference` 、其他程序集间接引用的程序集以及 .net 系统程序集。|
|-引用 ca1.dll [，ca2.dll,...]|要包括在 shell 中的程序集的逗号分隔列表。 这些程序集包括所有 cmdlet 和提供程序程序集，以及应加载的资源程序集。 如果未指定此参数，则会生成一个 shell，其中只包含 Windows PowerShell 提供的核心 cmdlet 和提供程序。<br /><br /> 可以使用其完整路径指定程序集，否则将使用参数指定的路径搜索这些程序集 `lib` 。|
|-update-formatdata fd1.format.ps1xml [，fd2.format.ps1xml,...]|要包含在 shell 中的格式数据的逗号分隔列表。 如果未指定此参数，则会生成一个 shell，其中只包含 Windows PowerShell 提供的格式数据。|
|-update-typedata td1.type.ps1xml [，td2.type.ps1xml,...]|要包含在 shell 中的类型数据的逗号分隔列表。 如果未指定此参数，则会生成一个 shell，其中只包含 Windows PowerShell 提供的类型数据。|
|-source c1.cs [，c2.cs,...]|Shell 开发人员提供的文件的名称，其中包含生成 shell 所需的任何源代码。<br /><br /> 源代码文件可以包含以下任何源代码：<br /><br /> -替代默认授权管理器的授权管理器实现。  (还可以将其提供编译到程序集中。 ) <br />-Assembly 信息性特性声明：例如，System.reflection.assemblycompanyattribute>、AssemblyCopyrightAttribute、AssemblyFileVersionAttribute、System.reflection.assemblyinformationalversionattribute>、System.reflection.assemblyproductattribute> 和 System.reflection.assemblytrademarkattribute>。|
|-authorizationmanager authorizationManagerType|包含授权管理器实现的类型。 这可以在源代码中定义，也可以编译到 (参数) 指定的程序集中 `reference` 。 如果未指定此参数，则使用默认的安全管理器。 该值应该是完整的类型名称，包括命名空间。|
|-win32icon|Shell 的 .exe 文件的图标。 如果未指定，则 shell 将具有 c # 编译器包含的图标，如果有任何)  (。|
|-initscript p.ps1|Shell 的启动配置文件。 文件 "按原样" 提供;不会通过 Make Shell 完成有效性检查。|
|-builtinscript s1.ps1 [，s2.ps1,...]|Shell 的内置脚本的列表。 在路径中的脚本之前会发现这些脚本，生成 shell 后，不能更改其内容。<br /><br /> 文件 "按原样" 提供;不会通过 Make Shell 完成有效性检查。|
|-resource resourcefile.txt|包含 shell 帮助和横幅资源的 .txt 文件。 第一个资源的名称为 ShellHelp，包含在用参数调用 shell 时显示的文本 `help` 。 第二个资源命名为 ShellBanner，它包含在交互模式下启动 shell 时显示的文本和版权信息。<br /><br /> 如果未提供此参数或这些资源不存在，则使用通用帮助和横幅。|
|-cscflags cscFlags|应传递给 c # 编译器 ( # A0) 的标志。 这些是通过未更改的传递的。 如果此参数包含空格，则应将其括在双引号中。|
|-?<br /><br /> -help|显示版权消息和 Make-Shell 命令行选项。|
|-verbose|在创建 shell 时显示详细信息。|

## <a name="see-also"></a>另请参阅

[Windows PowerShell 程序员指南](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
