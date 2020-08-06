---
title: StopProcessSample02 示例 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: bab32f5a2544905bd858bcecf5b0b2e2d127e642
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786435"
---
# <a name="stopprocesssample02-sample"></a><span data-ttu-id="8a3d3-102">StopProcessSample02 示例</span><span class="sxs-lookup"><span data-stu-id="8a3d3-102">StopProcessSample02 Sample</span></span>

<span data-ttu-id="8a3d3-103">此示例演示如何编写一个 cmdlet，该 cmdlet 在停止本地计算机上的进程时写入 debug (WriteDebug) 、verbose (WriteVerbose) 和警告 (WriteWarning) 消息。</span><span class="sxs-lookup"><span data-stu-id="8a3d3-103">This sample shows how to write a cmdlet that writes debug (WriteDebug), verbose (WriteVerbose), and warning (WriteWarning) messages while stopping processes on the local computer.</span></span> <span data-ttu-id="8a3d3-104">此 cmdlet 类似于 `Stop-Process` Windows PowerShell 2.0 提供的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8a3d3-104">This cmdlet is similar to the `Stop-Process` cmdlet provided by Windows PowerShell 2.0.</span></span>

### <a name="how-to-build-the-sample-by-using-visual-studio"></a><span data-ttu-id="8a3d3-105">如何使用 Visual Studio 生成示例。</span><span class="sxs-lookup"><span data-stu-id="8a3d3-105">How to build the sample by using Visual Studio.</span></span>

1. <span data-ttu-id="8a3d3-106">打开 Windows Internet Explorer 并导航到示例目录下的 StopProcessSample02 目录。</span><span class="sxs-lookup"><span data-stu-id="8a3d3-106">Open Windows Internet Explorer and navigate to the StopProcessSample02 directory under the Samples directory.</span></span>

    <span data-ttu-id="8a3d3-107">安装 Windows PowerShell 2.0 SDK 后，导航到 StopProcessSample02 文件夹。</span><span class="sxs-lookup"><span data-stu-id="8a3d3-107">With the Windows PowerShell 2.0 SDK installed, navigate to the StopProcessSample02 folder.</span></span> <span data-ttu-id="8a3d3-108">默认位置为 C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\StopProcessSample02。</span><span class="sxs-lookup"><span data-stu-id="8a3d3-108">The default location is C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\StopProcessSample02.</span></span>

2. <span data-ttu-id="8a3d3-109">双击解决方案的图标 ( .sln) 文件。</span><span class="sxs-lookup"><span data-stu-id="8a3d3-109">Double-click the icon for the solution (.sln) file.</span></span> <span data-ttu-id="8a3d3-110">这会在 Microsoft Visual Studio 中打开示例项目。</span><span class="sxs-lookup"><span data-stu-id="8a3d3-110">This opens the sample project in Microsoft Visual Studio.</span></span>

3. <span data-ttu-id="8a3d3-111">在“生成”菜单中选择“生成解决方案” 。</span><span class="sxs-lookup"><span data-stu-id="8a3d3-111">In the **Build** menu, select **Build Solution**.</span></span>

    <span data-ttu-id="8a3d3-112">示例库将在默认的 \bin 或 \bin\debug 文件夹中生成。</span><span class="sxs-lookup"><span data-stu-id="8a3d3-112">The library for the sample will be built in the default \bin or \bin\debug folders.</span></span>

### <a name="how-to-run-the-sample"></a><span data-ttu-id="8a3d3-113">如何运行示例</span><span class="sxs-lookup"><span data-stu-id="8a3d3-113">How to run the sample</span></span>

1. <span data-ttu-id="8a3d3-114">创建以下模块文件夹：</span><span class="sxs-lookup"><span data-stu-id="8a3d3-114">Create the following module folder:</span></span>

    `[user]/documents/windowspowershell/modules/StopProcessSample02`

2. <span data-ttu-id="8a3d3-115">将示例程序集复制到模块文件夹中。</span><span class="sxs-lookup"><span data-stu-id="8a3d3-115">Copy the sample assembly to the module folder.</span></span>

3. <span data-ttu-id="8a3d3-116">启动 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="8a3d3-116">Start Windows PowerShell.</span></span>

4. <span data-ttu-id="8a3d3-117">运行以下命令，将程序集加载到 Windows PowerShell：</span><span class="sxs-lookup"><span data-stu-id="8a3d3-117">Run the following command to load the assembly into Windows PowerShell:</span></span>

    `import-module stopprossessample02`

5. <span data-ttu-id="8a3d3-118">运行以下命令以运行 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="8a3d3-118">Run the following command to run the cmdlet:</span></span>

    `stop-proc`

## <a name="requirements"></a><span data-ttu-id="8a3d3-119">要求</span><span class="sxs-lookup"><span data-stu-id="8a3d3-119">Requirements</span></span>

