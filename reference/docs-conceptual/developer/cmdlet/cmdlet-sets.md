---
ms.date: 09/13/2016
ms.topic: reference
title: Cmdlet 集
description: Cmdlet 集
ms.openlocfilehash: b4bcb6548f9d64a8cc5e3fc3a66c671a5566001d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668229"
---
# <a name="cmdlet-sets"></a><span data-ttu-id="eb4de-103">Cmdlet 集</span><span class="sxs-lookup"><span data-stu-id="eb4de-103">Cmdlet Sets</span></span>

<span data-ttu-id="eb4de-104">设计 cmdlet 时，可能会遇到需要对同一数据块执行多个操作的情况。</span><span class="sxs-lookup"><span data-stu-id="eb4de-104">When you design your cmdlets, you might encounter cases in which you need to perform several actions on the same piece of data.</span></span> <span data-ttu-id="eb4de-105">例如，你可能需要获取并设置数据，或者启动和停止进程。</span><span class="sxs-lookup"><span data-stu-id="eb4de-105">For example, you might need to get and set data or start and stop a process.</span></span> <span data-ttu-id="eb4de-106">尽管你将需要创建单独的 cmdlet 来执行每个操作，但 cmdlet 设计应包括一个基类，用于派生单个 cmdlet 的类。</span><span class="sxs-lookup"><span data-stu-id="eb4de-106">Although you will need to create separate cmdlets to perform each action, your cmdlet design should include a base class from which the classes for the individual cmdlets are derived.</span></span>

<span data-ttu-id="eb4de-107">实现基类时，请注意以下事项。</span><span class="sxs-lookup"><span data-stu-id="eb4de-107">Keep the following things in mind when implementing a base class.</span></span>

- <span data-ttu-id="eb4de-108">声明基类中所有派生 cmdlet 使用的任何通用参数。</span><span class="sxs-lookup"><span data-stu-id="eb4de-108">Declare any common parameters used by all the derived cmdlets in the base class.</span></span>

- <span data-ttu-id="eb4de-109">向相应的 cmdlet 类添加 cmdlet 特定参数。</span><span class="sxs-lookup"><span data-stu-id="eb4de-109">Add cmdlet-specific parameters to the appropriate cmdlet class.</span></span>

- <span data-ttu-id="eb4de-110">重写基类中的相应输入处理方法。</span><span class="sxs-lookup"><span data-stu-id="eb4de-110">Override the appropriate input processing method in the base class.</span></span>

- <span data-ttu-id="eb4de-111">在所有 cmdlet 类上声明 [CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) 属性，但不要在基类上声明它。</span><span class="sxs-lookup"><span data-stu-id="eb4de-111">Declare the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) attribute on all cmdlet classes, but do not declare it on the base class.</span></span>

- <span data-ttu-id="eb4de-112">实现一个名为 [add-pssnapin](/dotnet/api/System.Management.Automation.PSSnapIn) 或 [Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn) 类，其名称和说明反映一组 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="eb4de-112">Implement a [System.Management.Automation.PSSnapIn](/dotnet/api/System.Management.Automation.PSSnapIn) or [System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn) class whose name and description reflects the set of cmdlets.</span></span>

## <a name="example"></a><span data-ttu-id="eb4de-113">示例</span><span class="sxs-lookup"><span data-stu-id="eb4de-113">Example</span></span>

<span data-ttu-id="eb4de-114">下面的示例演示了从同一基类派生 Get-Proc 和 Stop-Proc cmdlet 使用的基类。</span><span class="sxs-lookup"><span data-stu-id="eb4de-114">The following example shows the implementation of a base class that is used by Get-Proc and Stop-Proc cmdlet that derive from the same base class.</span></span>

```csharp
using System;
using System.Diagnostics;
using System.Management.Automation;             //Windows PowerShell namespace.

namespace Microsoft.Samples.PowerShell.Commands
{

  #region ProcessCommands

  /// <summary>
  /// This class implements a Stop-Proc cmdlet. The parameters
  /// for this cmdlet are defined by the BaseProcCommand class.
  /// </summary>
  [Cmdlet(VerbsLifecycle.Stop, "Proc", SupportsShouldProcess = true)]
  public class StopProcCommand : BaseProcCommand
  {
    public override void ProcessObject(Process process)
    {
      if (ShouldProcess(process.ProcessName, "Stop-Proc"))
      {
        process.Kill();
      }
    }
  }

  /// <summary>
  /// This class implements a Get-Proc cmdlet. The parameters
  /// for this cmdlet are defined by the BaseProcCommand class.
  /// </summary>

  [Cmdlet(VerbsCommon.Get, "Proc")]
  public class GetProcCommand : BaseProcCommand
  {
    public override void ProcessObject(Process process)
    {
      WriteObject(process);
    }
  }

  /// <summary>
  /// This class is the base class that defines the common
  /// functionality used by the Get-Proc and Stop-Proc
  /// cmdlets.
  /// </summary>
  public class BaseProcCommand : Cmdlet
  {
    #region Parameters

    // Defines the Name parameter that is used to
    // specify a process by its name.
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

    // Defines the Exclude parameter that is used to
    // specify which processes should be excluded when
    // the cmdlet performs its action.
    [Parameter()]
    public string[] Exclude
    {
      get { return excludeNames; }
      set { excludeNames = value; }
    }
    private string[] excludeNames = new string[0];
    #endregion Parameters

    public virtual void ProcessObject(Process process)
    {
      throw new NotImplementedException("This method should be overridden.");
    }

    #region Cmdlet Overrides
    // <summary>
    // For each of the requested process names, retrieve and write
    // the associated processes.
    // </summary>
    protected override void ProcessRecord()
    {
      // Set up the wildcard characters used in resolving
      // the process names.
      WildcardOptions options = WildcardOptions.IgnoreCase |
                                WildcardOptions.Compiled;

      WildcardPattern[] include = new WildcardPattern[Name.Length];
      for (int i = 0; i < Name.Length; i++)
      {
        include[i] = new WildcardPattern(Name[i], options);
      }

      WildcardPattern[] exclude = new WildcardPattern[Exclude.Length];
      for (int i = 0; i < Exclude.Length; i++)
      {
        exclude[i] = new WildcardPattern(Exclude[i], options);
      }

      foreach (Process p in Process.GetProcesses())
      {
        foreach (WildcardPattern wIn in include)
        {
          if (wIn.IsMatch(p.ProcessName))
          {
            bool processThisOne = true;
            foreach (WildcardPattern wOut in exclude)
            {
              if (wOut.IsMatch(p.ProcessName))
              {
                processThisOne = false;
                break;
              }
            }
            if (processThisOne)
            {
              ProcessObject(p);
            }
            break;
          }
        }
      }
    }
    #endregion Cmdlet Overrides
  }
    #endregion ProcessCommands
}
```

## <a name="see-also"></a><span data-ttu-id="eb4de-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb4de-115">See Also</span></span>

[<span data-ttu-id="eb4de-116">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="eb4de-116">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
