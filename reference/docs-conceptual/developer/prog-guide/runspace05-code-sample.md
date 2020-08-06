---
title: RunSpace05 代码示例 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 31a73f965a6e38dceec740a2f7d4adead3e2a3f9
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784735"
---
# <a name="runspace05-code-sample"></a>RunSpace05 代码示例

下面是[使用 RunspaceConfiguration 配置运行空间](https://msdn.microsoft.com/42681d19-2d05-4975-befd-afb1990e79b2)中所述的 Runspace05 示例的源代码。
此示例演示如何创建运行空间配置信息、创建运行空间、使用单个命令创建管道，然后执行管道。 执行的命令是 `Get-Process` cmdlet。

> [!NOTE]
> 您可以使用适用于 Windows Vista 的 Microsoft Windows 软件开发工具包和 Microsoft .NET Framework 3.0 运行时组件 (runspace05.cs) 下载 c # 源文件。 有关下载说明，请参阅[如何安装 Windows powershell 和下载 Windows POWERSHELL SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk)。
> 下载的源文件在目录中提供 **\<PowerShell Samples>** 。

## <a name="code-sample"></a>代码示例

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace05/Runspace05.cs" range="11-86":::

## <a name="see-also"></a>另请参阅

[Windows PowerShell 程序员指南](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
