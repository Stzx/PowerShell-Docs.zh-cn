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
# <a name="runspace02-c-code-sample"></a><span data-ttu-id="8a973-103">Runspace02 (C#) 代码示例</span><span class="sxs-lookup"><span data-stu-id="8a973-103">Runspace02 (C#) Code Sample</span></span>

<span data-ttu-id="8a973-104">下面是 Runspace02 示例的 c # 源代码。</span><span class="sxs-lookup"><span data-stu-id="8a973-104">Here is the C# source code for the Runspace02 sample.</span></span> <span data-ttu-id="8a973-105">此示例使用 [Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) 类来 `Get-Process` 同步执行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8a973-105">This sample uses the [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) class to execute the `Get-Process` cmdlet synchronously.</span></span> <span data-ttu-id="8a973-106">然后，使用 Windows 窗体和数据绑定在 DataGridView 控件中显示结果</span><span class="sxs-lookup"><span data-stu-id="8a973-106">Windows Forms and data binding are then used to display the results in a DataGridView control</span></span>

## <a name="code-sample"></a><span data-ttu-id="8a973-107">代码示例</span><span class="sxs-lookup"><span data-stu-id="8a973-107">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace02/Runspace02.cs" range="11-82":::

## <a name="see-also"></a><span data-ttu-id="8a973-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a973-108">See Also</span></span>

[<span data-ttu-id="8a973-109">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="8a973-109">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
