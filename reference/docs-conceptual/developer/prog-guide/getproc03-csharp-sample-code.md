---
ms.date: 09/13/2016
ms.topic: reference
title: GetProc03 (C#) 示例代码
description: GetProc03 (C#) 示例代码
ms.openlocfilehash: c81ba04b2b335f4ce992c6b3ed2f019cf6d7d20f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355572"
---
# <a name="getproc03-c-sample-code"></a>GetProc03 (C#) 示例代码

下面的代码演示了 `Get-Process` 可以接受流水线输入的 cmdlet 的实现。 此实现定义了一个 `Name` 参数，该参数接受管道输入，并根据提供的名称从本地计算机检索进程信息，然后使用 [WriteObject (system.object) ](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) 方法作为将对象发送到管道的输出机制。

> [!NOTE]
> 你可以使用适用于 Windows Vista 的 Microsoft Windows 软件开发工具包和 .NET Framework 3.0 运行时组件，为此 Get-Proc cmdlet 下载 c # 源文件 (getprov03.cs) 。 有关下载说明，请参阅 [如何安装 Windows powershell 和下载 Windows POWERSHELL SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk)。
> 下载的源文件在目录中提供 **\<PowerShell Samples>** 。

## <a name="code-sample"></a>代码示例

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample03/GetProcessSample03.cs" range="11-78":::

## <a name="see-also"></a>另请参阅

[Windows PowerShell 程序员指南](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