<span data-ttu-id="8a3d3-120">此示例需要 Windows PowerShell 2.0。</span><span class="sxs-lookup"><span data-stu-id="8a3d3-120">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="8a3d3-121">演示</span><span class="sxs-lookup"><span data-stu-id="8a3d3-121">Demonstrates</span></span>

<span data-ttu-id="8a3d3-122">此示例演示以下各项。</span><span class="sxs-lookup"><span data-stu-id="8a3d3-122">This sample demonstrates the following.</span></span>

- <span data-ttu-id="8a3d3-123">使用 Cmdlet 特性声明 cmdlet 类。</span><span class="sxs-lookup"><span data-stu-id="8a3d3-123">Declaring a cmdlet class by using the Cmdlet attribute.</span></span>

- <span data-ttu-id="8a3d3-124">使用 Parameter 特性声明 cmdlet 参数。</span><span class="sxs-lookup"><span data-stu-id="8a3d3-124">Declaring a cmdlet parameters by using the Parameter attribute.</span></span>

- <span data-ttu-id="8a3d3-125">写入详细消息。</span><span class="sxs-lookup"><span data-stu-id="8a3d3-125">Writing verbose messages.</span></span> <span data-ttu-id="8a3d3-126">有关用于编写详细消息的方法的详细信息，请参阅[WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose)。</span><span class="sxs-lookup"><span data-stu-id="8a3d3-126">For more information about the method used to write verbose messages, see [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose).</span></span>

- <span data-ttu-id="8a3d3-127">正在写入错误消息。</span><span class="sxs-lookup"><span data-stu-id="8a3d3-127">Writing error messages.</span></span> <span data-ttu-id="8a3d3-128">有关用于写入错误消息的方法的详细信息，请参阅[WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)。</span><span class="sxs-lookup"><span data-stu-id="8a3d3-128">For more information about the method used to write error messages, see [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError).</span></span>

- <span data-ttu-id="8a3d3-129">写入警告消息。</span><span class="sxs-lookup"><span data-stu-id="8a3d3-129">Writing warning messages.</span></span> <span data-ttu-id="8a3d3-130">有关用于编写警告消息的方法的详细信息，请参阅[WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning)。</span><span class="sxs-lookup"><span data-stu-id="8a3d3-130">For more information about the method used to write warning messages, see [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning).</span></span>

## <a name="example"></a><span data-ttu-id="8a3d3-131">示例</span><span class="sxs-lookup"><span data-stu-id="8a3d3-131">Example</span></span>

<span data-ttu-id="8a3d3-132">此示例演示如何通过使用 `WriteDebug` 、和方法来编写调试、详细和警告消息 `WriteVerbose` `WriteWarning` 。</span><span class="sxs-lookup"><span data-stu-id="8a3d3-132">This sample shows how to write debug, verbose, and warning messages by using the `WriteDebug`, `WriteVerbose`, and `WriteWarning` methods.</span></span>

