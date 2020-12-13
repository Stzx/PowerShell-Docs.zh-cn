---
ms.date: 09/13/2016
ms.topic: reference
title: Runspace01 示例
description: Runspace01 示例
ms.openlocfilehash: f47f79dd507db258119016353dc5a72d110d9252
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657922"
---
# <a name="runspace01-sample"></a><span data-ttu-id="02d0b-103">Runspace01 示例</span><span class="sxs-lookup"><span data-stu-id="02d0b-103">Runspace01 Sample</span></span>

<span data-ttu-id="02d0b-104">此示例演示如何使用 [system.exception 类以](/dotnet/api/system.management.automation.powershell) 同步方式运行 [Get Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="02d0b-104">This sample shows how to use the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) class to run the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet synchronously.</span></span> <span data-ttu-id="02d0b-105">[获取进程](/powershell/module/Microsoft.PowerShell.Management/Get-Process)cmdlet 将为在本地计算机上运行的每个进程返回[system.object](/dotnet/api/System.Diagnostics.Process) 。</span><span class="sxs-lookup"><span data-stu-id="02d0b-105">The [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet returns [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) objects for each process running on the local computer.</span></span> <span data-ttu-id="02d0b-106">然后，将从返回的对象中提取 [Processname \*](/dotnet/api/System.Diagnostics.Process.ProcessName) 和 [Handlecount \*](/dotnet/api/System.Diagnostics.Process.Handlecount) 属性的值，并将其显示在控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="02d0b-106">The values of the [System.Diagnostics.Process.Processname\*](/dotnet/api/System.Diagnostics.Process.ProcessName) and [System.Diagnostics.Process.Handlecount\*](/dotnet/api/System.Diagnostics.Process.Handlecount) properties are then extracted from the returned objects and displayed in a console window.</span></span>

## <a name="requirements"></a><span data-ttu-id="02d0b-107">要求</span><span class="sxs-lookup"><span data-stu-id="02d0b-107">Requirements</span></span>

 <span data-ttu-id="02d0b-108">此示例需要 Windows PowerShell 2.0。</span><span class="sxs-lookup"><span data-stu-id="02d0b-108">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="02d0b-109">演示</span><span class="sxs-lookup"><span data-stu-id="02d0b-109">Demonstrates</span></span>

- <span data-ttu-id="02d0b-110">创建要运行命令的 [system.web](/dotnet/api/system.management.automation.powershell) 对象。</span><span class="sxs-lookup"><span data-stu-id="02d0b-110">Creating a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object to run a command.</span></span>

- <span data-ttu-id="02d0b-111">将命令添加到 [system.web](/dotnet/api/system.management.automation.powershell) 对象的管道。</span><span class="sxs-lookup"><span data-stu-id="02d0b-111">Adding a command to the pipeline of the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="02d0b-112">同步运行命令。</span><span class="sxs-lookup"><span data-stu-id="02d0b-112">Running the command synchronously.</span></span>

- <span data-ttu-id="02d0b-113">使用 system.exception 对象从命令返回 [的对象中](/dotnet/api/System.Management.Automation.PSObject) 提取属性。</span><span class="sxs-lookup"><span data-stu-id="02d0b-113">Using [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects to extract properties from the objects returned by the command.</span></span>

## <a name="example"></a><span data-ttu-id="02d0b-114">示例</span><span class="sxs-lookup"><span data-stu-id="02d0b-114">Example</span></span>

 <span data-ttu-id="02d0b-115">此示例在 Windows PowerShell 提供的默认运行空间中以同步方式运行 [Get Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="02d0b-115">This sample runs the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet synchronously in the default runspace provided by Windows PowerShell.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Management.Automation;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace01
  {
    /// <summary>
    /// This sample uses the PowerShell class to execute
    /// the get-process cmdlet synchronously. The name and
    /// handlecount are then extracted from the PSObjects
    /// returned and displayed.
    /// </summary>
    /// <param name="args">Parameter not used.</param>
    /// <remarks>
    /// This sample demonstrates the following:
    /// 1. Creating a PowerShell object to run a command.
    /// 2. Adding a command to the pipeline of the PowerShell object.
    /// 3. Running the command synchronously.
    /// 4. Using PSObject objects to extract properties from the objects
    ///    returned by the command.
    /// </remarks>
    private static void Main(string[] args)
    {
      // Create a PowerShell object. Creating this object takes care of
      // building all of the other data structures needed to run the command.
      using (PowerShell powershell = PowerShell.Create().AddCommand("get-process"))
      {
        Console.WriteLine("Process              HandleCount");
        Console.WriteLine("--------------------------------");

        // Invoke the command synchronously and display the
        // ProcessName and HandleCount properties of the
        // objects that are returned.
        foreach (PSObject result in powershell.Invoke())
        {
          Console.WriteLine(
                      "{0,-20} {1}",
                      result.Members["ProcessName"].Value,
                      result.Members["HandleCount"].Value);
        }
      }

      System.Console.WriteLine("Hit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="02d0b-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="02d0b-116">See Also</span></span>
