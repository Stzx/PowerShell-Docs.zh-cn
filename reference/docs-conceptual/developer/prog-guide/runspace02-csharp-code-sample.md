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
# <a name="runspace02-c-code-sample"></a><span data-ttu-id="778b4-102">Runspace02 (C#) 代码示例</span><span class="sxs-lookup"><span data-stu-id="778b4-102">Runspace02 (C#) Code Sample</span></span>

<span data-ttu-id="778b4-103">下面是 Runspace02 示例的 c # 源代码。</span><span class="sxs-lookup"><span data-stu-id="778b4-103">Here is the C# source code for the Runspace02 sample.</span></span> <span data-ttu-id="778b4-104">此示例使用[Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke)类来 `Get-Process` 同步执行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="778b4-104">This sample uses the [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) class to execute the `Get-Process` cmdlet synchronously.</span></span> <span data-ttu-id="778b4-105">然后，使用 Windows 窗体和数据绑定在 DataGridView 控件中显示结果</span><span class="sxs-lookup"><span data-stu-id="778b4-105">Windows Forms and data binding are then used to display the results in a DataGridView control</span></span>

## <a name="code-sample"></a><span data-ttu-id="778b4-106">代码示例</span><span class="sxs-lookup"><span data-stu-id="778b4-106">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace02/Runspace02.cs" range="11-82":::

## <a name="see-also"></a><span data-ttu-id="778b4-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="778b4-107">See Also</span></span>

[<span data-ttu-id="778b4-108">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="778b4-108">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
