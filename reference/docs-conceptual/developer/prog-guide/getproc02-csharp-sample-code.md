---
ms.date: 09/13/2016
ms.topic: reference
title: GetProc02 (C#) 示例代码
description: GetProc02 (C#) 示例代码
ms.openlocfilehash: 17fd0d0c0829ed21ef955fd2e62e9ee089d62190
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355606"
---
# <a name="getproc02-c-sample-code"></a>GetProc02 (C#) 示例代码

下面的代码演示了 `Get-Process` 接受命令行输入的 cmdlet 的实现。 请注意，此实现定义了一个 `Name` 允许命令行输入的参数，并使用 [WriteObject (system.object) ](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) 方法作为将输出对象发送到管道的输出机制。

## <a name="code-sample"></a>代码示例

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample02/GetProcessSample02.cs" range="11-76":::

## <a name="see-also"></a>另请参阅

[Windows PowerShell SDK](../windows-powershell-reference.md)