```csharp
using System;
using System.Diagnostics;
using System.Collections;
using Win32Exception = System.ComponentModel.Win32Exception;
using System.Management.Automation;             //Windows PowerShell namespace
using System.Globalization;

namespace Microsoft.Samples.PowerShell.Commands
{
   #region StopProcCommand

    /// <summary>
   /// This class implements the stop-proc cmdlet.
   /// </summary>
   [Cmdlet(VerbsLifecycle.Stop, "Proc",
       SupportsShouldProcess = true)]
   public class StopProcCommand : Cmdlet
   {
       #region Parameters

      /// <summary>
      /// This parameter provides the list of process names on
      /// which the Stop-Proc cmdlet will work.
      /// </summary>
       [Parameter(
          Position = 0,
          Mandatory = true,
          ValueFromPipeline = true,
          ValueFromPipelineByPropertyName = true
       )]
       public string[] Name
       {
          get { return processNames; }
          set { processNames = value; }
       }
       private string[] processNames;

       /// <summary>
       /// This parameter overrides the ShouldContinue call to force
       /// the cmdlet to stop its operation. This parameter should always
       /// be used with caution.
       /// </summary>
       [Parameter]
       public SwitchParameter Force
       {
           get { return force; }
           set { force = value; }
       }
       private bool force;

       /// <summary>
       /// This parameter indicates that the cmdlet should return
       /// an object to the pipeline after the processing has been
       /// completed.
       /// </summary>
       [Parameter]
       public SwitchParameter PassThru
       {
           get { return passThru; }
           set { passThru = value; }
       }
       private bool passThru;

       #endregion Parameters

       #region Cmdlet Overrides

       /// <summary>
       /// The ProcessRecord method does the following for each of the
       /// requested process names:
       /// 1) Check that the process is not a critical process.
       /// 2) Attempt to stop that process.
       /// If no process is requested then nothing occurs.
       /// </summary>
       protected override void ProcessRecord()
       {
           foreach (string name in processNames)
           {
               string message = null;

               // For every process name passed to the cmdlet, get the associated
               // processes.
               // Write a nonterminating error for failure to retrieve
               // a process.

               // Write a user-friendly verbose message to the pipeline. These
               // messages are intended to give the user detailed information
               // on the operations performed by the cmdlet. These messages will
               // appear with the -Verbose option.
               message = String.Format(CultureInfo.CurrentCulture,
                              "Attempting to stop process \"{0}\".", name);
               WriteVerbose(message);

               Process[] processes;

               try
               {
                   processes = Process.GetProcessesByName(name);
               }
               catch (InvalidOperationException ioe)
               {
                   WriteError(new ErrorRecord(ioe,
                                     "UnableToAccessProcessByName",
                                         ErrorCategory.InvalidOperation,
                                             name));
                   continue;
               }

               // Try to stop the processes that have been retrieved.
               foreach (Process process in processes)
               {
                   string processName;

                   try
                   {
                       processName = process.ProcessName;
                   }
                   catch (Win32Exception e)
                   {
                       WriteError(new ErrorRecord(e, "ProcessNameNotFound",
                                         ErrorCategory.ObjectNotFound, process));
                       continue;
                   }

                   // Write a debug message to the host that can be used when
                   // troubleshooting a problem. All debug messages will appear
                   // with the -Debug option.
                   message = String.Format(CultureInfo.CurrentCulture,
                                 "Acquired name for pid {0} : \"{1}\"",
                                        process.Id, processName);
                   WriteDebug(message);

                   // Confirm the operation first.
                   // This is always false if the WhatIf parameter is specified.
                   if (!ShouldProcess(string.Format(CultureInfo.CurrentCulture,
                                        "{0} ({1})",
                                            processName, process.Id)))
                   {
                       continue;
                   }

                   // Make sure that the user really wants to stop a critical
                   // process that can possibly stop the computer.
                   bool criticalProcess = criticalProcessNames.Contains(processName.ToLower(CultureInfo.CurrentCulture));

                   if (criticalProcess && !force)
                   {
                       message = String.Format(CultureInfo.CurrentCulture,
                                    "The process \"{0}\" is a critical process and should not be stopped. Are you sure you wish to stop the process?",
                                        processName);

                       // It is possible that the ProcessRecord method is called
                       // multiple times when objects are received as inputs from
                       // the pipeline. So to retain YesToAll and NoToAll input that
                       // the user may enter across multiple calls to this function,
                       // they are stored as private members of the cmdlet.
                       if (!ShouldContinue(message, "Warning!",
                                    ref yesToAll, ref noToAll))
                       {
                           continue;
                       }
                   } // if (criticalProcess...

                   // Display a warning message if the cmdlet is stopping a
                   // critical process.
                   if (criticalProcess)
                   {
                       message = String.Format(CultureInfo.CurrentCulture,
                                     "Stopping the critical process \"{0}\".",
                                          processName);
                       WriteWarning(message);
                   } // if (criticalProcess...

                   // Stop the named process.
                   try
                   {
                       process.Kill();
                   }
                   catch (Exception e)
                   {
                       if ((e is Win32Exception) || (e is SystemException) ||
                           (e is InvalidOperationException))
                       {
                           // This process could not be stopped so write
                           // a nonterminating error.
                           WriteError(new ErrorRecord(
                                            e,
                                            "CouldNotStopProcess",
                                            ErrorCategory.CloseError,
                                            process)
                                      );
                           continue;
                       } // if ((e is...
                           else throw;
                   } // catch

                   message = String.Format(CultureInfo.CurrentCulture,
                                  "Stopped process \"{0}\", pid {1}.",
                                        processName, process.Id);

                   WriteVerbose(message);

                   // If the PassThru parameter is specified,
                   // return the terminated process object to the pipeline.
                   if (passThru)
                   {
                       message = String.Format(CultureInfo.CurrentCulture,
                                     "Writing process \"{0}\" to pipeline",
                                          processName);
                       WriteDebug(message);
                       WriteObject(process);
                   } // if (passThru...
               } // foreach (Process...
            } // foreach (string...
        } // ProcessRecord

       #endregion Cmdlet Overrides

       #region Private Data

       private bool yesToAll, noToAll;

       /// <summary>
       /// Partial list of critical processes that should not be
       /// stopped.  Lower case is used for case insensitive matching.
       /// </summary>
       private ArrayList criticalProcessNames = new ArrayList(
          new string[] { "system", "winlogon", "spoolsv" }
       );

       #endregion Private Data

   } // StopProcCommand

   #endregion StopProcCommand
}
```

## <a name="see-also"></a><span data-ttu-id="8a3d3-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a3d3-133">See Also</span></span>

[<span data-ttu-id="8a3d3-134">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="8a3d3-134">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
