---
ms.date: 09/13/2016
ms.topic: reference
title: Runspace01 (VB.NET) 代码示例
description: Runspace01 (VB.NET) 代码示例
ms.openlocfilehash: 69211662c166c40e6e99e287083f7bd53f9f536f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653850"
---
# <a name="runspace01-vbnet-code-sample"></a><span data-ttu-id="8ccf0-103">Runspace01 (VB.NET) 代码示例</span><span class="sxs-lookup"><span data-stu-id="8ccf0-103">Runspace01 (VB.NET) Code Sample</span></span>

<span data-ttu-id="8ccf0-104">下面是 [创建运行指定命令的控制台应用程序](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program)中所述的运行空间的代码示例。</span><span class="sxs-lookup"><span data-stu-id="8ccf0-104">Here are the code samples for the runspace described in [Creating a Console Application That Runs a Specified Command](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program).</span></span> <span data-ttu-id="8ccf0-105">为此，应用程序将调用运行空间，然后调用命令。</span><span class="sxs-lookup"><span data-stu-id="8ccf0-105">To do this, the application invokes a runspace, and then invokes a command.</span></span> <span data-ttu-id="8ccf0-106"> (请注意，此应用程序不指定运行空间的配置信息，也不会显式创建管道。 ) 调用的命令是 `Get-Process` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8ccf0-106">(Note that this application does not specify runspace configuration information, nor does it explicitly create a pipeline.) The command that is invoked is the `Get-Process` cmdlet.</span></span>

## <a name="code-sample"></a><span data-ttu-id="8ccf0-107">代码示例</span><span class="sxs-lookup"><span data-stu-id="8ccf0-107">Code Sample</span></span>

```vb
Imports System
Imports System.Collections.Generic
Imports System.Text
Imports System.Management.Automation
Imports System.Management.Automation.Host
Imports System.Management.Automation.Runspaces

Namespace Microsoft.Samples.PowerShell.Runspaces

    Module Runspace01
        ' <summary>
        ' This sample uses the RunspaceInvoke class to execute
        ' the get-process cmdlet synchronously. The name and
        ' handlecount are then extracted from  the PSObjects
        ' returned and displayed.
        ' </summary>
        ' <param name="args">Unused</param>
        ' <remarks>
        ' This sample demonstrates the following:
        ' 1. Creating an instance of the RunspaceInvoke class.
        ' 2. Using this instance to invoke a PowerShell command.
        ' 3. Using PSObject to extract properties from the objects
        '    returned by this command.
        ' </remarks>
        Sub Main()
            ' Create an instance of the RunspaceInvoke class.
            ' This takes care of all building all of the other
            ' data structures needed...
            Dim invoker As RunspaceInvoke = New RunspaceInvoke()

            Console.WriteLine("Process              HandleCount")
            Console.WriteLine("--------------------------------")

            ' Now invoke the runspace and display the objects that are
            ' returned...
            For Each result As PSObject In invoker.Invoke("get-process")
                Console.WriteLine("{0,-20} {1}", _
                    result.Members("ProcessName").Value, _
                    result.Members("HandleCount").Value)
            Next
            System.Console.WriteLine("Hit any key to exit...")
            System.Console.ReadKey()
        End Sub
    End Module
End Namespace
```

<!-- TODO!!!: [!code-csharp[Runspace01.vb](../../powershell-sdk-samples/SDK-2.0/vb/Runspace01/Runspace01.vb#L09-L53 "Runspace01.vb")] -->

## <a name="see-also"></a><span data-ttu-id="8ccf0-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8ccf0-108">See Also</span></span>

[<span data-ttu-id="8ccf0-109">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="8ccf0-109">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
