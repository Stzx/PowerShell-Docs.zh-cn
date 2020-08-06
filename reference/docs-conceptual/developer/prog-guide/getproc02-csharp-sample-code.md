---
title: 'GetProc02 (c # ) 示例代码 |Microsoft Docs'
ms.date: 09/13/2016
ms.openlocfilehash: d9afa8fff23d99661987c067e8082a9294c12717
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787149"
---
# <a name="getproc02-c-sample-code"></a><span data-ttu-id="30895-102">GetProc02 (C#) 示例代码</span><span class="sxs-lookup"><span data-stu-id="30895-102">GetProc02 (C#) Sample Code</span></span>

<span data-ttu-id="30895-103">下面的代码演示了 `Get-Process` 接受命令行输入的 cmdlet 的实现。</span><span class="sxs-lookup"><span data-stu-id="30895-103">The following code shows the implementation of a `Get-Process` cmdlet that accepts command-line input.</span></span> <span data-ttu-id="30895-104">请注意，此实现定义了一个 `Name` 允许命令行输入的参数，并使用[WriteObject (system.object) ](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_)方法作为将输出对象发送到管道的输出机制。</span><span class="sxs-lookup"><span data-stu-id="30895-104">Notice that this implementation defines a `Name` parameter to allow command-line input, and it uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending output objects to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="30895-105">代码示例</span><span class="sxs-lookup"><span data-stu-id="30895-105">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample02/GetProcessSample02.cs" range="11-76":::

## <a name="see-also"></a><span data-ttu-id="30895-106">另请参阅</span><span class="sxs-lookup"><span data-stu-id="30895-106">See Also</span></span>

[<span data-ttu-id="30895-107">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="30895-107">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
