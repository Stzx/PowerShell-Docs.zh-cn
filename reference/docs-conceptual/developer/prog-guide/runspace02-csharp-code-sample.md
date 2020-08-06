---
title: 'Runspace02 (c # ) 代码示例 |Microsoft Docs'
ms.date: 09/13/2016
ms.openlocfilehash: 1e58f035f20baa7443d9031499062a45beae01b9
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87778444"
---
# <a name="runspace02-c-code-sample"></a>Runspace02 (C#) 代码示例

下面是 Runspace02 示例的 c # 源代码。 此示例使用[Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke)类来 `Get-Process` 同步执行 cmdlet。 然后，使用 Windows 窗体和数据绑定在 DataGridView 控件中显示结果

## <a name="code-sample"></a>代码示例

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace02/Runspace02.cs" range="11-82":::

## <a name="see-also"></a>另请参阅

[Windows PowerShell SDK](../windows-powershell-reference.md)
