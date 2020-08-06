---
title: 'Runspace01 (c # ) 代码示例 |Microsoft Docs'
ms.date: 09/13/2016
ms.openlocfilehash: 418162731b4a98989642e1c61c655fdb0f002698
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787048"
---
# <a name="runspace01-c-code-sample"></a>Runspace01 (C#) 代码示例

下面是[创建运行指定命令的控制台应用程序](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program)中所述的运行空间的代码示例。
为此，应用程序将调用运行空间，然后调用命令。  (请注意，此应用程序不指定运行空间配置信息，也不会) 显式创建管道。 调用的命令是 `Get-Process` cmdlet。

> [!NOTE]
> 你可以使用适用于 Windows Vista 的 Microsoft Windows 软件开发工具包和 Microsoft .NET Framework 3.0 运行时组件，为此运行空间下载 c # 源文件 (runspace01.cs) 。
> 有关下载说明，请参阅[如何安装 Windows powershell 和下载 Windows POWERSHELL SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk)。
> 下载的源文件在目录中提供 **\<PowerShell Samples>** 。

## <a name="code-sample"></a>代码示例

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace01/Runspace01.cs" range="11-62":::

## <a name="see-also"></a>另请参阅

[Windows PowerShell 程序员指南](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
