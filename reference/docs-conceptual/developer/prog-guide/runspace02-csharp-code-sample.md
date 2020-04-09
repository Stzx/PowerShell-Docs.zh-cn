---
title: Runspace02 （C#）代码示例 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59a7b8b9-f72e-43fd-9a10-77404441a3f2
caps.latest.revision: 6
ms.openlocfilehash: 047d14d70853399bc262ac3f1541da38184c3ff8
ms.sourcegitcommit: 7f2479edd329dfdc55726afff7019d45e45f9156
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2020
ms.locfileid: "80977873"
---
# <a name="runspace02-c-code-sample"></a><span data-ttu-id="0ee0a-102">Runspace02 (C#) 代码示例</span><span class="sxs-lookup"><span data-stu-id="0ee0a-102">Runspace02 (C#) Code Sample</span></span>

<span data-ttu-id="0ee0a-103">下面是 Runspace02 C#示例的源代码。</span><span class="sxs-lookup"><span data-stu-id="0ee0a-103">Here is the C# source code for the Runspace02 sample.</span></span> <span data-ttu-id="0ee0a-104">此示例使用[Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke)类来同步执行 `Get-Process` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0ee0a-104">This sample uses the [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) class to execute the `Get-Process` cmdlet synchronously.</span></span> <span data-ttu-id="0ee0a-105">然后，使用 Windows 窗体和数据绑定在 DataGridView 控件中显示结果</span><span class="sxs-lookup"><span data-stu-id="0ee0a-105">Windows Forms and data binding are then used to display the results in a DataGridView control</span></span>

## <a name="code-sample"></a><span data-ttu-id="0ee0a-106">代码示例</span><span class="sxs-lookup"><span data-stu-id="0ee0a-106">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace02/Runspace02.cs" range="11-82":::

## <a name="see-also"></a><span data-ttu-id="0ee0a-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0ee0a-107">See Also</span></span>

[<span data-ttu-id="0ee0a-108">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="0ee0a-108">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
