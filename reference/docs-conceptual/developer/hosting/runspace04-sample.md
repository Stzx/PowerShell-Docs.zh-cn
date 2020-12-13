---
ms.date: 09/13/2016
ms.topic: reference
title: Runspace04 示例
description: Runspace04 示例
ms.openlocfilehash: 5a2e1137963e02def419bb924c63b0d651b0fdfa
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657744"
---
# <a name="runspace04-sample"></a><span data-ttu-id="335ff-103">Runspace04 示例</span><span class="sxs-lookup"><span data-stu-id="335ff-103">Runspace04 Sample</span></span>

<span data-ttu-id="335ff-104">此示例演示如何使用 [system.web](/dotnet/api/system.management.automation.powershell) 类来运行命令，以及如何捕获运行命令时引发的终止错误。</span><span class="sxs-lookup"><span data-stu-id="335ff-104">This sample shows how to use the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) class to run commands, and how to catch terminating errors that are thrown when running the commands.</span></span> <span data-ttu-id="335ff-105">运行了两个命令，最后一个命令传递给了一个无效的参数。</span><span class="sxs-lookup"><span data-stu-id="335ff-105">Two commands are run, and the last command is passed a parameter argument that is not valid.</span></span> <span data-ttu-id="335ff-106">因此，未返回对象并引发了终止错误。</span><span class="sxs-lookup"><span data-stu-id="335ff-106">As a result, no objects are returned and a terminating error is thrown.</span></span>

## <a name="requirements"></a><span data-ttu-id="335ff-107">要求</span><span class="sxs-lookup"><span data-stu-id="335ff-107">Requirements</span></span>

<span data-ttu-id="335ff-108">此示例需要 Windows PowerShell 2.0。</span><span class="sxs-lookup"><span data-stu-id="335ff-108">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="335ff-109">演示</span><span class="sxs-lookup"><span data-stu-id="335ff-109">Demonstrates</span></span>

<span data-ttu-id="335ff-110">此示例演示以下各项。</span><span class="sxs-lookup"><span data-stu-id="335ff-110">This sample demonstrates the following.</span></span>

- <span data-ttu-id="335ff-111">正在创建一个 [系统管理组件](/dotnet/api/system.management.automation.powershell) 对象。</span><span class="sxs-lookup"><span data-stu-id="335ff-111">Creating a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="335ff-112">将命令添加到 [system.web](/dotnet/api/system.management.automation.powershell) 对象的管道。</span><span class="sxs-lookup"><span data-stu-id="335ff-112">Adding commands to the pipeline of the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="335ff-113">向管道添加参数参数。</span><span class="sxs-lookup"><span data-stu-id="335ff-113">Adding parameter arguments to the pipeline.</span></span>

- <span data-ttu-id="335ff-114">同步调用命令。</span><span class="sxs-lookup"><span data-stu-id="335ff-114">Invoking the commands synchronously.</span></span>

- <span data-ttu-id="335ff-115">使用 system.exception 对象从命令返回 [的对象中](/dotnet/api/System.Management.Automation.PSObject) 提取并显示属性。</span><span class="sxs-lookup"><span data-stu-id="335ff-115">Using [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects to extract and display properties from the objects returned by the commands.</span></span>

- <span data-ttu-id="335ff-116">检索和显示运行命令时生成的错误记录。</span><span class="sxs-lookup"><span data-stu-id="335ff-116">Retrieving and displaying error records that were generated during the running of the commands.</span></span>

- <span data-ttu-id="335ff-117">捕获并显示命令引发的终止异常。</span><span class="sxs-lookup"><span data-stu-id="335ff-117">Catching and displaying terminating exceptions thrown by the commands.</span></span>

## <a name="example"></a><span data-ttu-id="335ff-118">示例</span><span class="sxs-lookup"><span data-stu-id="335ff-118">Example</span></span>

<span data-ttu-id="335ff-119">此示例在 Windows PowerShell 提供的默认运行空间中同步运行命令。</span><span class="sxs-lookup"><span data-stu-id="335ff-119">This sample runs commands synchronously in the default runspace provided by Windows PowerShell.</span></span> <span data-ttu-id="335ff-120">由于传递给命令的参数参数无效，最后一个命令将引发一个终止错误。</span><span class="sxs-lookup"><span data-stu-id="335ff-120">The last command throws a terminating error because a parameter argument that is not valid is passed to the command.</span></span> <span data-ttu-id="335ff-121">将捕获并显示终止错误。</span><span class="sxs-lookup"><span data-stu-id="335ff-121">The terminating error is trapped and displayed.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace04
  {
    /// <summary>
    /// This sample shows how to use a PowerShell object to run commands.
    /// The commands generate a terminating exception that the caller
    /// should catch and process.
    /// </summary>
    /// <param name="args">The parameter is not used.</param>
    /// <remarks>
    /// This sample demonstrates the following:
    /// 1. Creating a PowerShell object to run commands.
    /// 2. Adding commands to the pipeline of  the PowerShell object.
    /// 3. Passing input objects to the commands from the calling program.
    /// 4. Using PSObject objects to extract and display properties from the
    ///    objects returned by the commands.
    /// 5. Retrieving and displaying error records that were generated
    ///    while running the commands.
    /// 6. Catching and displaying terminating exceptions generated
    ///    while running the commands.
    /// </remarks>
    private static void Main(string[] args)
    {
      // Create a PowerShell object.
      using (PowerShell powershell = PowerShell.Create())
      {
        // Add the commands to the PowerShell object.
        powershell.AddCommand("Get-ChildItem").AddCommand("Select-String").AddArgument("*");

        // Run the commands synchronously. Because of the bad regular expression,
        // no objects will be returned. Instead, an exception will be thrown.
        try
        {
          foreach (PSObject result in powershell.Invoke())
          {
            Console.WriteLine("'{0}'", result.ToString());
          }

          // Process any error records that were generated while running the commands.
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
        catch (RuntimeException runtimeException)
        {
          // Trap any exception generated by the commands. These exceptions
          // will all be derived from the RuntimeException exception.
          System.Console.WriteLine(
                        "Runtime exception: {0}: {1}\n{2}",
                        runtimeException.ErrorRecord.InvocationInfo.InvocationName,
                        runtimeException.Message,
                        runtimeException.ErrorRecord.InvocationInfo.PositionMessage);
        }
      }

      System.Console.WriteLine("\nHit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="335ff-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="335ff-122">See Also</span></span>

[<span data-ttu-id="335ff-123">编写 Windows PowerShell 主机应用程序</span><span class="sxs-lookup"><span data-stu-id="335ff-123">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)
