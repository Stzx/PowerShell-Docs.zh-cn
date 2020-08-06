---
title: GetProcessSample03 示例 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 09df93792ab611e167279bc35755d8d6c28e7cf3
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784208"
---
# <a name="getprocesssample03-sample"></a>GetProcessSample03 示例

此示例演示如何实现一个用于检索本地计算机上的进程的 cmdlet。 它提供一个 `Name` 参数，该参数可接受管道中的对象或来自对象属性的值，该对象的属性名称与参数名称相同。 此 cmdlet 是 `Get-Process` Windows PowerShell 2.0 提供的简化版本的 cmdlet。

## <a name="how-to-build-the-sample-using-visual-studio"></a>如何使用 Visual Studio 生成示例。

1. 安装 Windows PowerShell 2.0 SDK 后，导航到 GetProcessSample03 文件夹。 默认位置为 C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample03。

2. 双击解决方案的图标 ( .sln) 文件。 这会在 Visual Studio 中打开示例项目。

3. 在“生成”菜单中选择“生成解决方案” 。

    示例库将在默认的 \bin 或 \bin\debug 文件夹中生成。

### <a name="how-to-run-the-sample"></a>如何运行示例

1. 创建以下模块文件夹：

    `[user]/documents/windowspowershell/modules/GetProcessSample03`

2. 将示例程序集复制到模块文件夹中。

3. 启动 Windows PowerShell。

4. 运行以下命令，将程序集加载到 Windows PowerShell：

    `Import-module getprossessample03`

5. 运行以下命令以运行 cmdlet：

    `get-proc`

## <a name="requirements"></a>要求

此示例需要 Windows PowerShell 2.0。

## <a name="demonstrates"></a>演示

此示例演示以下各项。

- 使用 Cmdlet 特性声明 cmdlet 类。

- 使用参数属性声明 cmdlet 参数。

- 指定参数的位置。

- 指定参数从管道中获取输入。 输入可从对象或对象属性中的值获取，该对象的属性名称与参数名称相同。

- 声明参数输入的验证特性。

## <a name="example"></a>示例

此示例演示了获取处理器 cmdlet 的实现，该 cmdlet 包含 `Name` 接受来自管道的输入的参数。

```csharp
namespace Microsoft.Samples.PowerShell.Commands
{
  using System;
  using System.Diagnostics;
  using System.Management.Automation;           // Windows PowerShell namespace
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
    /// Gets or sets the names of the
    /// process that the cmdlet will retrieve.
    /// </summary>
    [Parameter(
               Position = 0,
               ValueFromPipeline = true,
               ValueFromPipelineByPropertyName = true)]
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
    /// associated processes to the pipeline.
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
        // If process names are passed to the cmdlet, get and write
        // the associated processes.
        foreach (string name in this.processNames)
        {
          WriteObject(Process.GetProcessesByName(name), true);
        }
      } // End if (processNames ...)
    } // End ProcessRecord.

    #endregion Overrides
  } // End GetProcCommand.
  #endregion GetProcCommand
}
```

## <a name="see-also"></a>另请参阅

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
