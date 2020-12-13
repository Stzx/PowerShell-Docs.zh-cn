---
ms.date: 09/12/2016
ms.topic: reference
title: GetProc03 (VB.NET) 示例代码
description: GetProc03 (VB.NET) 示例代码
ms.openlocfilehash: fc70496178c85e101b380e68aacd64c8d1f350e9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355555"
---
# <a name="getproc03-vbnet-sample-code"></a><span data-ttu-id="77c4f-103">GetProc03 (VB.NET) 示例代码</span><span class="sxs-lookup"><span data-stu-id="77c4f-103">GetProc03 (VB.NET) Sample Code</span></span>

<span data-ttu-id="77c4f-104">下面的代码演示了 `Get-Process` 可以接受流水线输入的 cmdlet 的实现。</span><span class="sxs-lookup"><span data-stu-id="77c4f-104">The following code shows the implementation of a `Get-Process` cmdlet that can accept pipelined input.</span></span> <span data-ttu-id="77c4f-105">此实现定义了一个 `Name` 参数，该参数接受管道输入，并根据提供的名称从本地计算机检索进程信息，然后使用 [WriteObject (system.object) ](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) 方法作为将对象发送到管道的输出机制。</span><span class="sxs-lookup"><span data-stu-id="77c4f-105">This implementation defines a `Name` parameter that accepts pipeline input, retrieves process information from the local computer based on the supplied names, and then uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending objects to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="77c4f-106">代码示例</span><span class="sxs-lookup"><span data-stu-id="77c4f-106">Code Sample</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc03#getproc03vbAll](Msh_samplesgetproc03#getproc03vbAll)]  -->
