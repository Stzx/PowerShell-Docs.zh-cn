---
title: 如何编写 PowerShell 二进制模块 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 92395bd6b8be1bd3741888eb3716d62f0253e213
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779261"
---
# <a name="how-to-write-a-powershell-binary-module"></a>如何编写 PowerShell 二进制模块

二进制模块可以是包含 cmdlet 类的任何程序集 () 。 默认情况下，导入二进制模块时，会导入程序集中的所有 cmdlet。 但是，可以通过创建模块清单（其根模块是程序集）来限制导入的 cmdlet。  (例如，清单的 CmdletsToExport 键只能用于导出所需的 cmdlet ) 。此外，二进制模块还可以包含其他文件、目录结构以及单个 cmdlet 不能使用的其他有用的管理信息。

下面的过程介绍如何创建和安装 PowerShell 二进制模块。

#### <a name="how-to-create-and-install-a-powershell-binary-module"></a>如何创建和安装 PowerShell 二进制模块

1. 创建二进制 PowerShell 解决方案 (如使用 c # 编写的 cmdlet ) ，并提供所需的功能，并确保其正常运行。

   从代码的角度来看，二进制模块的核心只是一个 cmdlet 程序集。 事实上，在加载和卸载的过程中，PowerShell 会将单个 cmdlet 程序集视为模块，而不会对开发人员的其他工作进行额外的工作。 有关编写 cmdlet 的详细信息，请参阅[编写 Windows PowerShell cmdlet](../cmdlet/writing-a-windows-powershell-cmdlet.md)。

2. 如有必要，请创建解决方案的其余部分： (其他 cmdlet、XML 文件等) 并使用模块清单对它们进行说明。

   除了描述解决方案中的 cmdlet 程序集外，模块清单还可以描述你希望如何导出和导入模块、将公开哪些 cmdlet 以及哪些其他文件将进入模块。
   如前文所述，PowerShell 可以将二进制 cmdlet （如模块）视为不需要额外的工作。
   因此，模块清单主要用于将多个文件合并到一个包中，或用于显式控制给定程序集的发布。
   有关详细信息，请参阅[如何编写 PowerShell 模块清单](how-to-write-a-powershell-module-manifest.md)。

   下面的代码是一个非常简单的 c # 代码块，其中包含可用作模块的同一文件中的三个 cmdlet。

   ```csharp
   using System.Management.Automation;           // Windows PowerShell namespace.

   namespace ModuleCmdlets
   {
     [Cmdlet(VerbsDiagnostic.Test,"BinaryModuleCmdlet1")]
     public class TestBinaryModuleCmdlet1Command : Cmdlet
     {
       protected override void BeginProcessing()
       {
         WriteObject("BinaryModuleCmdlet1 exported by the ModuleCmdlets module.");
       }
     }

     [Cmdlet(VerbsDiagnostic.Test, "BinaryModuleCmdlet2")]
     public class TestBinaryModuleCmdlet2Command : Cmdlet
     {
         protected override void BeginProcessing()
         {
             WriteObject("BinaryModuleCmdlet2 exported by the ModuleCmdlets module.");
         }
     }

     [Cmdlet(VerbsDiagnostic.Test, "BinaryModuleCmdlet3")]
     public class TestBinaryModuleCmdlet3Command : Cmdlet
     {
         protected override void BeginProcessing()
         {
             WriteObject("BinaryModuleCmdlet3 exported by the ModuleCmdlets module.");
         }
     }

   }
   ```

3. 打包解决方案，并将包保存到 PowerShell 模块路径中的某个位置。

   `PSModulePath`全局环境变量描述 PowerShell 将用于查找模块的默认路径。 例如，在系统上保存模块的公用路径为 `%SystemRoot%\users\<user>\Documents\WindowsPowerShell\Modules\<moduleName>` 。 如果未使用默认路径，则需要在安装过程中显式声明模块的位置。 请确保创建一个文件夹以将模块保存在中，因为您可能需要使用文件夹存储解决方案的多个程序集和文件。

   请注意，从技术上讲，不需要在上的任何位置安装模块，它们 `PSModulePath` 只是 PowerShell 将在模块中查找的默认位置。 但是，除非您有充分的理由将模块存储在其他位置，否则这会被视为最佳做法。 有关详细信息，请参阅[安装 Powershell 模块](./installing-a-powershell-module.md)和[修改 Powershell 模块安装路径](./modifying-the-psmodulepath-installation-path.md)。

4. 通过调用[import-module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)将模块导入 PowerShell。

   调用[import-module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)会将模块加载到活动内存。 如果你使用的是 PowerShell 3.0 和更高版本，只需在代码中调用模块的名称，就会将其导入。有关详细信息，请参阅[导入 PowerShell 模块](./importing-a-powershell-module.md)。

## <a name="importing-snap-in-assemblies-as-modules"></a>导入管理单元程序集作为模块

管理单元程序集中存在的 cmdlet 和提供程序可以作为二进制模块加载。 当管理单元程序集作为二进制模块加载时，管理单元中的 cmdlet 和提供程序可供用户使用，但程序集中的管理单元类将被忽略，并且不会注册管理单元。 因此，即使 cmdlet 和提供程序可用于该会话，Windows PowerShell 提供的管理单元 cmdlet 仍无法检测该管理单元。

此外，管理单元引用的任何格式或类型文件都不能作为二进制模块的一部分导入。
若要导入格式和类型文件，必须创建模块清单。
请参阅[如何编写 PowerShell 模块清单](how-to-write-a-powershell-module-manifest.md)。

## <a name="see-also"></a>另请参阅

[编写 Windows PowerShell 模块](./writing-a-windows-powershell-module.md)
