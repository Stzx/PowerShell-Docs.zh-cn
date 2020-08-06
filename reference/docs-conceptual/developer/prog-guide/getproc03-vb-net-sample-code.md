---
title: GetProc03 (VB.NET) 示例代码 |Microsoft Docs
ms.date: 09/12/2016
ms.openlocfilehash: ad8a7b13d30b77acdaa2f5365b9b2da02aaeedce
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87771917"
---
# <a name="getproc03-vbnet-sample-code"></a><span data-ttu-id="3827b-102">GetProc03 (VB.NET) 示例代码</span><span class="sxs-lookup"><span data-stu-id="3827b-102">GetProc03 (VB.NET) Sample Code</span></span>

<span data-ttu-id="3827b-103">下面的代码演示了 `Get-Process` 可以接受流水线输入的 cmdlet 的实现。</span><span class="sxs-lookup"><span data-stu-id="3827b-103">The following code shows the implementation of a `Get-Process` cmdlet that can accept pipelined input.</span></span> <span data-ttu-id="3827b-104">此实现定义了一个 `Name` 参数，该参数接受管道输入，并根据提供的名称从本地计算机检索进程信息，然后使用[WriteObject (system.object) ](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_)方法作为将对象发送到管道的输出机制。</span><span class="sxs-lookup"><span data-stu-id="3827b-104">This implementation defines a `Name` parameter that accepts pipeline input, retrieves process information from the local computer based on the supplied names, and then uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending objects to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="3827b-105">代码示例</span><span class="sxs-lookup"><span data-stu-id="3827b-105">Code Sample</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc03#getproc03vbAll](Msh_samplesgetproc03#getproc03vbAll)]  -->
