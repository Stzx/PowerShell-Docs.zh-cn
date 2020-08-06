---
title: GetProcessSample02 示例 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: fa10774508b70f4aab4546cf4d6fbe8978032f1b
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784225"
---
# <a name="getprocesssample02-sample"></a><span data-ttu-id="156e9-102">GetProcessSample02 示例</span><span class="sxs-lookup"><span data-stu-id="156e9-102">GetProcessSample02 Sample</span></span>

<span data-ttu-id="156e9-103">此示例演示如何编写一个用于检索本地计算机上的进程的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="156e9-103">This sample shows how to write a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="156e9-104">它提供一个 `Name` 参数，该参数可用于指定要检索的进程。</span><span class="sxs-lookup"><span data-stu-id="156e9-104">It provides a `Name` parameter that can be used to specify the processes to be retrieved.</span></span> <span data-ttu-id="156e9-105">此 cmdlet 是 `Get-Process` Windows PowerShell 2.0 提供的简化版本的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="156e9-105">This cmdlet is a simplified version of the `Get-Process` cmdlet provided by Windows PowerShell 2.0.</span></span>

## <a name="how-to-build-the-sample-using-visual-studio"></a><span data-ttu-id="156e9-106">如何使用 Visual Studio 生成示例。</span><span class="sxs-lookup"><span data-stu-id="156e9-106">How to build the sample using Visual Studio.</span></span>

1. <span data-ttu-id="156e9-107">安装 Windows PowerShell 2.0 SDK 后，导航到 GetProcessSample02 文件夹。</span><span class="sxs-lookup"><span data-stu-id="156e9-107">With the Windows PowerShell 2.0 SDK installed, navigate to the GetProcessSample02 folder.</span></span> <span data-ttu-id="156e9-108">默认位置为 C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample02。</span><span class="sxs-lookup"><span data-stu-id="156e9-108">The default location is C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample02.</span></span>

2. <span data-ttu-id="156e9-109">双击解决方案的图标 ( .sln) 文件。</span><span class="sxs-lookup"><span data-stu-id="156e9-109">Double-click the icon for the solution (.sln) file.</span></span> <span data-ttu-id="156e9-110">这会在 Visual Studio 中打开示例项目。</span><span class="sxs-lookup"><span data-stu-id="156e9-110">This opens the sample project in Visual Studio.</span></span>

3. <span data-ttu-id="156e9-111">在“生成”菜单中选择“生成解决方案” 。</span><span class="sxs-lookup"><span data-stu-id="156e9-111">In the **Build** menu, select **Build Solution**.</span></span>

    <span data-ttu-id="156e9-112">示例库将在默认的 \bin 或 \bin\debug 文件夹中生成。</span><span class="sxs-lookup"><span data-stu-id="156e9-112">The library for the sample will be built in the default \bin or \bin\debug folders.</span></span>

### <a name="how-to-run-the-sample"></a><span data-ttu-id="156e9-113">如何运行示例</span><span class="sxs-lookup"><span data-stu-id="156e9-113">How to run the sample</span></span>

1. <span data-ttu-id="156e9-114">创建以下模块文件夹：</span><span class="sxs-lookup"><span data-stu-id="156e9-114">Create the following module folder:</span></span>

    `[user]/documents/windowspowershell/modules/GetProcessSample02`

2. <span data-ttu-id="156e9-115">将示例程序集复制到模块文件夹中。</span><span class="sxs-lookup"><span data-stu-id="156e9-115">Copy the sample assembly to the module folder.</span></span>

3. <span data-ttu-id="156e9-116">启动 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="156e9-116">Start Windows PowerShell.</span></span>

4. <span data-ttu-id="156e9-117">运行以下命令，将程序集加载到 Windows PowerShell：</span><span class="sxs-lookup"><span data-stu-id="156e9-117">Run the following command to load the assembly into Windows PowerShell:</span></span>

    `import-module getprossessample02`

5. <span data-ttu-id="156e9-118">运行以下命令以运行 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="156e9-118">Run the following command to run the cmdlet:</span></span>

    `get-proc`

## <a name="requirements"></a><span data-ttu-id="156e9-119">要求</span><span class="sxs-lookup"><span data-stu-id="156e9-119">Requirements</span></span>

<span data-ttu-id="156e9-120">此示例需要 Windows PowerShell 2.0。</span><span class="sxs-lookup"><span data-stu-id="156e9-120">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="156e9-121">演示</span><span class="sxs-lookup"><span data-stu-id="156e9-121">Demonstrates</span></span>

<span data-ttu-id="156e9-122">此示例演示以下各项。</span><span class="sxs-lookup"><span data-stu-id="156e9-122">This sample demonstrates the following.</span></span>

- <span data-ttu-id="156e9-123">使用 Cmdlet 特性声明 cmdlet 类。</span><span class="sxs-lookup"><span data-stu-id="156e9-123">Declaring a cmdlet class using the Cmdlet attribute.</span></span>

- <span data-ttu-id="156e9-124">使用参数属性声明 cmdlet 参数。</span><span class="sxs-lookup"><span data-stu-id="156e9-124">Declaring a cmdlet parameter using the Parameter attribute.</span></span>

- <span data-ttu-id="156e9-125">指定参数的位置。</span><span class="sxs-lookup"><span data-stu-id="156e9-125">Specifying the position of the parameter.</span></span>

- <span data-ttu-id="156e9-126">声明参数输入的验证特性。</span><span class="sxs-lookup"><span data-stu-id="156e9-126">Declaring a validation attribute for the parameter input.</span></span>

## <a name="example"></a><span data-ttu-id="156e9-127">示例</span><span class="sxs-lookup"><span data-stu-id="156e9-127">Example</span></span>

<span data-ttu-id="156e9-128">此示例演示了包含参数的进程中 cmdlet 的实现 `Name` 。</span><span class="sxs-lookup"><span data-stu-id="156e9-128">This sample shows an implementation of the Get-Proc cmdlet that includes a `Name` parameter.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="156e9-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="156e9-129">See Also</span></span>

[<span data-ttu-id="156e9-130">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="156e9-130">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
