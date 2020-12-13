---
ms.date: 09/13/2016
ms.topic: reference
title: GetProcessSample02 示例
description: GetProcessSample02 示例
ms.openlocfilehash: a0f43806b707359cb454817341f2c4972033c46a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660514"
---
# <a name="getprocesssample02-sample"></a><span data-ttu-id="4e31f-103">GetProcessSample02 示例</span><span class="sxs-lookup"><span data-stu-id="4e31f-103">GetProcessSample02 Sample</span></span>

<span data-ttu-id="4e31f-104">此示例演示如何编写一个用于检索本地计算机上的进程的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4e31f-104">This sample shows how to write a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="4e31f-105">它提供一个 `Name` 参数，该参数可用于指定要检索的进程。</span><span class="sxs-lookup"><span data-stu-id="4e31f-105">It provides a `Name` parameter that can be used to specify the processes to be retrieved.</span></span> <span data-ttu-id="4e31f-106">此 cmdlet 是 `Get-Process` Windows PowerShell 2.0 提供的简化版本的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4e31f-106">This cmdlet is a simplified version of the `Get-Process` cmdlet provided by Windows PowerShell 2.0.</span></span>

## <a name="how-to-build-the-sample-using-visual-studio"></a><span data-ttu-id="4e31f-107">如何使用 Visual Studio 生成示例。</span><span class="sxs-lookup"><span data-stu-id="4e31f-107">How to build the sample using Visual Studio.</span></span>

1. <span data-ttu-id="4e31f-108">安装 Windows PowerShell 2.0 SDK 后，导航到 GetProcessSample02 文件夹。</span><span class="sxs-lookup"><span data-stu-id="4e31f-108">With the Windows PowerShell 2.0 SDK installed, navigate to the GetProcessSample02 folder.</span></span> <span data-ttu-id="4e31f-109">默认位置为 C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample02。</span><span class="sxs-lookup"><span data-stu-id="4e31f-109">The default location is C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample02.</span></span>

2. <span data-ttu-id="4e31f-110">双击解决方案的图标 ( .sln) 文件。</span><span class="sxs-lookup"><span data-stu-id="4e31f-110">Double-click the icon for the solution (.sln) file.</span></span> <span data-ttu-id="4e31f-111">这会在 Visual Studio 中打开示例项目。</span><span class="sxs-lookup"><span data-stu-id="4e31f-111">This opens the sample project in Visual Studio.</span></span>

3. <span data-ttu-id="4e31f-112">在“生成”菜单中选择“生成解决方案” 。</span><span class="sxs-lookup"><span data-stu-id="4e31f-112">In the **Build** menu, select **Build Solution**.</span></span>

    <span data-ttu-id="4e31f-113">示例库将在默认的 \bin 或 \bin\debug 文件夹中生成。</span><span class="sxs-lookup"><span data-stu-id="4e31f-113">The library for the sample will be built in the default \bin or \bin\debug folders.</span></span>

### <a name="how-to-run-the-sample"></a><span data-ttu-id="4e31f-114">如何运行示例</span><span class="sxs-lookup"><span data-stu-id="4e31f-114">How to run the sample</span></span>

1. <span data-ttu-id="4e31f-115">创建以下模块文件夹：</span><span class="sxs-lookup"><span data-stu-id="4e31f-115">Create the following module folder:</span></span>

    `[user]/documents/windowspowershell/modules/GetProcessSample02`

2. <span data-ttu-id="4e31f-116">将示例程序集复制到模块文件夹中。</span><span class="sxs-lookup"><span data-stu-id="4e31f-116">Copy the sample assembly to the module folder.</span></span>

3. <span data-ttu-id="4e31f-117">启动 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4e31f-117">Start Windows PowerShell.</span></span>

4. <span data-ttu-id="4e31f-118">运行以下命令，将程序集加载到 Windows PowerShell：</span><span class="sxs-lookup"><span data-stu-id="4e31f-118">Run the following command to load the assembly into Windows PowerShell:</span></span>

    `import-module getprossessample02`

