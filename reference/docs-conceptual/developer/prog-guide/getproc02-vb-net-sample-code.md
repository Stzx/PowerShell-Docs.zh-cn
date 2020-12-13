---
ms.date: 09/13/2016
ms.topic: reference
title: GetProc02 (VB.NET) 示例代码
description: GetProc02 (VB.NET) 示例代码
ms.openlocfilehash: aefc3a4df5e0f29120916648ecdca41931a4c1c6
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "93354535"
---
# <a name="getproc02-vbnet-sample-code"></a><span data-ttu-id="cf9f0-103">GetProc02 (VB.NET) 示例代码</span><span class="sxs-lookup"><span data-stu-id="cf9f0-103">GetProc02 (VB.NET) Sample Code</span></span>

<span data-ttu-id="cf9f0-104">下面的代码演示了 `Get-Process` 接受命令行输入的 cmdlet 的实现。</span><span class="sxs-lookup"><span data-stu-id="cf9f0-104">The following code shows the implementation of a `Get-Process` cmdlet that accepts command-line input.</span></span> <span data-ttu-id="cf9f0-105">请注意，此实现定义了一个 `Name` 允许命令行输入的参数，并使用 [WriteObject (system.object) ](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) 方法作为将输出对象发送到管道的输出机制。</span><span class="sxs-lookup"><span data-stu-id="cf9f0-105">Notice that this implementation defines a `Name` parameter to allow command-line input, and it uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending output objects to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="cf9f0-106">代码示例</span><span class="sxs-lookup"><span data-stu-id="cf9f0-106">Code Sample</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc02#getproc02vball](Msh_samplesgetproc02#getproc02vball)]  -->

## <a name="see-also"></a><span data-ttu-id="cf9f0-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cf9f0-107">See Also</span></span>

[<span data-ttu-id="cf9f0-108">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="cf9f0-108">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
