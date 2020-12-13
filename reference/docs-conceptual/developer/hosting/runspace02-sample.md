---
ms.date: 09/13/2016
ms.topic: reference
title: Runspace02 示例
description: Runspace02 示例
ms.openlocfilehash: 0206e1a80f3e5488fd2dd5628985756a5ca343c8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657895"
---
# <a name="runspace02-sample"></a>Runspace02 示例

此示例演示如何使用 [system.exception 类来](/dotnet/api/system.management.automation.powershell) 同步运行 [获取进程](/powershell/module/Microsoft.PowerShell.Management/Get-Process) 和 [排序对象](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) 的 cmdlet。 [获取进程](/powershell/module/Microsoft.PowerShell.Management/Get-Process)cmdlet 将为在本地计算机上运行的每个[进程返回 System.Diagnostics.Process.Id](/dotnet/api/System.Diagnostics.Process) ，并根据对象的 `Sort-Object` [*](/dotnet/api/System.Diagnostics.Process.Id)属性对对象进行排序。 这些命令的结果使用 " [system.web](/dotnet/api/System.Windows.Forms.DataGridView) " 控件显示。

## <a name="requirements"></a>要求

此示例需要 Windows PowerShell 2.0。

## <a name="demonstrates"></a>演示

此示例演示以下各项。

- 创建要运行命令的 [system.web](/dotnet/api/system.management.automation.powershell) 对象。

- 将命令添加到 [system.web](/dotnet/api/system.management.automation.powershell) 对象的管道。

- 同步运行命令。

- 使用 [system.web](/dotnet/api/System.Windows.Forms.DataGridView) 控件在 Windows 窗体应用程序中显示命令的输出。

## <a name="example"></a>示例

此示例在 Windows PowerShell 提供的默认运行空间中同步运行 [获取进程](/powershell/module/Microsoft.PowerShell.Management/Get-Process) 和 [排序对象](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) cmdlet。 使用 " [system.web](/dotnet/api/System.Windows.Forms.DataGridView) " 控件以窗体显示输出。

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Collections;
  using System.Collections.ObjectModel;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;
  using System.Windows.Forms;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace02
  {
    /// <summary>
    /// This method creates the form where the output is displayed.
    /// </summary>
    private static void CreateForm()
    {
      Form form = new Form();
      DataGridView grid = new DataGridView();
      form.Controls.Add(grid);
      grid.Dock = DockStyle.Fill;

      // Create a PowerShell object. Creating this object takes care of
      // building all of the other data structures needed to run the command.
      using (PowerShell powershell = PowerShell.Create())
      {
        powershell.AddCommand("get-process").AddCommand("sort-object").AddArgument("ID");
        if (Runspace.DefaultRunspace == null)
        {
          Runspace.DefaultRunspace = powershell.Runspace;
        }

        Collection<PSObject> results = powershell.Invoke();

        // The generic collection needs to be re-wrapped in an ArrayList
        // for data-binding to work.
        ArrayList objects = new ArrayList();
        objects.AddRange(results);

        // The DataGridView will use the PSObjectTypeDescriptor type
        // to retrieve the properties.
        grid.DataSource = objects;
      }

      form.ShowDialog();
    }

    /// <summary>
    /// This sample uses a PowerShell object to run the Get-Process
    /// and Sort-Object cmdlets synchronously. Windows Forms and
    /// data binding are then used to display the results in a
    /// DataGridView control.
    /// </summary>
    /// <param name="args">The parameter is not used.</param>
    /// <remarks>
    /// This sample demonstrates the following:
    /// 1. Creating a PowerShell object.
    /// 2. Adding commands and arguments to the pipeline of
    ///    the PowerShell object.
    /// 3. Running the commands synchronously.
    /// 4. Using a DataGridView control to display the output
    ///    of the commands in a Windows Forms application.
    /// </remarks>
    private static void Main(string[] args)
    {
      Runspace02.CreateForm();
    }
  }
}
```

## <a name="see-also"></a>另请参阅

[编写 Windows PowerShell 主机应用程序](./writing-a-windows-powershell-host-application.md)