5. <span data-ttu-id="4e31f-119">运行以下命令以运行 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="4e31f-119">Run the following command to run the cmdlet:</span></span>

    `get-proc`

## <a name="requirements"></a><span data-ttu-id="4e31f-120">要求</span><span class="sxs-lookup"><span data-stu-id="4e31f-120">Requirements</span></span>

<span data-ttu-id="4e31f-121">此示例需要 Windows PowerShell 2.0。</span><span class="sxs-lookup"><span data-stu-id="4e31f-121">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="4e31f-122">演示</span><span class="sxs-lookup"><span data-stu-id="4e31f-122">Demonstrates</span></span>

<span data-ttu-id="4e31f-123">此示例演示以下各项。</span><span class="sxs-lookup"><span data-stu-id="4e31f-123">This sample demonstrates the following.</span></span>

- <span data-ttu-id="4e31f-124">使用 Cmdlet 特性声明 cmdlet 类。</span><span class="sxs-lookup"><span data-stu-id="4e31f-124">Declaring a cmdlet class using the Cmdlet attribute.</span></span>

- <span data-ttu-id="4e31f-125">使用参数属性声明 cmdlet 参数。</span><span class="sxs-lookup"><span data-stu-id="4e31f-125">Declaring a cmdlet parameter using the Parameter attribute.</span></span>

- <span data-ttu-id="4e31f-126">指定参数的位置。</span><span class="sxs-lookup"><span data-stu-id="4e31f-126">Specifying the position of the parameter.</span></span>

- <span data-ttu-id="4e31f-127">声明参数输入的验证特性。</span><span class="sxs-lookup"><span data-stu-id="4e31f-127">Declaring a validation attribute for the parameter input.</span></span>

## <a name="example"></a><span data-ttu-id="4e31f-128">示例</span><span class="sxs-lookup"><span data-stu-id="4e31f-128">Example</span></span>

<span data-ttu-id="4e31f-129">此示例演示包含参数的 Get-Proc cmdlet 的实现 `Name` 。</span><span class="sxs-lookup"><span data-stu-id="4e31f-129">This sample shows an implementation of the Get-Proc cmdlet that includes a `Name` parameter.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Commands
{
  using System;
  using System.Diagnostics;
  using System.Management.Automation;     // Windows PowerShell namespace

  #region GetProcCommand

  /// <summary>
  /// This class implements the get-proc cmdlet.
  /// </summary>
  [Cmdlet(VerbsCommon.Get, "Proc")]
  public class GetProcCommand : Cmdlet
  {
    #region Parameters

    /// <summary>
    /// The names of the processes retrieved by the cmdlet.
    /// </summary>
    private string[] processNames;

    /// <summary>
    /// Gets or sets the list of process names on which
    /// the Get-Proc cmdlet will work.
    /// </summary>
    [Parameter(Position = 0)]
    [ValidateNotNullOrEmpty]
    public string[] Name
    {
      get { return this.processNames; }
      set { this.processNames = value; }
    }

    #endregion Parameters

    #region Cmdlet Overrides

    /// <summary>
    /// The ProcessRecord method calls the Process.GetProcesses
    /// method to retrieve the processes specified by the Name
    /// parameter. Then, the WriteObject method writes the
    /// associated process objects to the pipeline.
    /// </summary>
    protected override void ProcessRecord()
    {
      // If no process names are passed to the cmdlet, get all
      // processes.
      if (this.processNames == null)
      {
        WriteObject(Process.GetProcesses(), true);
      }
      else
      {
        // If process names are passed to cmdlet, get and write
        // the associated processes.
        foreach (string name in this.processNames)
        {
          WriteObject(Process.GetProcessesByName(name), true);
        }
      } // End if (processNames...).
    } // End ProcessRecord.
    #endregion Cmdlet Overrides
  } // End GetProcCommand class.
  #endregion GetProcCommand
}
```

## <a name="see-also"></a><span data-ttu-id="4e31f-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4e31f-130">See Also</span></span>

[<span data-ttu-id="4e31f-131">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="4e31f-131">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
