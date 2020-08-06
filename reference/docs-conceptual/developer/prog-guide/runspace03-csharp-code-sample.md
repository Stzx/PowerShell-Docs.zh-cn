---
title: 'RunSpace03 (c # ) 代码示例 |Microsoft Docs'
ms.date: 09/13/2016
ms.openlocfilehash: df34652f60ed85b13739a04485cf6622cf924872
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784786"
---
# <a name="runspace03-c-code-sample"></a>RunSpace03 (C#) 代码示例

下面是 "创建运行指定脚本的控制台应用程序" 中所述的控制台应用程序的 c # 源代码。 此示例使用[Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke)类来执行一个脚本，该脚本通过使用传递到脚本的进程名称列表来检索进程信息。 它演示如何将输入对象传递给脚本，以及如何检索错误对象以及输出对象。

> [!NOTE]
> 您可以使用适用于 Windows Vista 的 Microsoft Windows 软件开发工具包和 Microsoft .NET Framework 3.0 运行时组件，下载此示例的 c # 源文件 (runspace03.cs) 。 有关下载说明，请参阅[如何安装 Windows powershell 和下载 Windows POWERSHELL SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk)。
> 下载的源文件在目录中提供 **\<PowerShell Samples>** 。

## <a name="code-sample"></a>代码示例

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace03/Runspace03.cs" range="11-88":::

## <a name="see-also"></a>另请参阅

[Windows PowerShell 程序员指南](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
