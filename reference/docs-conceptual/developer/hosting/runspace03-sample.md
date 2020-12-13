---
ms.date: 09/13/2016
ms.topic: reference
title: Runspace03 示例
description: Runspace03 示例
ms.openlocfilehash: fff699bf0545bb1419aa45b8c46bbd9c2cf0a99e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657854"
---
# <a name="runspace03-sample"></a><span data-ttu-id="ef38d-103">Runspace03 示例</span><span class="sxs-lookup"><span data-stu-id="ef38d-103">Runspace03 Sample</span></span>

<span data-ttu-id="ef38d-104">此示例演示如何使用 [system.web](/dotnet/api/system.management.automation.powershell) 类来同步运行脚本，以及如何处理非终止错误的操作。</span><span class="sxs-lookup"><span data-stu-id="ef38d-104">This sample shows how to use the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) class to run a script synchronously, and how to handle non-terminating errors.</span></span> <span data-ttu-id="ef38d-105">该脚本可接收一系列进程名称，然后检索这些进程。</span><span class="sxs-lookup"><span data-stu-id="ef38d-105">The script receives a list of process names and then retrieves those processes.</span></span> <span data-ttu-id="ef38d-106">脚本的结果（包括运行脚本时生成的非终止错误）显示在控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="ef38d-106">The results of the script, including any non-terminating errors that were generated when running the script, are displayed in a console window.</span></span>

## <a name="requirements"></a><span data-ttu-id="ef38d-107">要求</span><span class="sxs-lookup"><span data-stu-id="ef38d-107">Requirements</span></span>

<span data-ttu-id="ef38d-108">此示例需要 Windows PowerShell 2.0。</span><span class="sxs-lookup"><span data-stu-id="ef38d-108">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="ef38d-109">演示</span><span class="sxs-lookup"><span data-stu-id="ef38d-109">Demonstrates</span></span>

<span data-ttu-id="ef38d-110">此示例演示以下各项。</span><span class="sxs-lookup"><span data-stu-id="ef38d-110">This sample demonstrates the following.</span></span>

- <span data-ttu-id="ef38d-111">创建用于运行脚本的 [system.object](/dotnet/api/system.management.automation.powershell) 对象。</span><span class="sxs-lookup"><span data-stu-id="ef38d-111">Creating a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object to run a script.</span></span>

- <span data-ttu-id="ef38d-112">将脚本添加到 [system.web](/dotnet/api/system.management.automation.powershell) 对象的管道。</span><span class="sxs-lookup"><span data-stu-id="ef38d-112">Adding a script to the pipeline of the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="ef38d-113">通过调用程序将输入对象传递给脚本。</span><span class="sxs-lookup"><span data-stu-id="ef38d-113">Passing input objects to the script from the calling program.</span></span>

- <span data-ttu-id="ef38d-114">同步运行脚本。</span><span class="sxs-lookup"><span data-stu-id="ef38d-114">Running the script synchronously.</span></span>

- <span data-ttu-id="ef38d-115">使用 [system.exception](/dotnet/api/System.Management.Automation.PSObject) 对象从脚本返回的对象中提取并显示属性。</span><span class="sxs-lookup"><span data-stu-id="ef38d-115">Using [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects to extract and display properties from the objects returned by the script.</span></span>

- <span data-ttu-id="ef38d-116">检索和显示在运行脚本时生成的错误记录。</span><span class="sxs-lookup"><span data-stu-id="ef38d-116">Retrieving and displaying error records that were generated when the script was run.</span></span>

## <a name="example"></a><span data-ttu-id="ef38d-117">示例</span><span class="sxs-lookup"><span data-stu-id="ef38d-117">Example</span></span>

<span data-ttu-id="ef38d-118">此示例在 Windows PowerShell 提供的默认运行空间中以同步方式运行脚本。</span><span class="sxs-lookup"><span data-stu-id="ef38d-118">This sample runs a script synchronously in the default runspace provided by Windows PowerShell.</span></span> <span data-ttu-id="ef38d-119">脚本的输出和生成的任何非终止错误都将显示在控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="ef38d-119">The output of the script and any non-terminating errors that were generated are displayed in a console window.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Collections;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace03
  {
    /// <summary>
    /// This sample shows how to use the PowerShell class to run a
    /// script that retrieves process information for the list of
    /// process names passed to the script. It shows how to pass input
    /// objects to a script and how to retrieve error objects as well
    /// as the output objects.
    /// </summary>
    /// <param name="args">Parameter not used.</param>
    /// <remarks>
    /// This sample demonstrates the following:
    /// 1. Creating a PowerSHell object to run a script.
    /// 2. Adding a script to the pipeline of the PowerShell object.
    /// 3. Passing input objects to the script from the calling program.
    /// 4. Running the script synchronously.
    /// 5. Using PSObject objects to extract and display properties from
    ///    the objects returned by the script.
    /// 6. Retrieving and displaying error records that were generated
    ///    when the script was run.
    /// </remarks>
    private static void Main(string[] args)
    {
      // Define a list of processes to look for.
      string[] processNames = new string[]
      {
        "lsass", "nosuchprocess", "services", "nosuchprocess2"
      };

      // The script to run to get these processes. Input passed
      // to the script will be available in the $input variable.
      string script = "$input | get-process -name {$_}";

      // Create a PowerShell object. Creating this object takes care of
      // building all of the other data structures needed to run the script.
      using (PowerShell powershell = PowerShell.Create())
      {
        powershell.AddScript(script);

        Console.WriteLine("Process              HandleCount");
        Console.WriteLine("--------------------------------");

        // Invoke the script synchronously and display the
        // ProcessName and HandleCount properties of the
        // objects that are returned.
        foreach (PSObject result in powershell.Invoke(processNames))
        {
          Console.WriteLine(
                            "{0,-20} {1}",
                            result.Members["ProcessName"].Value,
                            result.Members["HandleCount"].Value);
        }

        // Process any error records that were generated while running
        //  the script.
        Console.WriteLine("\nThe following non-terminating errors occurred:\n");
        PSDataCollection<ErrorRecord> errors = powershell.Streams.Error;
        if (errors != null && errors.Count > 0)
        {
          foreach (ErrorRecord err in errors)
          {
            System.Console.WriteLine("    error: {0}", err.ToString());
          }
        }
      }

      System.Console.WriteLine("\nHit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="ef38d-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ef38d-120">See Also</span></span>

[<span data-ttu-id="ef38d-121">编写 Windows PowerShell 主机应用程序</span><span class="sxs-lookup"><span data-stu-id="ef38d-121">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)
