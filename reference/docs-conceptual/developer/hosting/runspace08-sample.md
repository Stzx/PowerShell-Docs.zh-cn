---
ms.date: 09/13/2016
ms.topic: reference
title: Runspace08 示例
description: Runspace08 示例
ms.openlocfilehash: ce60e85919a78143f26ff695a9c9104c86cd4f6a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657641"
---
# <a name="runspace08-sample"></a><span data-ttu-id="44e7b-103">Runspace08 示例</span><span class="sxs-lookup"><span data-stu-id="44e7b-103">Runspace08 Sample</span></span>

<span data-ttu-id="44e7b-104">此示例演示如何将命令和参数添加到 [system.web](/dotnet/api/system.management.automation.powershell) 对象的管道，以及如何以同步方式运行命令。</span><span class="sxs-lookup"><span data-stu-id="44e7b-104">This sample shows how to add commands and arguments to the pipeline of a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object and how to run the commands synchronously.</span></span>

## <a name="requirements"></a><span data-ttu-id="44e7b-105">要求</span><span class="sxs-lookup"><span data-stu-id="44e7b-105">Requirements</span></span>

<span data-ttu-id="44e7b-106">此示例需要 Windows PowerShell 2.0。</span><span class="sxs-lookup"><span data-stu-id="44e7b-106">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="44e7b-107">演示</span><span class="sxs-lookup"><span data-stu-id="44e7b-107">Demonstrates</span></span>

<span data-ttu-id="44e7b-108">此示例演示以下各项。</span><span class="sxs-lookup"><span data-stu-id="44e7b-108">This sample demonstrates the following.</span></span>

- <span data-ttu-id="44e7b-109">使用[Runspacefactory](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory)类创建一个 system.web. e x.///[运行空间](/dotnet/api/System.Management.Automation.Runspaces.Runspace)对象。</span><span class="sxs-lookup"><span data-stu-id="44e7b-109">Creating a [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) object by using the [System.Management.Automation.Runspaces.Runspacefactory](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory) class.</span></span>

- <span data-ttu-id="44e7b-110">创建使用运行空间的 [system.web](/dotnet/api/system.management.automation.powershell) 对象。</span><span class="sxs-lookup"><span data-stu-id="44e7b-110">Creating a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object that uses the runspace.</span></span>

- <span data-ttu-id="44e7b-111">将 cmdlet 添加到 [system.web](/dotnet/api/system.management.automation.powershell) 对象的管道。</span><span class="sxs-lookup"><span data-stu-id="44e7b-111">Adding cmdlets to the pipeline of the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="44e7b-112">同步运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="44e7b-112">Running the cmdlets synchronously.</span></span>

- <span data-ttu-id="44e7b-113">从命令返回的 [system.object](/dotnet/api/System.Management.Automation.PSObject) 对象中提取属性。</span><span class="sxs-lookup"><span data-stu-id="44e7b-113">Extracting properties from the [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects returned by the command.</span></span>

## <a name="example"></a><span data-ttu-id="44e7b-114">示例</span><span class="sxs-lookup"><span data-stu-id="44e7b-114">Example</span></span>

<span data-ttu-id="44e7b-115">此示例使用一个[system.web](/dotnet/api/system.management.automation.powershell)对象运行[获取进程](/powershell/module/Microsoft.PowerShell.Management/Get-Process)和[排序对象](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object)的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="44e7b-115">This sample runs the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) and [Sort-Object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) cmdlets by using a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Collections.Generic;
  using System.Collections.ObjectModel;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace08
  {
    /// <summary>
    /// This sample shows how to use a PowerShell object to run commands. The
    /// PowerShell object builds a pipeline that include the get-process cmdlet,
    /// which is then piped to the sort-object cmdlet. Parameters are added to the
    /// sort-object cmdlet to sort the HandleCount property in descending order.
    /// </summary>
    /// <param name="args">Parameter is not used.</param>
    /// <remarks>
    /// This sample demonstrates:
    /// 1. Creating a PowerShell object
    /// 2. Adding individual commands to the PowerShell object.
    /// 3. Adding parameters to the commands.
    /// 4. Running the pipeline of the PowerShell object synchronously.
    /// 5. Working with PSObject objects to extract properties
    ///    from the objects returned by the commands.
    /// </remarks>
    private static void Main(string[] args)
    {
      Collection<PSObject> results; // Holds the result of the pipeline execution.

      // Create the PowerShell object. Notice that no runspace is specified so a
      // new default runspace is used.
      PowerShell powershell = PowerShell.Create();

      // Use the using statement so that we can dispose of the PowerShell object
      // when we are done.
      using (powershell)
      {
        // Add the get-process cmdlet to the pipeline of the PowerShell object.
        powershell.AddCommand("get-process");

        // Add the sort-object cmdlet and its parameters to the pipeline of
        // the PowerShell object so that we can sort the HandleCount property
        //  in descending order.
        powershell.AddCommand("sort-object").AddParameter("descending").AddParameter("property", "handlecount");

        // Run the commands of the pipeline synchronously.
        results = powershell.Invoke();
      }

      // Even after disposing of the PowerShell object, we still
      // need to set the powershell variable to null so that the
      // garbage collector can clean it up.
      powershell = null;

      Console.WriteLine("Process              HandleCount");
      Console.WriteLine("--------------------------------");

      // Display the results returned by the commands.
      foreach (PSObject result in results)
      {
        Console.WriteLine(
                          "{0,-20} {1}",
                          result.Members["ProcessName"].Value,
                          result.Members["HandleCount"].Value);
      }

      System.Console.WriteLine("Hit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="44e7b-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="44e7b-116">See Also</span></span>

[<span data-ttu-id="44e7b-117">编写 Windows PowerShell 主机应用程序</span><span class="sxs-lookup"><span data-stu-id="44e7b-117">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)
