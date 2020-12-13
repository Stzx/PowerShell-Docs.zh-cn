---
ms.date: 09/13/2016
ms.topic: reference
title: Runspace02 (C#) 代码示例
description: Runspace02 (C#) 代码示例
ms.openlocfilehash: 9e2c0cf37d1bf12a92f4fbf781928c0241202915
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647448"
---
# <a name="runspace02-c-code-sample"></a>Runspace02 (C#) 代码示例

下面是 Runspace02 示例的 c # 源代码。 此示例使用 [Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) 类来 `Get-Process` 同步执行 cmdlet。 然后，使用 Windows 窗体和数据绑定在 DataGridView 控件中显示结果

## <a name="code-sample"></a>代码示例

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace02/Runspace02.cs" range="11-82":::

## <a name="see-also"></a>另请参阅

[Windows PowerShell SDK](../windows-powershell-reference.md)
